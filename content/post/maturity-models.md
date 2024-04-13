+++
author = "Ian Crosby"
title = "In Defence of Maturity Models"
date = "2019-05-08"
description = "In Defence of Maturity Models"
categories = [
    "cloud",
]
featured = true
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

** originally published on Container Solution's blog @ https://blog.container-solutions.com/in-defense-of-maturity-models **

Maturity models have received criticism for nearly as long as they’ve been around.  In my experience this has more to do with how they are used rather than any inherent fault with maturity models in general. As with any tool, it is when and how we decided to use it that matters most.

Let’s take a look at some of the recent criticisms and address them one by one. We’ll try to understand where the models fall short and where they can provide value. First off, a very brief intro to maturity models.

## A (very) Brief History of Maturity Models

Maturity models in general are not a new concept. We can trace them back to Maslow’s hierarchy of human needs. Developed by Abraham Maslow in 1943, it is a theory in psychology describing the levels* through which human motivations progress. Still widely in use today, Maslov’s pyramid, as it’s often called, demonstrates the benefits of a simple model used to explain a complex topic.

Within the IT world, the first major appearance of a maturity model is the Software Engineering Institute’s Capability Maturity Model in 1993. This framework was originally meant as a tool of the US DoD (Department of Defense) to evaluate government contractors. Since being published openly, it has been used to help organisations improve their software processes. The model proved highly successful and, as a result, has led to an explosion in maturity models throughout our industry. With quantity comes variety: there have been some good models created, but also some poor ones.  

 

Maslow’s Pyramid
 

The main goal of maturity models is to describe the maturation path and the different stages along which one should progress. Each stage needs to be well defined, along with the relationship between the stages. When put to use, maturity models identify both the current state and the desired state. They should also offer measures to progress along the maturation path.

## The Problem(s) with Maturity Models

As mentioned earlier, denouncing maturity models is nothing new. Recently there has been some criticism from some very solid sources, including the recent book Accelerate by Nicole Forsgren, Jez Humble, and Gene Kim. (If you haven’t read it, then I highly recommend doing so). Another source of criticism has been from people promoting Wardley Mapping, who point out that traditional maturity models often lack context and fail to provide an order for undertaking their recommended steps. In reading this recent criticism I was conflicted. There are some valid points from people in the industry I highly respect, such as: maturity models oversimplifying reality or assuming a one-size-fits-all progression path. I completely agree that every organization has unique circumstances, challenges and needs. How could we possibly put them all into the same maturity model mould?

When we built our own maturity model at Container Solutions we made sure to consider these very valid criticisms. When working with client organisations we regularly use our own Cloud Native Maturity Matrix to map their current maturity, identify gap analysis, and discern where they should focus their efforts in order to reap the most benefits. This is a model which has proved very useful for our clients.

This post, then, is an attempt to talk about the major concerns with typical maturity models and identify where they struggle and often fail. Then we will look at how we attempted to address these concerns as we built the CS Maturity Matrix -- and make the argument that, when used appropriately, maturity models can be very useful.

 
I’ve attempted to summarize the main complaints I’ve seen with regards to maturity models, and how we’ve specifically tried to address them.

## Maturity models oversimplify reality.

This is a valid complaint and is a real problem with most maturity models. Specifically by mapping complex organisational structures to a linear model. This is a common challenge for any model. Simplifying without oversimplifying.

This was something we at Container Solutions were acutely aware of when trying to create our own maturity model. Which is why we ended up with a maturity matrix. While not completely solving the problem of over-simplification, it provides us with three key benefits:

1. By adding a second dimension, we are able to capture much more variation which exists in different organisations in such a complex environment.
2. We are able to show the correlation across different areas. The most important message to get across when discussing IT transformations in my opinion is that this is about far more than tooling or technology. Our maturity matrix has proven a great way to explain the connection between culture and technology (see Figure 3 below).
3. Once the current maturity and desired maturity are identified via the model, the model itself identifies where effort should be placed in order to benefit the most. Specifically since we want to mature all rows at a similar rate, it is the one which currently lags behind which should be addressed first.

**mm_diagram**

Figure 3: The CS Cloud Native Maturity Matrix with Gap Analysis

## Maturity Models assume a single path.

Most maturity models I have seen (including ours) only offer a single path of maturity -- thus giving the impression that there is only one road to take for all organisations. It would be foolish to assume that all organisations will progress the same way.

Our belief is that maturity models should not be about moving through stages, but rather to show a consistent vision or transformation goals and to understand the current state. For example, if you are currently in ‘waterfall’ stage, you don't necessarily need to set up agile first, but can go directly to Cloud Native. What is important is that you may need different activities depending where are you coming from. So while the goals looks similar for most, the path to get there will vary greatly.

## Maturity models presume an end state.

The idea that there is some final state we want to achieve tends to be a problem with maturity models. It is also something which we struggled with internally while developing our own CNMM. You don’t want to pass the message that there is an ultimate architecture/maturity to which all organisations must strive, and after which they are ‘done’.

How we attempted to solve this was to include a state beyond the “goal state” of Cloud Native. This is a speculative state which we vaguely named “Next.” While the specific technologies and techniques in the Next column are predictions -- after all, who can know the future? --  the goal is to show that you will continue to evolve even after achieving the current goal of Cloud Native.

To me, this is particularly interesting because the idea of an end state iat all runs completely counter to Cloud Native. Our goal is to build systems which are constantly evolving.

## Capability vs Maturity

In Accelerate, they stress the importance of focusing on capability models vs maturity models. Some of the reasons for this are the ones highlighted above. Additionally a capability model focuses on specific outcomes. This is an important point to keep in mind. It allows us to connect the goal (maturity level) with specific outcomes (capabilities) . The two are not mutually exclusive, rather, a good maturity model should focus on capabilities.

Where Maturity Models can be useful.
With so many challenges it makes sense to ask whether there are still benefits in using such tools. Here are some of the largest benefits I see to be gained by using maturity models:

*Simplicity* - large IT projects, such as Cloud Native Transformations are extremely complicated and can be difficult to grasp. It is often necessary to be able to trim out a great many details in order to provide a view of the whole, with a specific lens. In the case of maturity models, we get an intentionally high level view of the current state of our organisation, the state to which we are currently working towards, and how we get there.

*Visual representation* - related to the previous point, another benefit I’ve seen of maturity model is that they give a graphical representation of your project. We can often be overwhelmed with walls of text and detailed requirements. A simple, visual representation, even if it contains the same data often opens up a different part of our brain and triggers new ideas or ways of thinking.

*Trends* - while it is true that every company is unique, and each Cloud Native transformation is going to be different, it is also true that we must learn from those who have gone before us. One of the great benefits of open source software is that we can leverage the work and the learning of others.  Similarly, by creating a maturity model based on the choices, decisions and mistakes made by others, we can develop a model based on best practices of what has worked (and what hasn’t) in other organisations.

## A tool is only useful when used appropriately

At the end of the day, our Cloud Native Maturity Matrix model is a tool. Like any tool, if you are lacking appropriate context and information it is simply not useful. Similarly, as with any tool, it can cause more harm than good if used inappropriately. Sure I can run an Oracle database inside a Docker container, but that doesn’t mean that I should.

There is a very good paper What Make a Useful Maturity Model? by Jens Poeppelbuss and Maximilian Roeglinger that proposes design principles for maturity models. This is a great resource for anyone looking to create their own maturity model, or to evaluate the validity of an existing one. After reading through the paper I have been able to identify some missing pieces in our own model and identify some improvements. For example, a more clear explanation of the assessment criteria, or more granular levels of maturity.

Just like a Cloud Native architecture, our CS Maturity Matrix doesn’t have an end state. It is constantly being updated.

## Conclusion

It’s important for us to call out when things aren’t working. We should definitely not continue to use tools simply because we’ve used these tools in the past.  As a result of the initial utility and success of maturity models, there has been a huge growth in quantity, without any standards or checks on quality.

“In many circles maturity models have gained a bad reputation, but although they can easily be misused, in proper hands they can be helpful.” - Martin Fowler

The best answer to the question ‘Are maturity models useful?’  is, unsurprisingly, “Yes, but…” They can be useful, with caveats. The most important is context: make sure that the model you are using applies to the situation.

Finally, it’s crucial how you use the model. To quote one of my colleagues: “No one has ever dug a great hole holding the shovel upside-down the whole time.” Having the right tools is only the start. Using them the right way is what really yields results.
