---
layout: post
title:  "First day at RC"
date:   2018-04-02 00:18:08 -0500
tags: blogging, ruby, timezone, version managing
---
"RC" stands for the [Recurse Center](https://www.recurse.com/). So, today was
my first day at RC. I will be spending the next three months growing as a
programmer (and as a person, for that matter). I am blown away by the quality
of the people and of the work environment here. I feel extremely privileged to
be a part of this community.

I had been meaning to give [xonsh](http://xon.sh/) a try for a while now. I may
explore its use in the context of data analysis workflows. I installed it in a
Python 3.6 conda environment and, voilà, I could run Bash and Python commands
together! Look:

    $ import glob
    $ if len(glob.glob('*.csv')) < 10: ls

For the rest of the afternoon, I debugged the blog that this very post lives
in. Thank you Arpith, Yuri, and Ashley for bearing with me! We noticed issues
with the links found in my RSS feed:

* the domain name was wrong;
* dates (and, hence, URLs) were derived from UTC time, not local time (which
results in the *next* day if you are blogging in the evening somewhere in the
Americas).

The first issue was quite straightforward to
[fix](https://github.com/mkcor/mkcor.github.io/commit/adf71935891fbab4e96b1a87d78516a1386cb811).
Somehow, when setting up this blog a long time ago, I gave a domain name which
I never (even intended to) purchase.

The second issue was confusing, because what I would get locally (untracked
files under `_sites/` resulting from `$ jekyll build` and browseable via
`$ jekyll serve`) would differ from what lived online. Locally, I would get
dates based on local time: This [post], written on December 30, 2015 around
8pm *Montréal time*, would be dated 2015-12-30. I think this is the desired
behaviour. But, online, the same post would be dated 2015-12-31 and live at a
URL containing `.../2015/12/31/...`.

Specifying the timezone in the [configuation](https://jekyllrb.com/docs/configuration/)
[fixed](https://github.com/mkcor/mkcor.github.io/commit/449dbda46ee42a8f7488241f9cf03491c680cef4)
the dates and URLs online. But it did not fix the links in the RSS feed! The
answer came from reading through this
[issue](https://github.com/mmistakes/minimal-mistakes/issues/417), which made
us aware of the Jekyll Feed plugin.

Finally, since I was running Jekyll version 3.0.1, I thought I would upgrade to
the latest version (3.7.3). Somehow,

    $ gem update jekyll
    Updating installed gems
    Nothing to update

would not do...(?) I had to run

    $ gem install jekyll:3.7.3

explicitly to get the latest version of Jekyll. I admit I am not fully
comfortable running Ruby and Jekyll system-wide... I create a virtualenv or a
conda env even for the tiniest Python project. Apparently, in Ruby, you would
use RVM or rbenv. Well, I admit my static blog is not really a Ruby project.
