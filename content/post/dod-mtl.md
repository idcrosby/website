+++
author = "Ian Crosby"
title = "What we learned at DevOpsDays Montreal"
date = "2019-11-19"
description = "Recap of DevOpsDays Montreal"
categories = [
    "cloud",
]
featured = true
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

_originally published on Container Solution's blog @ https://blog.container-solutions.com/what-we-learned-at-devops-days-montreal-spoiler-a-lot _

Community has always been a huge part of Container Solutions, from meetups to workshops to conferences. When we launched our new office in Montreal last year, we were eager to join in the local community by participating in events. So we co-sponsored last year’s DevOps Days Montreal. Earlier this month, we did it again. 


A good line-up of speakers took to the stage over the two days, covering a wide array of topics from DevSecOps, to career development and the legal implications of open-source licenses. In true Montreal style, presentations were done in French and English, with questions and discussions switching back and forth between the two.


Open Source Under Attack
Richard Fontana, senior commercial counsel at RedHat, gave an opening keynote that dove into the timely topic of legal implications of open source. He spoke about an ongoing ‘multi-front attack’ on the definition of open source. In many cases, he said, these new challengers ‘want to expand the meaning of open source to bring in more restrictive licensing terms . . . to add restrictions that historically weren’t part of open source.’

Some companies are adjusting their open-source licenses to help freeze out business competition, Fontana said.

But one area from which the attacks are coming is the ‘Ethical Source’ movement, he said, led by developers, particularly young developers, who object to the use of open-source software for what they see as bad purposes. So, they enumerate restrictions as part of their open-source licenses, such as that the software cannot be used for the manufacture of weapons or sale of tobacco, or in violation of human-rights treaties.

Fontana defended the historic definition of open source, saying that restrictive licenses violate the original intent of having a public ‘commons’ of shared knowledge. ‘Using the right to exclude to introduce restrictions that historically would not have been tolerated in open source should be resisted, in my opinion. Or if we want to accommodate, these licenses should not get the open source label.’

He concluded, ‘Private software licenses are ill-suited to achieving public, social, and political goals not specifically tied to software development.’


Bringing DevOps to a Research Team
Catherine Proulx, a researcher at the National Research Council Canada who works on the convergence of gaming technology, virtual and augmented reality, and cognitive health, spoke about applying DevOps principles to research.


Researchers, she says, are most concerned with publishing their work and are competitive with each other. Her current team, which works in partnership with hospitals and medical centers, had no process for deploying its data in the beginning.

So, she said, 'I did what any developer would do: I stole a couple of hours from my project and I built a tool.' A few lines of Python later, her team had an automated way to deploy its work.

But, she learned, ‘It’s a lot harder to change a culture than to change a tool.’ To get her colleagues to use it, she told them that the tool was available—and that the only difference from the way it worked before, a method that relied heavily on Excel sheets and Post-It notes, was that each new version would be tracked by the tool. She also told them that ‘we can go back to our Excel sheets if you don’t like it.’

And so, Proulx recalled, ‘with some reluctance, people started using it.’ Gradually, she said, people began using the tool, discovering its features.

Now, she says, 'The team is feeling that they own the tools, they own the processes. And they can change them if they need to. And best of all, we’re publishing our work. We’re getting results.’

Proulx’s tips for bringing a DevOps culture to a research team:

Start with the simplest, cheapest solution you can find.
Make sure you can revert back to the old system.
Don’t try to ‘repair’ the research process.
Accept that there will be uncertainty and setbacks.
Don’t assume that your team knows what a DevOps infrastructure looks like.
GIve the team a chance to experiment—even if you know what the end should look like.
Keep your researchers’ goals in mind; they are likely not the same as yours.
 


Keeping Firmware Safe
Yannick Brosseau’s presentation on firmware (yes it still exists, even in a Cloud Native world) included lots of practical advice. Brosseau, a hardware system engineer on the Firmware Management team at Facebook, said he thinks there needs to be more open-source work done on firmware and related tooling.

He offered the following tips from his company’s system for managing firmware:

Find a common format for all firmware.
Know what version you are running in each machine.
Test your most critical application with the new firmware.
Deploy at a time when traffic is low. ‘You need to reboot any machine that you have,’ Brousseau said.
Don’t deploy to 100% of your machines at once. Start with 10% or less: ‘Make sure you get some baking time before it goes fully into production.’
 


 

In case you missed the Montreal event, all of these talks are available on the DevOpsDays YouTube channel.

Open Spaces
One of the best things at any DevOps Days conference are the Open Spaces. For anyone not familiar with this concept, the basic idea is that the conference attendees get to choose the topics they want to discuss, and are subsequently able to engage in organised discussions amongst each other.


A few highlights from the discussions in Montreal included:

Mono-repo vs Multi-repo
A topic which seems on pace to become the new ‘vim versus emacs’, participants discussed the pros and cons of using a mono-repo versus multiple repos, and specifically the impact it has on CI/CD.

Some companies use a mono-repo approach in order to have all their source code and dependencies in a single place and have it all available via a single Git clone. This technique is mainly appreciated by front-end developers who don’t want to deal with the complexity of managing a dependency tree spread across multiple projects/repositories.

But this approach has some drawbacks. A huge mono-repo can slow down CI/CD pipelines, partially caused by the coupling between each module. In case of a single isolated change, any module that depends on this one will also need to be rebuilt and repackaged. A mono-repo could also be tricky if the plan is to deploy it as microservices.

One recommendation given was to take a look at how npm, for example, deals with package management and see if it’s possible to replicate it. But does anyone really want to use npm as a model example? The debate rages on. . . .

Pull Requests: Best Practices
Here were some of the main streams of thought on this topic:

Git commits. Usually a task contains one or more Git commits, and these could be broken into one or more pull requests. The challenge here is to determine the right amount of commits that should be included in a pull request.

Commit frequency turns out to be very personal. Some people do a commit per functionality, others a commit for every batch of meaningful changes. It’s up to the developer to decide how frequently commits should be done. If many commits are done for a single task, and a task that generates a pull request, we could end up having a huge pull request with a lot of changes.

Detecting bugs. One goal of a pull request is to detect anomalies before the code is merged to the main branch. When creating a pull request, it is recommended to use automated tools to analyse code changes, output test coverage, potential bugs, code smells, and CVEs. With some tools, it is also possible to block the merging of any pull request if it does not fit the configured quality standards.

Review procedure for pull requests. Should it be pair review? Single review? Multiple reviewers? It all depends on the company and the development team. For those having senior developers in their team, usually that senior dev will be the one assigned to the pull request. Some others will prefer having a senior and a junior dev assigned to the pull request. Others will assign it to the whole team, to have the chance that their pull request will be reviewed as soon as possible

GitOps in Practice
Following an Ignite talk earlier in the day on GitOps, by Alex Gervais of Datawire, this open space had some great discussions about how companies are implementing (or planning to implement) GitOps in their teams. A wide range of tooling was discussed: ArgoCD, Flux, Flagger, Keel, and Spinnaker are all in use, with most people having reasonable success.

Other topics being kicked around: the difference between GitOps and Infrastructure as Code, and whether to adopt a push-or-pull methodology.

Monoliths to Microservices
A good discussion arose from a group of attendees who were mostly looking to get started on splitting a monolith into microservices. While the group covered some common questions, such as why they needed microservices and the barriers to migrating, the discussion moved on to focusing on cloud adoption.

Participants wrestled with whether a microservice architecture is necessary for moving to or at least fully optimising the cloud. A common misconception still seems to exist among managers. ‘The cloud’ does not equal  ‘Cloud Native’.

Closing Thoughts
Overall, it was an engaging and interactive community event, and one that we at Container Solutions look forward to being a part of again here in Montreal. It’s great to see the local DevOps community evolve and the topics that are generating interest.

For anyone who was not able to attend this year, check out the presentations online. We strongly recommend coming along for the 2020 edition!