---
layout: post
title:  "Week 3, day 1 at RC"
date:   2018-04-16 00:18:48 -0500
tags: self-care, academia, continuous integration, conda
---
This morning, the weather was awful and, hence, perfect to stay in bed. I spent
a significant part of the day taking care of myself. On Friday, I went to
Columbia University with a few other RCers to attend a seminar
[On the Rational Role of Randomization](https://fphil.org/2018/04/03/icard-on-the-rational-role-of-randomization/).
I enjoyed how interdisciplinary it was (philosophy, computer science,
statistics, ...). I couldn't stay focused the entire time, so I will reach out
to the speaker, [Thomas Icard](https://stanford.edu/~icard/).

I missed the point he made about Bayesians making decisions, which is *the*
point I should have paid most attention to! Anecdotally, I had forgotten what
academic meetings looked like, after working in tech startups for several
years. For example, out of nowhere, a professor starts telling a story about a
Nobel laureate that happened over four decades ago...

Today, I decided to tackle this
[issue](https://github.com/bayesways/case_studies_Py/issues/4): What we want is
to automate the repetitive tasks of our data analysis pipeline. For now, we
focus on the very end of this pipeline, where we export our Jupyter notebook
into a PDF (via LaTeX). In a way, we are repurposing continuous integration
(CI) which, originally, automates the running of a test suite in a software
project.

I paired with [Brad](https://github.com/redSlug) to get started with this. It
was great to brainstorm, rubber duck, and get frustrated together! Initially,
we went for [CircleCI](https://circleci.com/). We switched to
[Travis CI](https://travis-ci.org/), because I could find more easily
[how to](https://conda.io/docs/user-guide/tasks/use-conda-with-travis-ci.html)
use it with conda. After one build that errored and another one that failed (as
expected), I got one to
[pass](https://travis-ci.org/mkcor/case_studies_Py/builds/367392774) and called
it a day. I will submit a pull request once I clean up the `environment.yml`
file: As I'm glad to read in this
[comment](https://github.com/conda/conda/issues/6073#issuecomment-357028031),
this file should only list user-provided dependencies.

Today, I would like to thank Ben for helping me out with my Linux kernel. I
could not boot because of a sound issue... For today, I selected an older
kernel to be able to boot. It's part of the Linux experience!
