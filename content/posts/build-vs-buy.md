---
title: "Choosing technologies"
description: "Build vs Buy? Buy then Build?"
date: 2024-01-11T18:15:31+3:00
categories: ['Category A', 'Category B']
tags: ["proof-of-concept"]
draft: false
---

## Setting the scene

Your manager comes to you with an urgent task: You need an API Gateway and you need it yesterday. 

First you type in "API Gateway" into Google. You find a long list of articles telling you what the core features of an API Gateway are and some commercial offerings as well as some open source solutions. Finally, you realize all the blog posts are actually written by API Gateway vendors and they're using it for organic search SEO.

At this point you realize you have 2 options: 
- Build an API Gateway
- Use an Open Source API Gateway

No, you can't go with a commercial offering, not in this [post-ZIRP](https://newsletter.pragmaticengineer.com/p/zirp) economy!

So how do you go about deciding?

## Tradeoff Analysis

If you do things by the books, you will soon end up with columns of pros and cons for build vs buy. Build will generally give you greater flexibility, buy will generally be faster. Exceptions apply to the previous statement.

Most of the time, even if you intend to build something from scratch yourself, it's a worthwhile investment to kick the tyres on the open source offerings. 

Here's why:
- It lets you get familiar with the features you need
- It lets you see how someone else solved the problem
- It typically also gives you a hint of where the challenging parts are

## Use the open-source product first

If you need to get something deployed, start with an open-source solution (if one exists) first. As you start to use it,