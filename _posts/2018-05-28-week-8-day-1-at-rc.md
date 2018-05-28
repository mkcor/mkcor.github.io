---
layout: post
title:  "Week 8, day 1 at RC"
date:   2018-05-28 14:00:00 -0500
tags: [moving, proceedings, politics, vim]
---
I'm back! Two weeks ago, RC held
[Never Graduate Week](https://www.recurse.com/about). I missed it, to be
able to sort, store, donate, sell all my stuff in Montréal. Yes, I'm getting
ready to be a *digital nomad* for a few months[^1].
Last week was week 7 for my batch. Konstantinos and I submitted our
[proceedings](http://procbuild.scipy.org/) paper, titled "A Bayesian’s journey
to a better research workflow" (and I spent the rest of the week mostly
recovering from it).

[^1]: Cela ne pourra pas durer trop longtemps, à l'heure où il nous faut
      réinvestir le *territoire*, la *terre* et le *terroir*.

Week 7 for Spring 2 (my batch) also means week 1 for Summer 1, the new batch!
In this new batch, I have already met a couple people who cannot settle for
programming-for-the-sake-of-programming, which delights me. I enjoyed the
lengthy brainstorming session I had with Avery, some elements of which reminded
of this LibrePlanet 2017
[talk](https://media.libreplanet.org/u/libreplanet/m/move-fast-and-break-democracy/)
by Shauna Gordon-McKeon.

Today, I'm in shock after the Eurocratic putsch that happened in Italy[^2]. So,
I decided to tackle a project which would not mobilize all of my intellectual
and emotional resources (e.g., *not* learning
[Haskell](https://www.haskell.org/)). Let us consider this very blog you are
reading now. I have been meaning to display the *tags* which I specify for each
blog post: As you can see in the source of, say, the latest
[post](https://raw.githubusercontent.com/mkcor/mkcor.github.io/master/_posts/2018-05-09-week-6-day-3-at-rc.md),
I have been using the `tags` key in the
[YAML](https://en.wikipedia.org/wiki/YAML) header.

[^2]: Seguo l'informazione su
      [ByoBlu](https://www.byoblu.com/2018/05/28/il-nuovo-contratto-di-luigi-di-maio/).

But I have not been writing its value properly! I found this
[blog post](https://www.jflh.ca/2016-01-23-adding-and-displaying-tags-on-jekyll-posts)
and realized that my comma-separated tags should be wrapped in `[ ]` to form an
array. I paired with [Daniel](http://dan-f.me/) who, unlike me, is an
experienced web developer. Where does the HTML get put together? Exploring the
tree from the root directory, we found that
[`_layouts/`](https://github.com/mkcor/mkcor.github.io/tree/master/_layouts)
contained `.html` files with code showing attributes `title` and `date`, just
like the keys used in the YAML header.

[Here](https://github.com/mkcor/mkcor.github.io/commit/174c675b3cd1b24af7b176fc0c4d15ddd2a6e3d2)
is the basic functionality (and styling). Once I remembered that `_site/`
contained only build artifacts (and, indeed, this directory is
[not tracked](https://github.com/mkcor/mkcor.github.io/blob/master/.gitignore#L1)),
it was not too hard to figure out which file to edit for styling. I should also
thank Daniel for teaching me the `S` shortcut in vim: Delete line and enter
insert mode in one key stroke! Next, I should handle the non-array
comma-separated syntax I used to use in tags.
