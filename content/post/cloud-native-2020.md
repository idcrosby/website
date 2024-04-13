+++
author = "Ian Crosby"
title = "7 Cloud Native Trends for 2020"
date = "2020-01-13"
description = "Preview of Cloud Native for 2020"
categories = [
    "cloud",
]
featured = true
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

_originally published on Container Solution's blog @ https://blog.container-solutions.com/7-cloud-native-trends-to-watch-in-2020 _

As Cloud Native continues to grow in popularity, with more organisations than ever adopting the tech and all that comes with it, let’s take a look at what we are expecting to see in 2020.

Kubernetes as a technology is slowly fading into the background, as it becomes the O/S of the cloud. We predict more focus on the abstractions, tools, and platforms being built on top coming out of the constantly growing community.

Here are seven trends we are keeping an eye on in the new year:

## 1. GitOps becomes standard for Cloud Native.

One of the trends we were most excited about in 2019 was the advent of GitOps. A natural extension to Infrastructure-as-Code and Continuous Delivery, GitOps focuses on using Git as a single source of truth for your system. Changes to infrastructure and applications are made declaratively through a Git repository, with an automated process which ensures the current state of your system reflects the state in the repo. The term GitOps was coined by the folks over at Weave Works and you can read more about it on our blog.

The creation of the GitOps Engine, a collaboration between the two biggest players in the space, WeaveWorks Flux and Intuit’s Argo, shows great promise as a standard tool for implementing GitOps. Expect the space to become a bit more crowded this year as different flavors and niche use cases are catered to.

GitOps is in early stages of adoption, but we foresee it becoming a standard for all Cloud Native-aspirational companies in 2020.

## 2. Hybrid cloud is the future.

Whether you are a fan of it or not, hybrid or multi cloud looks to be the future of Cloud Native solutions. It is becoming clear that any reasonably large organisation will not run entirely on a single ‘cloud’ in the future, whether that cloud is on-premises, public or private.

For a variety of reasons—data security, disaster recovery, handling scale, data privacy—a multi or hybrid cloud solution is desirable. As a result, in the past year all three major cloud providers launched a product to support hybrid cloud (AWS Outposts, Google’s Anthose, and Azure Arc).

One of the main points of appeal of Kubernetes to many organisations is how it lends itself to a hybrid cloud setup. While this is true to some degree, as soon you span multiple clouds you invite a lot of complexity. There are some tools which aim to simplify this, Kubefed, aka Federation v2, Crossplane, or via a service mesh such as Istio.

In the coming year, we expect this space and the tools to continue to evolve, and at the same time companies looking to implement hybrid cloud setups will re-evaluate their expectations as they realize this comes with a cost.

## 3. Kubernetes must make this the Year of the Developer—or else.

One of the biggest and most consistent criticisms of Kubernetes is how it does not lend itself to developers. For the operations and platform teams, Kubernetes has been a great enabler. But often times developers feel left behind. It has added complexity to their software lifecycle, having to learn the new technologies, without adding much (visible) benefit. Having a production-like development environment remains very difficult in the world of distributed, microservice, Cloud Native applications.

We are starting to see more efforts to address this issue, from Ambassador, Draft, and Garden just to name a few. We are expecting 2020 to be the year that Kubernetes becomes developer friendly. Expect many teams to move away from K8s if this challenge is not solved.

## 4. SRE will go from buzzword to common practice.

Since Google first released ‘Site Reliability Engineering’, detailing how it runs production systems, the term and role has continued to grow rapidly. As of 2019 SRE is still emerging as a practice according to recent surveys.

Most companies are implementing SRE within their organisation, but a large number of them are not applying the correct processes and are instead simply rebranding operations teams. The same survey from Catchpoint, linked above, indicates that SLOs (Service Level Objectives) are often not defined, and there remains too much toil in the organisation— two key metrics of SRE.

As the practice continues to mature, we expect the processes to become more strict, including a thorough production review for all services and well-defined SLO/SLI/SLA, and for proper SRE to become a hard requirement for any company maintaining production systems.

## 5. ‘Remote first’ will give more companies an edge.

One aspect Container Solutions often promotes to companies is that they must become remote-work friendly. It is not only desirable to workers, but it forces best practices in terms of communication and autonomy. (Just under 32 percent of people who participated in Stack Overflow’s annual developer survey in 2019 said the chance to work remotely was most important to them in choosing a job.)

The tools and practices that are required to support remote work are beneficial regardless of whether you have remote workers. (We practise what we preach: We have not only seven offices across Europe and Canada but also lots of people who work fully or mostly remote.)

What does this have to do with Cloud Native? As we have written about previously, Cloud Native is about more than just technology. From a Conway’s Law perspective, if we are building large scale distributed systems with clear, declarative interfaces, we should look to implement the same things into our organizational structure.

As the push for remote work continues, we expect companies that offer a remote-first approach to have a significant advantage over their competitors.

## 6. MLOps opens new opportunities.

While not necessarily falling under the Cloud Native umbrella, the introduction of MLOps in 2019 is an exciting development. MLOps is the process of operationalising and managing the lifecycle of machine learning in production, essentially applying the tools and practices of DevOps to the domain of data science.

We see this as the bridge between machine learning and Cloud Native, allowing data science and ML teams to leverage Cloud Native practices and technologies. The opportunity here is tremendous, and we are expecting this space to really explode in the next year.

## 7. Debates about ethics will grow louder and more urgent.

For the past few years, concerns about ethics and technology have taken center stage, from companies’ use of data to the energy consumption by data centres. We believe that these are important conversations. From a Cloud Native perspective, we see more discussions ahead in 2020 on which companies we should support (or not), how we can help reduce carbon footprint, and more.

## Conclusion

While Cloud Native technology itself becomes more and more mainstream, the space is only evolving faster. Adoption of the major technologies such as Kubernetes continues to expand, which results in the need for additional abstractions and tooling. These are a few of the items we’re keeping an eye on for this year, but we’re even more excited about the unknown areas which will surely arise in 2020.