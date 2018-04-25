---
layout: post
title:  "Week 4, day 3 at RC"
date:   2018-04-25 00:18:00 -0500
tags: dancing, web app, reactive programming, deployment
---
Early this morning, I went to a dance party on a boat; yes, I'm talking about
[Daybreaker](https://www.daybreaker.com/)! I had to catch up on sleep
afterwards... I have perused some of Shiny's
[source code](https://github.com/rstudio/shiny/blob/2260459422fe526f082bc392ed3f39fa52cb11e5/R/reactives.R).

Studying reactive programming as I did
[yesterday]({% post_url 2018-04-24-week-4-day-2-at-rc %}) makes me feel more
connected with all the people who are teaching themselves
[React](https://reactjs.org/), a web framework in JavaScript (JS). I'm not
inclined to program in JS again, so it's good to know that
[shinyjs](https://github.com/daattali/shinyjs) exists.

I have painlessly deployed my
[single-file](https://gist.github.com/mkcor/caf23ff13fda8076066f2deea328a327)
Shiny app (it's available [here](https://mkcor.shinyapps.io/reactivity/)) using
[shinyapps.io](https://www.shinyapps.io/). This is yet another convenience of
the RStudio ecosystem. Below is the R command and its stream. Talk about an
abstraction!

    > rsconnect::deployApp('reactivity')
    Preparing to deploy application...DONE
    Uploading bundle for application: 330235...DONE
    Deploying bundle: 1339067 for application: 330235 ...
    Waiting for task: 522262167
      building: Building image: 1350955
      building: Fetching packages
      building: Installing packages
      building: Installing files
      building: Pushing image: 1350955
      deploying: Starting instances
      rollforward: Activating new instances
      success: Stopping old instances
    Application successfully deployed to https://mkcor.shinyapps.io/reactivity/
