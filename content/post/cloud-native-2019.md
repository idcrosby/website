+++
author = "Ian Crosby"
title = "Cloud Native in 2019: A look ahead"
date = "2019-01-14"
description = "Preview of Cloud Native for 2019"
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

** originally published on Container Solution's blog @ https://blog.container-solutions.com/cloud-native-in-2019-a-look-ahead **

Cloud Native has been around for a few years now, but 2018 was the year Cloud Native crossed the chasm to go truly mainstream. From the explosion in the number of projects making up the CNCF landscape, to IBM’s $34 billion purchase of Red Hat under their Hybrid Cloud division, the increasingly wide adoption of Kubernetes, capped off by CloudNativeCon in Seattle with eight thousand attendees, the past year Cloud Native became the major trend in the industry.

So then the question now is, “what will happen in 2019”?

We have seen strong indications of where the sector is heading, and how it will grow over the next year. The large surge in popularity and adoption of Cloud Native technologies such as Kubernetes has led to many new use cases. New use cases result in new challenges, which translate into new requirements and tools. If I were to pick one main theme for this year it would be security. Many of the forthcoming tools, features, products are specifically focused on addressing security concerns.

Here are a few of the trends we expect to see in the year ahead:

Cloud Native meets the Enterprise - We will see continued adoption of Kubernetes and Cloud Native tech by large enterprise companies. This will have a two-way effect. Cloud Native will continue to influence enterprise companies. They will need to adjust their culture and ways of working in order to properly leverage the technologies. From their end, enterprises will have a strong influence on shaping the future of Cloud Native. We predict a continued focus on features regarding security. An additional effect from the pressure around security and reliability will potentially lead to slowing down both speed and release cycles of some of the major projects.

The Year of Serverless (really) - We predict serverless/FaaS is finally going to live up to the hype this year. It feels like we’ve been talking about serverless for a long time already, but except for some niche use cases it hasn’t really lived up the expectations so far. Up until recently, AWS Lambda has been pretty much the only proven, production scale option. With the rise of new Kubernetes-focused tools such as KNative and promising platforms such as OpenFaas, serverless becomes much more attractive for companies who don't run on AWS (or are wary of vendor lock in).

Not Well Contained - While last year it seemed that we were headed to 'everything in a container', more recently we've seen many VM/Container hybrid technologies, such as AWS Firecracker, Google's gVisor and Kata Containers. These technologies are arising mostly for reasons around security and multi-tenancy. They offer stronger isolation while keeping performance similar to containers. We expect to see a move away from trend of running everything as a Docker container. Thanks to standardization on Open Container Initiative specifications and the Container Runtime Interface these new runtimes can be abstracted away from the applications and the developers writing them. We will continue to use Docker (or other OCI compliant) images for our applications, it will be the underlying runtimes which will likely change.

Managing state - The early use cases of Cloud Native focused heavily around stateless applications. While Kubernetes made persistent storage a first class citizen from early on, properly migrating stateful workloads to containers and Kubernetes was fraught with risks and new challenges. The ephemeral, dynamic and distributed nature of cloud native systems make the prospect of running stateful services, specifically databases, on Kubernetes worrying to say the least. This led to many to be content migrating their stateless applications, while avoiding moving over stateful services at all costs. More recently, we have seen a large increase in the number of open source tools, products and services for managing state in the cloud native world. Combined with a better understanding by the community, 2019 looks to be the year when we are comfortable running our critical stateful services on Kubernetes.

We’re excited to see what kind of surprises this year brings as well. Will Kubernetes maintain its dominance? Could a new technology come along to take away its steam? Unlikely, though not impossible as there has been considerable criticism of it’s complexity, with some more lightweight options popping up. Will unikernels finally see more adoption as we continue to focus on security and resource optimisation? Will the CNCF landscape continue exploding in size, or will we finally see a paring down of tooling and more standardization?

No matter whatever surprises that may yet pop up, we’re confident in saying Cloud Native will continue to be the major trend in IT over the next year...and many more, as CN increasingly influences how everyday enterprises run their technology for years to come.