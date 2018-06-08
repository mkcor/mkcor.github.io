---
layout: post
title:  "Week 9, day 4 at RC"
date:   2018-06-07 18:00:00 -0500
tags: [R, tidyverse, low level, expression]
---
Exploring [`gestalt`](https://github.com/egnha/gestalt) has led me to study the
[tidyverse](https://www.tidyverse.org/) at a lower level. So far, I have been a
power *end* user of the tidyverse. First of all, I learnt about this R package
called [`rlang`](https://rlang.r-lib.org/), for working with low-level features
of the R language and the tidyverse. And there is the
[tidy evaluation](https://rlang.r-lib.org/reference/tidy-evaluation.html)
framework, for manipulating R expressions in specific ways (before they are
evaluated).

Like in any programming language, an expression in R is a combination of calls
(think *function calls*) and symbols (think *names* given to objects). We may
want to intercept, capture an expression (or parts thereof) instead of
evaluating it, because:

* extra, unnecessary computing may result from repeated evaluations, so we
  would like to optimize our program (see
  [lazy evaluation](https://en.wikipedia.org/wiki/Lazy_evaluation));
* we may want to repurpose this expression for use in other environments?

An [environment](http://adv-r.had.co.nz/Environments.html) is "a bag of names,"
where each name points to an object elsewhere in memory (the objects do not
live in the environment). Today, I learnt that a
[quosure](https://rlang.r-lib.org/reference/quotation.html#capture-expressions-in-quosures)
was an object wrapping an expression and its environment. I found this
sentence very beautiful: "Since they always evaluate in their original
environment, quosures can be seen as a vehicle that allow expressions to travel
from function to function but that beam back instantly to their original
environment upon evaluation."

Maybe "a vehicle" should be replaced with "vehicles" though. Otherwise, I
started a conversation with Eugene about
[metaprogramming](https://en.wikipedia.org/wiki/Metaprogramming). To be
continued next week...
