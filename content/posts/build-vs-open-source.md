---
title: "Build vs Open-Source"
description: "A framework for deciding when to adopt an open-source solution, and when you've outgrown it."
date: 2024-11-28T17:54:44+03:00
categories: ['software']
tags: ["open-source", "build-vs-buy"]
draft: false
---

## Setting the scene

Your manager comes to you with an urgent task: You need an API Gateway and you need it yesterday.

First you type in "API Gateway" into Google. You find a long list of articles telling you what the core features of an API Gateway are and some commercial offerings as well as some open source solutions. Finally, you realise all the blog posts are actually written by API Gateway vendors and they're using it for organic search SEO.

At this point you realise you have 2 options:

- Build an API Gateway
- Use an Open Source API Gateway

No, you can't go with a commercial offering, not in this [post-ZIRP](https://newsletter.pragmaticengineer.com/p/zirp) economy!

So how do you go about deciding?

## Tradeoff Analysis

If you do things by the books, you will soon end up with columns of pros and cons for build vs open-source. Build will generally give you greater flexibility, open-source will generally be faster and require less maintenance. Exceptions apply to the previous statement.

Most of the time, even if you intend to build something from scratch yourself, it's a worthwhile investment to kick the tyres on the open source offerings.

Here's why:
- It lets you get familiar with the features you need
- It lets you see how someone else solved the problem
- It typically also gives you a hint of where the challenging parts are

## Use the open-source product first

If you need to get something deployed, start with an open-source solution (if one exists) first. It solves your problem today but isn't necessarily a forever solution. As you start to use the open-source solution, you'll learn what the features are and where the points of friction are. Which use-cases are easily solved by the open-source solution? You can keep a list of use-cases that are well solved and a list of gaps that act as a trigger point: if you have a deal breaker gap, then you've outgrown the open-source product.

## What happens when you outgrow the open-source product?

At some point, you might find that the open-source product doesn't fit your needs anymore. Generally any open-source or commercial software has a fundamental constraint: they can only ship features that 80% of their customer-base need. Most enterprise companies will have specific requirements that aren't supported by off-the-shelf open source or commercial software, whether that be scale, high availability or integration with the unique software ecosystem at that company.

You now have three options:

- Upstream contributions if enough other users will benefit
- Fork the Open-Source solution (e.g. Alibaba did this with their fork of MySQL, [AliSQL](https://github.com/alibaba/AliSQL))
- Create your own custom implementation from scratch

## When do you build custom from the start?

Every software company deploys a blend of open-source technology and in-house software. Generally, we want to build the core product in-house and use off-the-shelf for everything else: API Gateways, Feature Flag systems, databases, deployment tooling, etc. This helps us preserve our focus and attention on our core product, instead of wasting time implementing things that our customers don't care about.

We don't want to end up in a situation where our core product is inflexible because it's entirely an open-source product. We want the ability to add new features that differentiate our product from competitors.

## Conclusion

So now you have a rough idea of when to build something custom and when to just deploy an open source tool and find a more interesting problem to write code for.