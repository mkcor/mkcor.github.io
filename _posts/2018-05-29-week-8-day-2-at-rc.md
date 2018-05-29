---
layout: post
title:  "Week 8, day 2 at RC"
date:   2018-05-29 17:00:00 -0500
tags: [outreach, haskell, static typing, R]
---
This morning was conducive to taking stock. I enjoyed reading Ashley's
[blog post](https://bits.ashleyblewer.com/blog/2018/05/28/weeks-7-and-8-at-recurse-center/)[^1].
I filled out the mid-batch survey, to let the RC faculty know how my batch was
going. I also reached out to a friend, who I believe would be a good fit for
RC, and wrote her an alumni recommendation. RC has a system in place for
recommending people who would be great Recursers and, hence, growing the RC
community.

[^1]: Touché, I am also an eye-rolling person!

In the afternoon, I started learning Haskell over at
[Haskell.org](https://www.haskell.org/): This interactive tutorial is quite
friendly and funny. You can get started right away, running Haskell code in the
web-based sandbox, no need to install any software! I didn't get to the meet of
Haskell (i.e., functions), instead I lingered over character strings which, in
Haskell, are lists of characters.

Check this out, where `λ` denotes the Haskell prompt:

```haskell
λ 'a'
'a' :: Char
λ "a"
"a" :: [Char]
λ "a" == ['a']
True :: Bool
```

I had no idea I should be so careful when using single vs double quotes. So,
use single quotes to create a character, and double quotes to create a
character *string*. Haskell lists contain elements of the same type; indeed,

```haskell
λ ['a', 'b', 'c']
"abc" :: [Char]
λ [42, 12, 22]
[42,12,22] :: Num t => [t]
λ [25, "marianne"]
No instance for (Num [Char]) arising from the literal ‘25’
In the expression: 25
In the expression: [25, "marianne"]
```

To keep elements of different types together, you need a tupe:

```haskell
λ (25, "marianne")
(25,"marianne") :: Num t => (t, [Char])
```

At this point, Haskell lists reminded me of
[atomic vectors](https://cran.r-project.org/doc/manuals/r-release/R-lang.html#Vector-objects)
in R, while Haskell tuples reminded me of
[generic vectors](https://cran.r-project.org/doc/manuals/r-release/R-lang.html#List-objects)
aka lists in R... Except that R is, well, dynamically typed.

```r
> # atomic vector
> c(42, 12, 22)
[1] 42 12 22
> typeof(c(42, 12, 22))
[1] "double"
> c('a', 'b', 'c')
[1] "a" "b" "c"
> typeof(c('a', 'b', 'c'))
[1] "character"
> # generic vector
list(25, "marianne")
[[1]]
[1] 25

[[2]]
[1] "marianne"

> typeof(list(25, "marianne"))
[1] "list"
# What if...
> c(25, "marianne")
[1] "25"       "marianne"
> typeof(c(25, "marianne"))
[1] "character"
> # Really?
> typeof(c(25, "marianne")[1])
[1] "character"
> c(25, "marianne")[1]
[1] "25"
```

Aww, R! I sat down with [Casey](https://rodarmor.com/) to touch on some of the
unexpected (non-robust) behaviours in R. We also discussed single vs double
quotes; he showed me character vs string in C. Finally, he shared this
hilarious quote he derived from Sartre's "L'enfer, c'est les autres:"

1. "Hell is other people"
2. "Hell is other people's code..."
3. "Hell is other people's dynamically typed code!"

On the contrary, Haskell is statically typed. How comforting! Something else I
liked right away about Haskell is the `let` syntax, to bound a variable,
because it feels similar to writing math[^2]. One thing I liked less is what
seems to be an absence of standard coding style: Look at how my `[42, 12, 22]`
is returned as `[42,12,22]` (eww).

[^2]: I discovered `let <variable> = ...` in recent JS but there is no `in` and
      it does not feel the same way.
