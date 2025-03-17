---
title: "From MVP to V1: Adjusting Development Strategies"
date: 2024-01-11T18:15:31+3:00
tags: ["proof-of-concept"]
draft: true
---

## How should software be built?

It depends.

There are two speeds at which Software Engineers need to develop code. The right speed depends on the stage of the company you are working at.

But before we get into that, we need to define what product-market fit is.

## Product Market Fit (PMF)

According to [Wikipedia](https://en.wikipedia.org/wiki/Product-market_fit):

> Product-market fit, also known as product/market fit, is the degree to which a product satisfies a strong market demand.

To rephrase this, it means you've proven that customers will pay for what you are building.

## Pre-product market fit

At this point, speed is everything. There are a million and one failed startups that have not found PMF. The first objective of a startup is to achieve product-market fit. Scope creep often comes in here, but it's important to be ruthless and to keep the feature set for the MVP as minimal as possible.

What do you not do here?

- Design highly scalable architecture
- Automate repetitive processes
- Refactor and clean up tech debt
- Write unit tests to make it easy to refactor and extend functionality
- Write code that is easy to unit test

A few caveats:
- If it's faster to write a unit test to verify some complex logic is correct, it's okay to do so.
- If you write any tests at all, integration tests and end-to-end tests have the highest return on investment here.

The goal is to validate your product hypothesis as quickly as possible. If you fail fast and fail cheaply, this means you have more opportunities to pivot and try different ideas.

## Post Product Market Fit

Congrats, you've found PMF. Customers are banging down your door to buy your product. Now you can build everything for real. You know the crappy MVP that's held together by scotch tape and hacky workarounds? You can now build your V1 the "right way".

Often companies will build on top of what already exists and evolve the MVP. This creates competing incentives because when building an MVP, any corner that can be cut should be cut. If you know you'll throw away the MVP, it removes any unnecessary constraints and also simplifies the solution space for the MVP and the V1.

A few considerations:
- In the process of building an MVP, you will have discovered better abstractions and models of the problem space.
- For a V1, you can start to think about how to architect your system and development process to increase development velocity and feature quality.

### Conclusion

Hopefully, I've helped clarify that it's okay to break the rules and show that there's no single "right way" of building software. The right way depends on the context around which the software is written. By recognizing these different stages exist, you can adjust your development approach accordingly, building the right software for the right circumstances.













