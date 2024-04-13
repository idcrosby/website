+++
author = "Ian Crosby"
title = "You don't need Kubernetes, you need unit tests."
date = "2019-04-11"
featured = true
description = "You don't need Kubernetes, you need unit tests."
categories = [
    "cloud",
]
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

** originally published on Container Solution's blog @ https://blog.container-solutions.com/no-you-dont-need-kubernetes-you-need-unit-tests **

No, you don’t need Kubernetes, no matter how much you believe it to be the answer to all your troubles. What you actually need is unit tests. Let's look at why this is true.

## Solving the right problem

A challenge we often suffer from in tech is the idea that we can use the latest, coolest technology, to solve our current problems. If you are struggling with the stability of your platform and watch a conference talk on a case study touting the resiliency and benefits of Kubernetes, this can seem like a great fit. The problem is that within the 30 minute video clip we don’t get the full background on what came before this, and all the work that went into getting prepared for such a setup. I can personally recount numerous occasions where I rationalised introducing some new technology to solve a problem, which could have been done with a code refactor or using an existing piece of tech.

## The Request

I’ll take one example I saw recently, but this is a pattern we have seen numerous times, albeit maybe not this drastic. In this case, a client contacted us because they wanted to migrate an application to Kubernetes. Not an unusual or incorrect thing to do. When we asked about the motivations behind this, the reason they gave was to save costs. They had estimated that they could reduce their costs by leveraging Kubernetes' auto-scaling features. Again, this is not an unreasonable assumption.

We agreed to help them to build out a small proof of concept (PoC) to validate this assumption. We strongly promote the idea of experimentation and PoCs as a quick and cheap way to validate (or just as important invalidate) assumptions and reduce risk before jumping into a large, long term project.

## The Take

As we started getting into the PoC and digging into the existing code and infrastructure, many red flags started to appear. The most notable issue was a complete lack of tests. Upon digging a little we did find some tests which had been commented out to ‘fix the build’. Now, I could start throwing stones (since I have a clear view from within my glass house), but many of us have been guilty of such practices, TODOs, and FIXMEs placed in comments with the best intentions. I will simply use this as an example to illustrate my point.

Some other crucial pieces which are often missing include a consistent development environment. A single simple way for a new developer to build, run and test their code locally. If each developer is cobbling together their own custom test setup, or if everyone needs to share a single test/integration environment, this seriously slows down developers and development.

Another related item I have run into is infrastructure automation. If it takes several days to spin up a ‘production like’ environment to run a proof of concept then this is where you should be investing your effort.

## The Problems

While these are latent issues which, even the engineers of this organisation were more than painfully aware of, the resulting penalties are often less visible. Especially as this is a gradual process, which worsens over time. As externals coming in, with a specific mandate the problems are much more apparent.

If you cannot make a change to your application and *quickly* and *easily* validate that the application still works, you will be incentivised to not make changes to that application. This is the exact opposite of what we want in a Cloud Native environment. Changes should be as simple as possible to make, test and verify.

If you cannot replicate your production environment - e.g. (re)creating a production like setup to be used as testing/staging etc, spin up a local developer environment - you are missing the point of Cloud Native.

## Solutions?

In such a situation, introducing new technology is not going to solve your challenges, it will only compound the problems you already have.

It’s important to note that these weren’t bad engineers, nor were they led astray by bad managers. These issues arise in most organisations, as a result of shortcuts, time constraints, tight deadlines, and personnel changes.

There are certain hard prerequisites which must be in place before you can actually benefit from Cloud Native technologies:

* Testing - should be fully automated, have a significant coverage, but more importantly give you confidence that when your tests pass, your application works.
* CI/CD - a reliable, build pipeline which runs on every commit and tells your team if that change will work in production or not.
* Infra Automation - You should be able to spin up a brand new production like environment with a single command. Following the principles of infrastructure as code, this automation must be treated as your application code, versioned and tested in its own right.

## Building the base

These three pieces are the core of what is needed from a technical perspective before you embark on a proper Cloud Native migration. (Culture is a whole other, equally crucial aspect I am intentionally not covering here).

With these pieces in place, you can have strong confidence to make significant changes to your applications and architecture. And you should! Cloud native is not an end state. Our goal should be a proper evolutionary architecture which is designed for change.

It’s 2019, do we really not understand the value of testing?

I have yet to have anyone tell me that they have too many tests (too long, complex, slow maybe). No one is arguing that there is no value in writing tests, (or refactoring complex code, or improving a build pipeline, etc) but for some reason these tasks are never a priority. The results are not visible. The tasks themselves are not the most attractive to engineers. But the results of not having them are real.

How rampant is this?

If you recognise some of these sins in your own organisation, or code base, there is no need to be ashamed. This is much more common than we think. While we are used to seeing conference talks, reading blogs, etc., on all of the great things people are doing and the amazing setups, this is not the norm. We as an industry don’t talk enough about our failures and issues.

## /Rant

So, in order to avoid this post being simply a raving tirade, what are some practical lessons to take away?

Ensure you take care of the pre-reqs first - adoption of Cloud Native tools will be much easier, and provide many times more benefits when you have these in place. (Testing, CI/CD, Infra Automation.)

Software entropy ensures that disorder within a software system consistently increases the more we touch it. Bad code doesn’t start as bad code, but gets there over time. We must consistently make an effort to clean up and improve our existing code in parallel to adding new features to ensure that we aren’t bogged down in technical debt.

The ownership is at all levels - whether you are a developer, a sys admin, a team lead/manager, or hired-in external consultant - we are all guilty of not prioritising these pieces, and we all share the responsibility to make sure they happen.

The good news is that (at the risk of losing business) investing in these ‘basic’ pieces will be cheaper and bring more benefit than migrating your existing applications to a cloud native architecture. Of course once you’ve covered the basics you can call us to help with the fun part :)