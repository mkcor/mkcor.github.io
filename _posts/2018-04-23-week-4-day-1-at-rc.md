---
layout: post
title:  "Week 4, day 1 at RC"
date:   2018-04-23 00:19:48 -0500
tags: [customizing, reading, networking, streaming]
---
This morning, I did a lot of planning and emailing. After lunch, I walked into
Converse's flagship store. Downstairs, I discovered the workshop, where they
make [custom shoes](https://www.converse.com/us/en_us/c/converse/custom). I
liked the idea.

In the library-like area of RC, I found a copy of this
[paper](https://hal.inria.fr/hal-00406166) and started reading it. Let me show
you its [BibTeX](https://en.wikipedia.org/wiki/BibTeX) entry (adapted from
[HAL](https://hal.inria.fr/hal-00406166v2/bibtex)'s):

    @inproceedings{flajolet:hal-00406166,
      TITLE = {HyperLogLog: the analysis of a near-optimal cardinality estimation algorithm},
      AUTHOR = {Flajolet, Philippe and Fusy, Éric and Gandouet, Olivier and Meunier, Frédéric},
      URL = {https://hal.inria.fr/hal-00406166},
      BOOKTITLE = {AofA: Analysis of Algorithms},
      ADDRESS = {Juan les Pins, France},
      EDITOR = {Jacquet, Philippe},
      PUBLISHER = {Discrete Mathematics and Theoretical Computer Science},
      SERIES = {DMTCS Proceedings},
      VOLUME = {DMTCS Proceedings vol. AH, 2007 Conference on Analysis of Algorithms (AofA 07)},
      PAGES = {137-156},
      YEAR = {2007},
      MONTH = Jun,
      KEYWORDS = {cardinality estimation ; Probabilistic algorithm},
      PDF = {https://hal.inria.fr/hal-00406166/file/dmAH0110.pdf},
      HAL_ID = {hal-00406166},
      HAL_VERSION = {v2},
    } 

I couldn't resist pasting it for two reasons: 0) academic nostalgia and 1)
address in the South of France! 

The paper caught my attention because it presents a cardinality estimator where
applications range from *networking* (which I've been meaning to get better at)
to data mining (which we use in data science). A cardinality estimator is an
algorithm for estimating (here, *probabilistically*) the number of distinct
elements in ((very) large) datasets. The latter usually come in the form of
[streams](https://en.wikipedia.org/wiki/Stream_(computing)), either because the
dataset is too large to fit in memory (data mining context) or because it is
(malicious?) data traffic (networking context).
