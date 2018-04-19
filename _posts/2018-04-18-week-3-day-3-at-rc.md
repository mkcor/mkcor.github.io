---
layout: post
title:  "Week 3, day 3 at RC"
date:   2018-04-18 00:20:08 -0500
tags: automation, deployment, patch, moving
---
Today, I submitted
[pull requests](https://github.com/mkcor?tab=overview&from=2018-04-18)! Let me
relish in the sense of accomplishment... As I wrote in the descriptions and
comments of these pull requests, I would like to use the container-based
infrastructure of Travis CI (and not `sudo apt-get install`). I would also like
to improve the overall project organization. But, in the meantime, I'm so proud
that the automation just *works*!

I shared my joy with the entire RC space. I'm deploying to GitHub Pages, so
this is [where](https://mkcor.github.io/case_studies_Py/) my build artifacts
live. One day, we'll customize the landing page. I spent a while wrestling with
[`diff`](https://github.com/bayesways/case_studies_Py/pull/7/commits/f26265109e7b9138086d6a73beed4a5eeb66817c)
and [`patch`](https://github.com/bayesways/case_studies_Py/pull/7/commits/f7da35aa73f0ba3faa3331ffb5b772762cd85625).
I thought I could write the patch myself, but I had to give up. It's not
human-writable; let `diff -u` take care of it.

Today, I'm moving, so I have to get going! I'm changing neighbourhoods in
Brooklyn.
