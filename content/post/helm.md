+++
author = "Ian Crosby"
title = "Delivering Kubernetes Native Applications with Helm"
date = "2018-06-29"
description = "Delivering Kubernetes Native Applications with Helm"
categories = [
    "cloud",
]
featured = true
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

_originally published on Container Solution's blog @ https://blog.container-solutions.com/delivering-kubernetes-native-applications-with-helm _

Last week, at the GOTO Conference Amsterdam, I gave a talk on how Kubernetes is in the process of crossing The Chasm. As in, the notable (and perilous) gap that exists in the Technology Adoption Lifecycle spectrum between early adopters -- who are willing to invest sweat equity in new/developing technologies -- and mainstream users looking for a turn-key solution with a mature feature set and tooling. Kubernetes is at a critical crossover point and my talk explores the factors indicating if it will successfully complete its jump to the mainstream.

Kubernetes is becoming a widespread commodity, and with it comes an increasingly robust ecosystem of products and tooling. But the wider Kubernetes spreads, the broader the spectrum of use cases people will try to apply it to.

Recently I worked with a Container Solutions client who, like many others, were entering a cloud native migration. The one catch in their case being that they do not host their own applications. They need to deliver software to their customers. I had not encountered this before. Previously we had dealt mostly with organisations who hosted their own software, e.g SaaS. This new client, however, presented a new challenge.

So this was my first time seeing this use case, but I knew it would not be the last. And it presented fundamental questions: How do you deliver software if you are building a distributed microservices system or application, specifically built to run on top of Kubernetes?  What does it look like to deliver this product to your clients, if you need to ship them software and that software has to run on top of K8s?

The ideal, when splitting a giant monolith into microservices, is to draw these nice boundaries and put in all this great tooling -- but this was a new complication. How does this newly cloud native entity then, post-migration,  deliver their product to customers?

We identified four possible responses to the problem.

Ship a cluster to them
Set up cluster for them, and maintain it, as a service
Make it a requirement for the client to have their own K8s cluster in place, that they would then maintain.
Tell them, sorry, the ecosystem doesn’t support this kind of model where you have to deliver services, so you can’t join the club.  
Options one (trying to ship a cluster in a box) and two (set up/host the cluster for them) were not ideal. These solutions would not scale for the one hosting, and furthermore would not be acceptable for most enterprise companies. They need to have security and control of their own internal assets, and also this would likely breach GDPR requirements for hosting your own data. Option four of course is not one we wanted to deliver, either. We have to be open and can’t give bad advice, so if that was the case we would have to greatly reduce services or try to come up with other things. But as cloud native evolves, these are the challenges that will arise -- and, if they are not solvable, then there is a chance that Kubernetes will never be able to be cross the chasm.

So we selected option three, making Kubernetes a requirement. It was a decision not only for this client, but a new paradigm being established with this new model: Kubernetes becomes the OS. Ultimately, we decided, it’s OK to put this as a requirement because the idea is Kubernetes will become ubiquitous and widespread, is right now in the process of becoming so.

“Vanilla” Kubernetes is difficult to digest
If the solution is that we require Kubernetes,  the clients will need help initially setting up their own cluster. Ideally, this should hide the complexity -- they don’t need to know how it works, we just want it to work for them. However there was still the difficulty that “vanilla” Kubernetes applications can have dozens upon dozens of configuration files, with no logic between them. So how do we actually send our application to them, now that they have their own cluster to run this on, how do we still somehow deliver them our software?

Fortunately, there is a comprehensive, and nicely packaged, solution.

At the Helm
Helm, the Kubernetes package manager, was the missing piece. Helm is not included as part of K8s itself, but came from the open source community around K8s. Helm’s creation was driven in response to demand, as people started to see the need for things like templating and  package management.

The software was created in 2015 by Matt Butcher and  Jason Hansen, and a company, Deis, was reorganized shortly after the release to support the software and build out additional tools. Microsoft purchased Deis in 2017, and just this month the Cloud Native Computing Foundation’s technical oversight committee voted to accept the Helm package manager as an incubation-level hosted project.  Which only makes sense, given that an estimated 64 percent of Kubernetes users deploy Helm, according to a recent CNCF survey.

Helm allows the packaging of applications as Kubernetes charts, while simultaneously enabling the applications themselves to be consistently set up across different K8s deployments. It handles all dependencies; if, for example, there is a specific order required when creating resources, this logic can be built into Helm. Configuration is all in a single place, too -- there may be dozens of different pieces of the system application, but only one place the user needs to go to configure it all.

The software also makes it possible to have lifecycle hooks. If, say, something needs to happen before install, or a script needs to run before upgrade, we can inject these specific database migrations or any kind of cleanup that needs to happen. All that becomes automated. Helm also handles upgrades and revisions, even in different versions of an application. It can do very smooth upgrades and rollbacks as well, when required.

And you can deploy and upgrade with a single standard Helm command -- since all this is not in your application, but rather sits outside and manages it for you. Which is nice for us too, since we don’t have to worry about building it into our own client-specific solutions. Helm’s standard implementation is agnostic across all implementations.

The Bridge Ahead
Even as robust new tools like Helm emerge in the ecosystem, there is still some risk involved when tying your software delivery process to Kubernetes. The biggest risk? That you are making a bit of a gamble these will be THE technologies of the future. If you tie yourself to this now, and it turns out to not cross the chasm, you have set yourself up for potential failure...or at least a lot of rework down the road.  

The same risk is inherent in any new technology, however, and we at Container Solutions are confident in advising this particular road. This is Kubernetes’ chasm moment, and Helm is helping to build a bridge across the chasm.