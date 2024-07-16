---
title: "Engineering"
date: 2020-02-02T18:04:55+11:00
draft: true
---

Engineers are in the business of turning ideas into reality. Just like a wizard forms an intent and channels the energies of the ether, an engineer uses the tools at their disposal, the keyboard, the programming language and the cloud platform to formulate and execute an idea.

First, you want to test that idea was a good one. First attempts at an idea should be quick and dirty. If you've crafted an implmenetation to perfection, you've taken too long to test your idea. The first thing you need to do is to test the idea. 

The next question comes when you've worked out, great, the idea was a good one. How do I keep this running and bringing whatever benefits (money, social good, value) to the world? Then comes the bulk of the work, in making an idea robust, durable and maintainable.

Complexity
All systems are a function of their complexity. As complexity goes up, so does the speed of change of a system.

The success of an engineering team lies in their ability to test ideas quickly and then keep great ideas running for as long as the idea holds value in the world.
If we model it as a system

Inputs -> Engineering team -> Outputs

The inputs to a team include feedback from the users or customers.
The outputs are the systems we build and maintain.

So the key principles of an enginering team should be

- Speed
  - How quickly can we build something?
  - How quickly can we change something?
- Quality
  - How do we know that that the idea is a good one?
  - 

Programming languages constrain an engineer in how they can think about a problem and how they can express and solve a problem. Just like if how in some spoken languages, we have a myriad of words to express some things, but is anemic for expressing other ideas. The eskimo language has 20 differnt words to describe snow.

So what slows down engineering?
- Not having a goal
  - We need a north star for teams to align around, a purpose. This means that all team members should be able to point to a single source of truth for what the goals are, and why we agreed to take certain approaches. 
  - Most importantly, this should include things we've decided not to solve. The best way to achieve a goal is to only do the things that MUST be done to ensure it's actualization.
- Solving problems that don't need to be solved
  - The best way to 
- Alignment
- Focussing on multiple things
- Having too many meetings
- A lack of knowledge to execute on the idea
- A lack of understanding of the problem
  - Difficulty in accessing the relevant information
  - Lack of context of the problem we try to solve
    - This is why the practice of writing User Stories has become so popular
    - It's a semi-formal way of expressing what a user wants, leaving the flexibility to the implementer to solve the problem in any way.
- Lack of motivation
- Needing to write lots of boilerplate code when we just want to work on the key parts

Great, we've landed on a winner of an idea. How do we keep this going?
- Once a team has landed on a successful product, the next phase is to keep it running and profitable
- The feedback loop never stops as you're constantly iterating on new ideas, and more refined expressions of the original idea you came up with
- So, you need to ensure that an engineering team is kept tight in the loop of feedback from customers, so that we can keep making the product better and better.
- Part of this is managing complexity as a system grows. As ideas formulate and old ones die, we must religiously clean out the cruft that accumulates.
- Throughout this process, a design doc is the ultimate evergreen expression of how a system has evolved, and a log of all the decisions made in the lifetime of the system.
- 



So what tools do we need to do the above?

- First we capture the idea, by understanding who will be using the things we create.
  - This takes the form of user research and interviews. 
  - Human centered design.
- Once we've gained insight into a set of problems or jobs to be done, we can express these as user stories
  - As a human being, I would like to have access to fresh water so that I can be hydrated every day.
- Next we need to formulate our proposed solution to the problem. This can be captured in SYSL as a use-case

```
Human:
    Hydrate:
        Cabinet <- Glass
        Tap <- On
        Drink water
        return hydrated
```

Now we need to build the system that enables this interaction.
- So we need to build the Cabinet service that returns a glass
- Then we need to return a Tap service that returns water

We can specify those now here.

```
Cabinet:
    Glass:
        return glass
```
```
Tap:
    On:
        return water
    Off:
        ...
    
```

Once we've specified these services, we can generate some code that implements these services, as well as the necessary connectivity.
Before we're done here though, we need to implement the internal logic for each of these.
The cabinet service needs to keep track of how many glasses are in it. It needs to be replenished with clean glasses.
The tap needs to check how much water is available to it, and whether it has a sufficient water pressure.

Expressing these concepts in a modelling language allows engineers to take an idea first and see what it looks like. It helps in the design phase as it a purer expression of the idea, when seeing a diagram, versus trying to read some code. 

The common practice now is for these diagrams to be build using Visio or some other tool, before code is written against these diagrams. Sysl allows for these diagrams to go from idea to implmenetation directly. This also has the added benefit that any future changes are made directly to the model, the single source of truth.

Now that our system has been implemented, how about the running of these system? Because our documentation is always up to date, any troubleshooting is aided by these highly accurate diagrams.

But wait there's more.

Because the generated code has a set of standard observability tools baked in, we can diagnose and troubleshoot using a set of observability tools.

Oh and how about ensuring that our systmes are connected in a standard way, securely and reliably? Yup, code generation also provides that.

Soft factors to engineering success
- Team size
- Knowledge
  - Easy to discover relevant information
  - 
- Meeting budgets
- Discoverability
- Empowerment of autonomous teams
- Clear high level goals
- 
















