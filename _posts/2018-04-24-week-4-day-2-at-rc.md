---
layout: post
title:  "Week 4, day 2 at RC"
date:   2018-04-24 00:19:48 -0500
tags: [neighbourhood, spanish, web app, reactive programming]
---
I stayed in Brooklyn for most of the day today. It feels good to experience my
new neighbourhood. I met up with Ana at the
[Commons Café](http://thecommonsbrooklyn.org/) and I had lunch at
[Oaxaca Taqueria](https://www.oaxacatacos.com/). There, the guy wouldn't
understand why I wouldn't switch to Spanish. Well... Hablo francés e italiano,
entonces, entiendo casi todo, pero... Bueno, la próxima vez, voy a tratar de
pedir en español.

I encountered the term *observable* when reading
[yesterday]({% post_url 2018-04-23-week-4-day-1-at-rc %})'s paper. I wasn't
sure what it meant. In physics, an observable is a variable which can be
measured; its value is a function of the system's state. In the paper,
'observable' must be understood in the context of
[reactive programming](https://en.wikipedia.org/wiki/Reactive_programming),
since the latter is concerned with data streams.

Looking up 'observable' and 'observer' prompted me to hone my understanding of
reactivity in the context of [Shiny](https://shiny.rstudio.com/), a web
framework in R. Like many data scientists, I often resort to Shiny to create
web apps painlessly. Shiny apps offer a convenient and effective way to share
insights and ask questions about data. Reactivity is about updating the app
upon change in a reactive source (here, user input).

So, an observable is a function of an *observer*, which is a *dependent* (or
*child*, in the reactive graph) of upstream objects (such as reactive sources).
To learn, I wrote this
[R code](https://gist.github.com/mkcor/caf23ff13fda8076066f2deea328a327),
adapting the
[single-file example](https://shiny.rstudio.com/gallery/single-file-shiny-app.html)
from Shiny's gallery. I followed this
[overview](https://shiny.rstudio.com/articles/reactivity-overview.html) step by
step and added comments, so that my toy (overkill) example can serve as a memo.
