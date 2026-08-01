---
title: "Software Engineer -> Harness Engineer"
date: 2026-06-19T00:00:00+03:00
draft: true
---

## An industry with an identity crisis

It appears that the software industry is in one of the largest times of change since the rise of the web or mobile. Coding agents like Codex and Claude are good. So good that they can crank out code better than 90% of human software engineers, in maybe 10% of the time. I know this can seem terrifying, especially for software engineers who are scared they will be out of a job, but we can see it as an opportunity as well.

It used to be that writing software required punchcards, and I still haven't heard of anyone who enjoyed using punch cards. Then it used to be that most software was written in assembly language. I'm sure there were some folks who did or still do enjoy these things, but most software engineers I've worked with enjoy a slightly higher level of abstraction.

And abstraction is what thes coding agents give us. They're good at churning out code, amazing at debugging but are terrible at avoiding duplication, creating clean abstractions and doing the whole "software engineering is programming integrated over time" part [https://en.wikipedia.org/wiki/Software_engineering#cite_note-27]

The hard part isn't getting code that works written. It's getting code that can be maintained and changed over the course of its useful lifetime. And that part hasn't been automated by coding agents because they lack the context, not because they lack the reasoning skills. It takes an enormous amount of context to make the right decision about how to create maintainable software. If your company is about to deprecate support for Java, and migrate all services to Go, maybe migrating to the latest Java version is not a good use of time/ tokens. For now, most of the decisions that are made are still outside of the context, out of reach of coding agents and effectively invisible.

## Software Engineering Redefined

So instead of writing the code directly, as Software Engineers we're now responsible for ensuring the coding agents produce maintainable code, and avoid common pitfalls that you as an experienced developer know about but the LLM does not. After all, the LLM was trained on all the publicly available code (which is potentially not the best quality code in existence, if we take the median). So instead of working on the product, we're now working on the factory that builds the product. Our job is to build the context pipelines, the guardrails and the positive feedback loops that improve the speed and quality of our product output. 

## The Harness Engineer

This is still a new and rapidly evolving space but we can see some companies describing what this new world could look like. OpenAI has [written about their experiments with a product with 0 human written code.](https://openai.com/index/harness-engineering/). [Martin Fowler's bliki](https://martinfowler.com/articles/harness-engineering.html) also contains a treasure trove of concepts and terms that attempt to define the taxonomy of Harness Engineering.