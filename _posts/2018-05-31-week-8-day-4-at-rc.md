---
layout: post
title:  "Week 8, day 4 at RC"
date:   2018-05-31 19:00:00 -0500
tags: [flights, presentation, political science, sed]
---
Today, I felt overwhelmed with planning and emailing. Some of the planning was
not even work-related; I'm looking forward to reuniting with friends and
family... I managed to book a (one-way) flight, which made me feel better
about my progress. A few days ago, I booked a (round-trip) flight to Austin, TX
to go to [SciPy 2018](https://scipy2018.scipy.org/). Go, me!

I have been meaning to report on my experience at the
[BUILD]({% post_url 2018-05-02-day-0-at-build %})
[event]({% post_url 2018-05-03-day-1-at-build %})
earlier this month. So, I signed up to present today (at RC, every Thursday at
5:45pm, we enjoy a series of 5-minute presentations). I put together this short
list of
[web pages](https://gist.github.com/mkcor/c07061e07d3c99ed4b5153621487d4de)
and went through them. Thanks to this mini-presentation, I had the pleasure of
meeting a Recurser who studied political science at WashU.

To keep it somewhere, let me paste below the `sed` command that Casey and I
devised the other day:

```bash
sed -i "s/tags: \(.*\)/tags: [\1]/" *.md
```

The goal was to fix the non-array comma-separated syntax
[I used to use]({% post_url 2018-05-28-week-8-day-1-at-rc %})
to add tags to these blog posts. It resulted in this
[changeset](https://github.com/mkcor/mkcor.github.io/commit/2bc9dfa33511cf4fb53f6974efbf39726b135c53)
and, in the process, I learnt the following:

* `sed` differs in some ways between Unix variants (the above being GNU `sed`);
* `-i` stands for 'in-place';
* the [regex](https://en.wikipedia.org/wiki/Regular_expression) subpattern
inside `( )` is a *capturing group*;
* `\1` is a backreference to the first (here, only one) capturing group.
