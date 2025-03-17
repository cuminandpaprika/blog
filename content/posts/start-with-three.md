---
title: "Start with Three"
date: 2020-04-11T14:34:27+10:00
draft: false
---

Engineering projects that require maintainable code should always start with a team of 3 or more engineers.

Why such an arbitrary number, you might ask? Why can't a single engineer write maintainable code? Perhaps your thoughts might lean towards peer-review for PRs and arrive at the number 2. Two engineers should be enough to properly review.

So why is it important for software to be maintainable?

Software in the real world is only written to solve a problem for someone. But it doesn't solve that problem fully (that's a discussion for another post). It only represents a solution to a problem **at that point in time**. Unfortunately, we don't live in a static world, so problems are always evolving. As the problem changes and new problems arise, the software must be modified or updated to meet these altered conditions. Or else they must be retired and decommissioned, as they are no longer _fit for purpose_. 

Here's where I'll bring in a dirty word. _Business._ Most of the software written today is to meet the requirements of a business. Someone wants to sell this solution to a problem, to some people who have this problem (A.K.A customers). A business can only continue to be profitable if their solution solves the ever-evolving problems of their customers. Therefore, if I have sufficiently convinced you that software must always change, then let me make a case for why it should be easy to maintain. 

Maintainability refers to the ability to quickly and successfully make changes to a codebase. If a business sells an unmaintainable product, then they can only sell a single version. As soon as they start trying to improve their product, they will very quickly see an endless amount of time and money spent on these changes. (This is probably why waterfall was and still is so popular. If you want to be sure that the change you make is correct, before making it, then it's reasonable to spend months on end planning it.) Thus, for businesses whose operating model relies on being able to continuously solve problems for their customers, they must have maintainable products.

Now, let's paint a picture of what a maintainable system looks like.

A maintainable codebase means that:

- Any engineer should be able to jump on the project and understand how it is set up (With the right knowledge of the language and frameworks used.)
- Any engineer should be able to confidently make changes
  - This means that a new engineer must understand
    - What problem the application is designed to solve. This requires a mixture of prose written for humans, as well as unit tests, so that we have a way of asserting that the application solves the problem it sets out to solve.
    - The limitations or bounds of the problem solved. The murky TODOs which have been left there, so that future engineers know not to step on these landmines. Or are at least aware of them enough to know they need to carefully disarm these landmines.
- The codebase is arranged in a modular fashion so that it is easy to understand where changes or additions should be made

This gives us a number of elucidating metrics:

- Documentation
  - Documentation exists for setting up prerequisites
  - Documentation exists for why this application exists
- Unit Test Coverage
  - Do unit tests exist for each modular part of the application?
  - Are these "unit" tests actually integration tests?
    - The question should be how many unit tests exist that do not make references to other modules?
- Modularity
  - Are the different software modules well-named?
  - Do they do anything that isn't listed on the box?
  - How many files/ modules must be touched to add a new feature?

Each of these measures is almost never done for a one-person project, sometimes done for a two-person project and is done a little bit more in a three-or-more project. Many of these attributes arise as a result of needing to collaborate with others. When we are not forced to collaborate with others, we tend not to think of the artifacts of software development from an external perspective. Even when this "external perspective" is a future version of ourselves.

Often in software engineering, a small proof-of-concept done by one or two people becomes a resounding success, acquiring more resources and a full team to "make it production ready". There are two scenarios here:

1. The engineering culture has matured enough to understand that proof-of-concepts are disposable tools for investigating the unknown. The ONLY engineering artifact that should be kept when building out the next product is the knowledge and understanding of the problem domain.
2. Most often, proof-of-concept code is handed to a team and they are locked into working with the architectural and language choices made by people who had no interest in the wider ramifications of their choices. They just wanted to make something work! Thus, a significant amount of effort is spent at this stage to add tests, write documentation, and even get the prototype working on their local machines.

If you're in the former, then hooray! You're making the most of throwaway code and its ability to let you do high-risk, innovative things and to use the learnings to build something better.

If you're in the latter, then please consider selling your management on the benefits of starting fresh. Writing maintainable code is an attitude, that is either adopted fully or not at all. Endless amounts of refactoring and posthumous documentation only serve to slow you down.

Hopefully by now, I've convinced you of three things:

- Software must be maintainable
- It's okay to write throwaway code.
- Throwaway code is not maintainable code.
- When you're ready to start writing maintainable code, a team of 3 or more is usually better.
