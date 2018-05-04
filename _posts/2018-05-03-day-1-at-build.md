---
layout: post
title:  "Day 1 at BUILD"
date:   2018-05-03 18:28:00 -0600
tags: academia, political science, data visualization, plotly
---
Today at [BUILD](http://politicaldatascience.com/BUILD/), we

* formulated research questions and hypotheses,
* ran [topic models](https://en.wikipedia.org/wiki/Topic_model),
* analyzed timeseries,
* created visualizations, etc.

Wow! We split into three groups and reconvened at the end of the day. Everyone
was so productive, eloquent, and pleasant to work with. I also appreciated the
hallway conversations I had with a few participants. Of course, we talked about
academia, career pathways, and *actual* work.

I used Plotly to create and share beautiful graphs. Below is the R code I wrote
to generate this [plot](https://plot.ly/~marianne2/2751). If you are interested
in working on these data (social media activity of US mayors), please team up
with a grad student from the Department of Political Science at
[WUSTL](https://wustl.edu/)!

```r
library(tidyverse)
library(lubridate)
library(plotly)

# Load data into memory.
fb <- read_csv("~/Downloads/FacebookPosts.csv")
fb$PageID <- as.character(fb$PageID)
mayors <- read_csv("~/Downloads/Mayors.csv")
mayors$FacebookPageID <- as.character(mayors$FacebookPageID)

# Count weekly number of FB posts per FB page.
fb %>%
  group_by(week = week(CreatedTime), PageID) %>%
  count() -> weekly_fb_counts

# Compute average weekly count.
weekly_fb_counts %>%
  group_by(PageID) %>%
  summarise(mean = mean(n), sd = sd(n), n = n()) -> wfc

# Join with table containing mayor/city data.
wfc %>%
  left_join(mayors, by = c("PageID" = "FacebookPageID")) -> wfc

# Create a graph showing multiple variables.
fp <- plot_ly(wfc,
             x = ~ Ideology,
             y = ~ mean,
             type = "scatter",
             mode = "markers",
             size = ~ Population / 10000,
             color = ~ CityWhite,
             text = ~ CityName) %>% hide_colorbar() %>%
  add_annotations(x = 0.4,
                  y = 90,
                  showarrow = FALSE,
                  text = "size ~ population") %>%
  add_annotations(x = 0.4,
                  y = 70,
                  showarrow = FALSE,
                  text = "color ~ non-white %") %>%
  layout(title = "Facebook post counts by US Mayors (Jun 29, 2008--Apr 18, 2018)",
         yaxis = list(title = "Weekly average"))

# Publish graph to Plotly.
api_create(fp, filename = "fb-posts-ideology-heterogeneity")
```
