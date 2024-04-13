+++
author = "Ian Crosby"
title = "DevOps, the Sec is silent"
date = "2022-01-31"
description = "Why Security has always been a part of DevOps."
categories = [
    "cloud",
]
featured = true
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

** originally published on Container Solution's blog @ https://blog.container-solutions.com/devsecops **

There are two hard problems in tech: cache invalidation, naming things, and off by one errors. We have proven this over and over again through a multitude of poorly named things. Whether it’s AWS Services called things like Athena, Cloud9, Snowball, and Snowmobile, the over exploitation of Greek nautical words, or my personal pet peeve, “The Cloud”, we are, not to put too fine a point on it, utterly shit at names.
Most often a bad name is harmless, or at worst a minor annoyance, but sometimes a term can have adverse consequences. Buzzword de jour DevSecOps is one those terms I personally take exception to—it sets up false expectations and, being a buzzword, lacks nuance.

What makes this worse is that the central idea—summed up by Michelle Ribeiro in her forthcoming O’Reilly book “Learning DevSecOps” as “to have development, security, and operations teams working together to create business value through the fast delivery of secure software using a process of continuous security”—is laudable, but the key DevOps concept of shared ownership already includes Security. Or, at least, it should.

The Sec is Silent
Whilst you can get a hundred definitions of DevOps by asking 99 people, you’d be at fault if you didn’t include security in a definition of what fully implemented DevOps entails.

The term DevSecOps implies that Security is separate, a third pillar. In such a case, why does it stop at Security? What about Observability? What about Resiliency? Flexibility? Scalability? In that sense the “Revolutionary Model of Software Development” from Emily Freeman, which has each of these as joint responsibilities, does a much better job of explaining how these various areas should be integrated.

At least as frustrating is the term “Shifting Left on Security”. Unless you are operating in a traditional waterfall model, the concept of shifting left is nonsensical. Where is left? What is happening over there?

The original concept of shifting left, with regards to testing, goes back to 2001. Back then most of us were indeed operating in a waterfall model, but reusing this nomenclature today is problematic. As we start to shift everything left (testing, security, observability, etc) we’re adding more gates between the business of writing software and actually getting it deployed.

This matters because it gives us the wrong mental model. We want to make it as easy as possible to deliver value. These are not stages we need to pass through in order to do so, but rather are considerations which should be included in all aspects and by everyone involved in the software delivery process.

DevAiSecBizObsMLOps
A further issue is that tech terms are often created, or quickly co-opted, by companies trying to push forward their own agenda—. a constant source of annoyance in the tech industry. As a new term gains popularity, it is quickly grasped by any company that can claim even minor semblance to their product, spending vast piles of marketing dollars to deliberately seed confusion in the marketplace. The more vague or ambiguous a term the worse it gets. Consider observability; how confident are you that you know the difference between an observability tool and a traditional APM monitoring tool?

DevSecOps was the first of the XXOps variants, of which we have seen many, very few of which are relevant.

Not all Bad
Rant aside, there are some honest aims and positive results which have come out of the “DevSecOps” movement. Security has long held a problematic role in software development. From my experience most organisations seem to fall into one of the two extremes when it comes to applying security

The Greek Oracle—anyone who has worked for or with any large enterprise company has experienced the pains of dealing with the mysterious security team. Often unseen and unnamed, only accessible by an obscure ticketing system or physical telephone, the security team holds extreme power. They will deem a technology, product feature or service as worthy or unworthy, through a convoluted process intended to confuse. They appear to be beholden to no one, existing merely to frustrate. When rejecting a solution they rarely give any sort of explanation, expecting you to simply accept their decision as the final word
The Cowboy—commonly found in startups, the cowboy has adopted the famous Zuckerburg mantra of “Move fast and break things” where ‘things’ includes customers’ trust and government regulations. Security is at best an afterthought, but more commonly a ‘neverthought’. Anything which may slow down the churn out of features is discarded, and security is the first to go. The argument is often used that it will be added in later, but in practice this almost never happens as back-filling security is always extremely costly, and extraordinarily technically challenging.
Moreover the focus on security, whether it’s through bad terminology or because of the latest high profile leak, has resulted in more interest and education on security. We are moving away from security being the sole responsibility of a single team (or person!) and towards a world where everyone is aware of and responsible for the security of their app/platform/service.

The Cloud - Not Secure by Default
There is good reason for the renewed focus on security, specifically in respect to DevOps and Cloud. There has been an exponential growth in terms of technology and opportunity since 2006, when vendors like Google and Amazon began using “cloud computing” to describe people accessing software, computer power, and files over the Web instead of on their desktops.

But the cloud is not secure by default. Cloud Native environments tend to be highly complex. From a software point of view they include things like containers, microservices, service meshes, and declarative APIs. Many of our existing security tools and approaches simply don’t work in the new environment even though the problems they were designed to solve still exist.

The issue is even worse in multi-cloud environments, whether as a result of mergers and acquisitions or through deliberate choices. As a recent McKinsey report noted, “The enterprise perimeter has changed in recent years as the paths to access data assets has soared, with no single perimeter existing. The influx of IT functions hosting on-premises, private- and public-cloud environments is upon us. As a result, multi- and hybrid-cloud security will continue to be critical, and CISOs will be willing to pay for increasingly hard-to-find skills (such as mainframe security) from a service provider.”

But, to coin a phrase, WTF is DevSecOps really? Speaking at QCon London in 2019, Guy Podjarny gave a fantastic definition. It is worth taking the time to watch the talk in full but to summarize, Podjarny stated that DevOps has three key pillars, which are, in rough order of evolution:

DevOps technologies (containers, cloud, serverless etc)
DevOps methodologies (microservices, continuous integration)
DevOps shared ownership (making it everyone’s responsibility to operate the software and ensure quality; WTF readers might think of this more broadly as culture).
Following on from that, in practical terms, DevSecOps simply means:

Securing DevOps technologies: adapting existing security tools to these new tech stacks, finding the new risks that they introduce, and doing something about them.
Security in DevOps methodologies: tapping into the opportunities the new methodologies present for security (for example using CI to apply security policies in our development process, applying processes such as GitOps.)
Including security in DevOps shared ownership: finding the right means to get developers to embrace security.

Crucially, for developers to take on more responsibility for security we need to provide tools aimed at developers rather than security professionals, and provide educational material to match it.

Conclusion
I’m not going to hold on to hope that the term DevSecOps will go away. At this point it has been ingrained too far into too many company’s OKRs. And I don’t look forward to fighting the ever growing list of security focused cloud companies. DevSecOps is, for better or worse, with us to stay. At least until the next poorly named trend comes along…

In fact, I grudgingly believe that more good than harm has resulted from “Shifting Left on Security” and “DevSecOps”. So while I will continue to grumble at imperfect naming and wrongly used terms, I am not-so- secretly happy that the discussions are happening and the focus continues to grow.