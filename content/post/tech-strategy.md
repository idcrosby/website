+++
author = "Ian Crosby"
title = "What is a tech strategy?"
date = "2021-04-30"
featured = true
description = "A guide for how to define your tech strategy."
categories = [
    "cloud",
    "test",
]
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

A few years back I embarked on a dream project. The client contacted us to design and build a greenfield Cloud Native platform. They had a new and exciting hardware device that was going to collect lots (lots!) of data and solve a myriad of really interesting problems. They had the domain and the hardware expertise, and what they needed from us was the knowledge and skills to build the required Cloud Native platform.

As I mentioned, a dream project. Cutting-edge technology, machine learning, big data, and the opportunity to design and build a fully Cloud Native platform from scratch. Over the next few months, that’s exactly what we did. Microservices, containers, event driven, Kubernetes, high availability. It was beautiful.

The warning signs started coming in as we tried to pin down which one of the hundreds of potential use cases we would tackle first. Priorities and focus began shifting rapidly. Finally, our client came to us with “good news”: they’d found an actual customer for this platform. Could we run the system on a single server in their building, which was not allowed to have an internet connection…?

Our “perfect architecture” was useless. And it was no fault of the client. They asked for a modern,  Cloud Native system, but that’s not what they needed. We hadn’t aligned with their business goals. We never dug in deep enough to learn what they really were.

And that is just one example of why you need a tech strategy before you build. 

What a tech strategy is—and isn’t
A technical strategy is a crucial part of any business. While you’d be hard pressed to find someone who disagrees with that statement, if you ask around you will get many different answers to the question, WTF is a tech strategy?

Strategy in itself is an often misunderstood or misused term. On top of that, in the tech world where things move at a fast pace, it can be tempting to skip the hard work of defining your actual strategy, and rely on duplicating the technologies, choices, and approaches of others, perhaps mimicking the top tech firms like Google, Netflix, etc. (This is known as meme copying,  or a “me too” strategy.) This may seem like a logical approach: if another company shows success with a certain set of technologies, then shouldn’t it work for us as well? But in doing so we are making a serious mistake and skipping the first, and most essential, part of a tech strategy.

Why do I need one?
“If you don't know where you are going, you will probably end up somewhere else.” 

— Laurence J. Peter, educator and "hierarchiologist" 

Before embarking on defining a technical strategy, or any task for that matter, it’s useful to understand why you are doing so. There are three main goals behind creating a strategy:

Alignment. A well-defined tech strategy is the best way to ensure everyone is on the same page. We often think we are all in agreement on where we are going and why, but once we start to define it we realise each has their own interpretation.
Focus and direction. A strategy gives clarity on what we are doing, and just as importantly what we aren’t. It should be communicated and available to everyone as a constant reference. Not just for those implementing the strategy, but to all stakeholders. 
Enable autonomy and distributed decision making. We hire smart people and pay them significantly. We want them to be able to make decisions and progress independently. However autonomy without guidance leads to chaos. A clear strategy gives the right level of direction to teams while leaving room for creativity.
So WTF is it?
The simplest way to explain a tech strategy is “it defines how you will leverage technology to support your business goals”. Now, this of course presumes that you already have an overall strategy and have identified what your business goals are. If that’s not the case, you’ve got bigger problems than having to worry about putting your tech strategy together.

With those business goals as a starting point, your tech strategy should identify which technology patterns will best help you overcome the challenges and realise the business objectives. It needs to be high level enough that you leave room for decisions and adjustment in the implementation. But it also must be specific enough that it gives a clear direction and is unambiguous, so that different teams don’t end up interpreting your strategy in different ways. 

Tech strategy components
Based on author Richard Rumelt’s definition of strategy in his book Good Strategy / Bad Strategy, you should have three core pieces (what he calls the “kernel”) that make up your strategy.

The diagnosis. What is the essential or main challenge that you are facing?
The guiding policy. What is your overall approach to solving the above challenge?
Coherent actions. A list of initial, specific, short-term actions your organisation or team can take.
The diagnosis can be technical, but again, it must flow from the business goals. For example, imagine an enterprise software company that has a business goal to reduce the time to deliver value. The organisation is currently shipping new releases every six months, and have determined it must be able to release features and fixes daily to satisfy its clients and stay competitive.

If you are part of that organisation, you conduct an analysis of your current tech stack and processes. You identify the biggest impediment to achieving this goal; your diagnosis is the software’s complex and tightly coupled (monolithic) architecture, where even tiny bug fixes take weeks to deploy, because of the complicated code base, unknown dependencies, and time-consuming testing.

Next, the guiding policy must be defined. This should give a clear direction for how you are solving the problem. Whenever there are debates or discussions down the line, referring to the guiding policy should help decide on which is the best approach.  Coming back to our (simplified) example above, the guiding policy in this case may be to “enable team autonomy while embracing automation”. Such a policy could lead to migrating the architecture to smaller, decoupled services which are owned by a single team.

Finally, we want to define coherent actions. This is where we get specific. What are the first, concrete tasks that will be carried out to begin execution of our strategy? 

Bad tech strategy
Bad tech strategies come in many forms. I have seen many, and have built a few myself. From my own experience, these are the most common forms of bad tech strategy:

Not aligning with the business
The primary cause of a bad tech strategy, as I alluded to earlier, is not aligning with your business goals. It doesn’t matter how elegant an architecture you design, or modern the technologies you are using. If what you are building does not support the goals your organisation is trying to achieve, you are building the wrong thing. In such situations, having modern Cloud Native tools and practices in place will only help you build the wrong thing faster. Which doesn’t really help much.

There is no such thing as the right architecture, or the ideal tech stack. It depends on your use case. What are you building? What are your constraints? Who are your users? 

Following trends
Something we are often guilty of in the tech industry is an attraction to the new and shiny. We read a blog or watch a conference talk about the latest technologies, and how one of the FAANG (Facebook, Amazon, Apple, Netflix and Alphabet/Google) companies is leveraging it to significant benefit. We want to follow the industry trends and worry about our tech stack being seen as legacy. But few of us run at Netflix scale, so do we really need the same technologies as them? 

This approach carries obvious risk. It’s a pattern we have seen more than once: a difficult and expensive migration to a new technology stack or platform, and upon completion, you are no better off (usually worse) than when you started. On top of that, you now have lock-in: You’re tied to a specific technology, beholden to a vendor contract perhaps, and you can’t easily get free of the relationship.

Even in the case where you have correctly identified a technology that solves your specific challenges, your strategy should be framed around those challenges rather than the specific tech. Otherwise, you risk losing track of your original motivation. 

Solving non-existent problems
Another common pitfall that companies run into when developing their technology strategy is trying to solve a problem they don’t actually have. This usually takes the form of pre-optimisation—i.e., addressing a problem you expect to have in the future, or having an incorrect/incomplete view of your current system and the challenges within it. The latter is an easier mistake to correct.

To ensure you have an accurate view of what your current challenges are, it’s essential to do the necessary analysis. Some exercises that are really helpful here include Value Stream Mapping. 

For example, if you want to reduce the time it takes to get a new product feature from idea to production, a common place to look for improvements is your build pipeline. Maybe by introducing some clever techniques you can reduce software build time by half! That seems like an enormous gain, but what if your build then gets deployed to a staging environment, where the QA team takes a week to perform manual testing? Reducing your build time in such a scenario is futile. Performing a Value Stream Mapping exercise can quickly and easily identify where you should focus your efforts.

What’s more challenging is building a strategy that solves the problems you expect to encounter further down the line. Of course, a strategy should anticipate the future, but too often we misjudge what our challenges will be tomorrow. A common example here is preemptively building for scale. 

We’d all like to believe our platforms and products will hit Netflix-like scale at some point, but that is rarely reality. Even if your traffic does significantly increase, are you confident that you will scale the right pieces? Do you already know if your problem scales horizontally or vertically? These are all difficult questions to answer in advance.

The best approach I have seen to solving this problem is to build systems that are meant to change. Evolutionary architectures, with well-defined interfaces, fully automated CI/CD pipelines, and comprehensive test coverage, are all great investments that will allow you to make the changes needed when you actually hit the challenges.

The 3-year plan
A common execution strategy amongst large, enterprise organisations is to have a group of architects sit in a room and define an entire system redesign, and come out with a three-year plan (it is always three years), which is then forced down upon the development teams to implement. Then, without exception, issues arise, deadlines slip, and like some validation of Zeno’s Dichotomy paradox, the plan never sees it to completion. 

There are many reasons why these types of plans do not work, the separation of the plan designers and the plan executors being a big one. Another important error in this approach is getting too specific, especially on such a long timescale. A strategy is not meant to define everything that is to be done. It gives you a clear goal (diagnosis), a consistent approach (guiding policy), and defines only the initial set of actions. Once those initial actions are underway, we will already have new information, which must be incorporated into our plan and help define the subsequent actions. 

Good tech strategy
One of the most challenging parts of defining a strategy is striking the right balance between direction and flexibility. If you don’t give enough direction, you end up with a mission statement. In such cases people will either choose to interpret your strategy in whichever way aligns with their thinking, or they remain motionless. Either way, that is not the result you’re looking for. However if you don’t leave room for flexibility then you rob those closest to the ground of the opportunity to make any decisions. You also don’t allow yourself to react to new information. A good strategy must be adaptive.

There are two techniques we’ve found to help strike that balance. The first is by creating a strong overarching guiding policy. This may include a list of principles. Examples could be: 

“You build it, you run it.”
“Automate everything.”
“Architect for change.”
“Leverage managed services.”
Your principles will act as a guide when choices need to be made. This leaves the room for the people closest to the action to make decisions, but provides strong guidance on which decisions align with the overall strategy. 

A good test for principles is that they can identify potential choices that would not follow the overall strategy. For example, if we take the principle “Leverage managed services”, then a choice to host our own SQL database (while running on a public cloud) would clearly be in violation of that principle.   

The second technique is having concrete, short-term actions. The further ahead in time we look, the less we know. Technology and tools will change, the industry will adjust, our market will shift, and we ourselves will gain new insights. 

The moment we are most confident in is now. This is why it makes sense for us to clearly define what actions to undertake at the beginning. However, as soon as we have begun to undertake these first steps, the landscape will change. We must leave room to adapt based on what we learn.

Feedback loops
We’ve highlighted how crucial it is for a technical strategy to be derived from business goals. However, this is often not a one-way street. It is also possible, and often desirable, for the technology to steer the business. 

Technology determines what’s possible. When putting together the overall business strategy, you will take into consideration what is technically feasible. For example, a company looking to develop a remote driving system would require extremely low latency. Previously this would not have been possible, but with the introduction of 5G networks, it becomes possible. The tech landscape changes quickly. When new information, tooling, or technology becomes available, this information should be fed back into your initial goals.

With a modern Cloud Native system, we can gain critical insights into our product and our users. By leveraging deployment techniques, such as A/B testing, feature flags, and advanced metrics through distributed tracing and observability platforms, we can learn a lot. Running experiments becomes cheap and easy. These insights should also be regularly fed back to the business to potentially adjust the direction.

Conclusion
Having a solid tech strategy is important for every company. It can be the differentiating factor in an extremely competitive market.

Building a good tech strategy is hard work. It requires making difficult decisions, and trade-offs. It can be very tempting to simply look at what others have done successfully and copy from that. While it’s important to draw lessons from what others have done, you will not find another organisation with the same challenges, history, goals, and constraints as yours. 

A tech strategy is much more than the technologies being used. A strategy must start with the specific challenges you are facing. What are the problems you are trying to solve? Once you have that defined, you can move on to identifying your guiding policy, and the specific actions you will take in the short term.  Your organisational culture also plays a crucial role, as IBM’s Holly Cummins argued previously in a WTF Is Cloud Native? blog post.

There are many pitfalls in putting together a tech strategy. But if you stick to the key components, align with your business goals, and allow for flexibility, you have a good chance of coming out ahead.