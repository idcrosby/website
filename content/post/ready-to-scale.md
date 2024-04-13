+++
author = "Ian Crosby"
title = "Preparing to scale"
date = "2020-04-09"
description = "A case study."
categories = [
    "cloud",
]
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

** originally published on Container Solution's blog @ https://blog.container-solutions.com/case-study-a-company-gets-ready-to-scale **

QOMPLX, an intelligent-decision platform provider, offers data handling, analytics, reporting, and advanced algorithms. The company, celebrating its fifth year in business, finds itself in the midst of a growth phase. It’s onboarding more clients and working to stay ahead of its explosive growth curve.  

PSscaleup

The Northern Virginia company’s current products focus on cybersecurity, insurance underwriting, and quantitative finance, and are built on top of a shared analytics infrastructure.

The focus for QOMPLX's Platform Experience team is to continue to mature the stability, reliability, and scalability of the platform while also preparing to grow quickly. 

To help prepare for the company’s next phase, QOMPLX asked Container Solutions to conduct a Cloud Native Assessment. Our assessments, usually conducted over two or three days, evaluate an organization’s current state of Cloud Native maturity, from its infrastructure and tooling to the related processes and structures that support its business activities.

The assessment, which concludes with a visualization on a Cloud Native Maturity Matrix of how the client is faring in nine categories, focuses on identifying the main challenges to achieving the client’s goals. It also identifies future risks and how to mitigate them. 

A Cloud Native Assessment is the first step in Container Solutions' four-step method for Cloud Native transformation: Think, Design, Build, Run. The method, developed over years of experience with companies in a variety of industries, helps our customers reduce risk, eliminate wrong moves, and deliver value to their own customers faster.

Ultimately, we worked with the QOMPLX Platform Experience team for two weeks. Following the assessment, Container Solutions and the QOMPLX team built a working proof of concept (PoC), to mitigate some of the biggest risks they will face as they mature their platform.  This included expanded use of Kubernetes as the primary container orchestration platform.

Through the assessment and PoC with the team, we came up with an approach to update QOMPLX in an iterative fashion, with no downtime. Here’s what happened.

## Building a Case for Change

The most important question to ask at the start with any project is ‘why?’.  Even if the reasons and goals of a project seem evident, it’s crucial to define them. This is a Cloud Native pattern we call ‘Business Case’ This helps to avoid vanity projects, and to align the group. (This and other patterns can be found in our new book, Cloud Native Transformation.)


PSbusinesscase

QOMPLX’s engineering culture focuses on three primary pillars: stability, scalability, and security. Having quickly grown and developed its core product, the company was rapidly growing, through major traction in the market. Its decision makers knew that to prepare for the increased growth, both in clients and products, they would need to focus on the stability and scalability of their core platform.  QOMPLX had already decided to build its case for change by engaging with Container Solutions.

We quickly onboarded a project with the QOMPLX Platform Experience team to assess, map, and guide the team through its journey.

## ‘Strangling’ an Old System

The days of the ‘three-year plan’ for building and deploying a new architecture/system are gone. Not that such plans ever worked in the first place. The goal behind Cloud Native architecture is continuous, incremental improvements.

Our recommendation for QOMPLX was that it execute  its roadmap in a gradual fashion: focusing on components, one at a time, to implement our recommendations along with the company’s own roadmap features.

Equally important, we want to accomplish this with the least amount of impact on the existing system and teams as possible. Therefore, at QOMPLX we opted to use the Strangler Pattern. Normally used as a way to migrate from monolith to microservices, it can be equally useful in our case. 

PSstrangle

As we modify each component from the old to the new pattern, a ‘facade’ service is used, which replaces the original interface and routes the traffic appropriately. With this approach, the calling services are blissfully unaware of the changes abstracted behind the interface contract.

Additionally, the facade service provides additional control on the traffic routing, enabling design patterns like canary deployments, gradually increasing the traffic to the new service, validating each migrated component, and collecting metrics in order to ensure the older versions are no longer receiving traffic before they are removed.

## Migrating Culture

Cloud Native is about more than the technologies you use. One of the main goals of our Cloud Native Assessment is to look at all aspects of an organization—from processes, to team structure, to culture.

At QOMPLX, the engineering teams were looking to address reactive spikes in their operations, which naturally comes during all phases of product consumption growth. The ‘hustle’ culture can be efficient in the short term, but when looking to scale, a change in mindset is required. We helped the company’s engineers focus on maturing their tooling so that additional automation could both free time and standardize tasks (tests, deployments, etc.).

## A Small Experiment

For our proof of concept at QOMPLX, we had a few concrete goals:

* Validate the hypothesis that running the system across multiple platforms was feasible.
* Provide an example for migrating services one at a time.
* Create a template and best practices for future applications.
 

In order to achieve these goals, we set up a Kubernetes cluster (EKS and Terraform) and deployed a crucial service onto the cluster. Our goal in a PoC is to lower risk, which is why we decided to focus on a critical component. If the migration works for this one, we can be more confident when it comes to moving the rest. (Note that, when performing the actual migration, organizations will want to start with something less critical, though they can be confident that the risk has already been removed.)

Once we validated that the application is functioning on the cluster, we deployed our facade service to the cluster and re-routed traffic from the old service to the new one. Thus, we verified that the entire system continues to function across both clusters.

## Next Steps for QOMPLX?

After the successful proof of concept, the QOMPLX team will start to move forward with the migration of their remaining services. The next step is to triage each component. There are three options for each:

* Rehost: Components that can be migrated directly to the new system without any significant changes.
* Refactor: Services that require a partial rewrite before they can be moved over. They may have hard dependencies on the previous infrastructure.
* Remain: If rehosting or refactoring is not viable or possible, components can be left on the old platform. The end result for these pieces are to be retired or replaced eventually.
 

Once all components have been triaged, they must be prioritized to determine the order in which they should be tackled. Priority would be given to pieces that change frequently and those that are easy to extract. The things that are stable and not changing are left behind on the old platform and moved over last. This pattern, we call Lift and Shift at the End. 

PSliftandshift

## Summing Up

Setting up for growth is not a trivial task. It requires both technical investment as well as revisiting your processes and culture. Cloud Native transformation projects such as these get increasingly complex (pun intended). 

Breaking these projects down into the four phases—Think, Design, Build, Run—gives us a structure for tackling such large problems. An initial assessment of the landscape, challenges and goals (Think), followed by a small, well scoped proof of concept (Design) enables us to bring down the risk and determine a clear path forward, which can then be implemented (Build), maintained  and scaled (Run).

Companies like QOMPLX are pushing the envelope on what’s possible, while also enlisting external experts to help them navigate their journey.