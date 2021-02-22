+++
author = "Ian Crosby"
title = "Building a Static Website"
date = "2021-02-21"
draft = false
description = "Does this make me full stack?"
tags = [
    "tech",
]
categories = [
    "cloud",
    "test",
]
series = ["Learning-Tech"]
image = "patrick-tomasso-GfDyRbLofHg-unsplash.jpg"
+++

Having spent my career in tech between backend software development and infrastrucutre, the front end has always seemed like black magic to me. So when deciding to setup my own site I was a bit intimidated and also determined to not touch or see any css whatsover. As my previous experience can be summed up below:

![CSS](./css.gif)

In addition to my no-css rule, I had a view other requirements:

* Cheap
* Portable
* Minimal
* Markdown support
* Full CI/CD
* Entirely automated

Luckily, there are a plethora of wonderful and easy to use frameworks nowadays. After a quick search I opted for the following tech stack:

* GitHub (as CMS)
* Hugo
* GitHub Actions (for CI/CD)
* Google Cloud Storage for hosting static content

I sketched out a basic architecture/flow diagram of what I was planning to build:

![Pipeline](./pipeline.png)

First step was to setup the basic site with Hugo. This is straightforward, simply following the Hugo [quick start guide](https://gohugo.io/getting-started/quick-start/) and choosing a theme. Hugo also makes local development extremely simple.

After that I setup a Google Cloud Storage bucket. If you have your own domain (as in my case), you can connect that domain directly with a storage bucket. This requires you to create a CNAME record that points to c.storage.googleapis.com. After that's created you can create the bucket via the gsutil command line tool:

    gsutil mb -c standard -l northamerica-northeast1 gs://www.my-domain.com

`-c` specifies the storage class
`-l` specifies the location/region

Next up is setting up the CI/CD, which in this case is simply building the static assets and pushing them to a Google cloud storage bucket. I specifically chose to use GitHub actions because I've been looking for an excuse to try them out.

Turns out, GitHub actions are quite straightforward. Before diving into writing your own actions, a quick search in the [Marketplace](https://github.com/marketplace?type=actions) will usually get you what you're looking for. In my case, two actions:

* [Actions Hugo](https://github.com/peaceiris/actions-hugo) for building the assets with Hugo.
* [Upload Cloud Storage](https://github.com/google-github-actions/upload-cloud-storage) - for uploading the static assets to my bucket.

All that's left is adding in some basic configuration, and we end up with the following workflow:

    name: Hugo build and deploy

    on:
    push:
        branches: [ main ]
    pull_request:
        branches: [ main ]

    # Allows you to run this workflow manually from the Actions tab
    workflow_dispatch:

    jobs:
    build:
        runs-on: ubuntu-18.04
        steps:
        - uses: actions/checkout@v2
            with:
            submodules: true

        - name: Setup Hugo
            uses: peaceiris/actions-hugo@v2.4.13
            with:
            hugo-version: '0.80.0'

        - name: Build
            run: hugo --minify

        - name: DeployStaging
            if: ${{ github.event_name == 'pull_request' }}
            uses: google-github-actions/upload-cloud-storage@main
            with:
            credentials: ${{ secrets.GCLOUD_SA_KEY }}
            path: ./public
            destination: iancrosbytest-staging
        
        - name: DeployProd
            if: ${{ github.event_name == 'push' }}
            uses: google-github-actions/upload-cloud-storage@main
            with:
            credentials: ${{ secrets.GCLOUD_SA_KEY }}
            path: ./public
            destination: iancrosbytest

_*Note I also added a deploy to staging which is triggered by PRs._

Other steps:

Creating a service account to allow access for pushing to the Google Cloud Storage bucket.

    gcloud iam service-accounts create github-deploy-site \
    --description="Used for deploying static assets to cloud storage bucket" \
    --display-name="github-deploy"

Then we grant the required permissions:

    gcloud projects add-iam-policy-binding iancrosby-ca 
        --member="serviceAccount:github-deploy-site@iancrosby-ca.iam.gserviceaccount.com" \
        --role="roles/storage.objectAdmin"

And finally, we create the key which we can then store as a secret for our GitHub Action:

    gcloud iam service-accounts keys create ~/temp-key.json \
        --iam-account github-deploy-site@iancrosby-ca.iam.gserviceaccount.com
