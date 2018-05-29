---
layout: post
title:  "Week 5, day 1 at RC"
date:   2018-04-30 19:00:00 -0500
tags: [bouldering, cobblestones, bokeh, streaming]
---
Yesterday, I went to the *original*
[Brooklyn Boulders](https://brooklynboulders.com/gowanus/) for a bouldering
session with my roommate. Afterwards, I hit the cobblestones of Soho. I picked
a cozy restaurant where they played live music. Yes, life could be worse. But
it could also be better... with a warmer weather!

I have been meaning to start using [Bokeh](https://bokeh.pydata.org/) for a
*long* time. I set it as a goal for my batch at RC, otherwise it might never
happen. That's typically what RC is for. Et
[voilà](https://github.com/bokeh/bokeh/issues/7842)! As you can see below, the
Python code is very friendly. With Bokeh, we are still following our thread of
handle large/streaming datasets...

```py
import pandas as pd

from bokeh.models import BoxAnnotation
from bokeh.plotting import figure, show, output_notebook

# get data for atmospheric carbon dioxide concentration
# (https://datahub.io/core/co2-ppm)
co2 = pd.read_csv('https://datahub.io/core/co2-ppm/r/co2-mm-mlo.csv')
co2['Date'] = pd.to_datetime(co2['Date'])

# create a new plot with a title and a datetime x axis
p = figure(title='Safe range for CO2 ppm',
           x_axis_type='datetime',
           x_axis_label='Date',
           y_axis_label='CO2 ppm')

# add a line renderer
p.line(co2.Date, co2.Interpolated, line_color='gray')

# add a box
p.add_layout(BoxAnnotation(bottom=250, top=350, line_color='green',
                           fill_alpha=0.2, fill_color='green'))

# show the plot
show(p)
```
