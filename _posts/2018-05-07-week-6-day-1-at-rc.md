---
layout: post
title:  "Week 6, day 1 at RC"
date:   2018-05-07 10:00:00 -0500
tags: [blockchain, python, data provenance, open science]
---
Today, I tackled one of the items on my RC checklist:
[blockchain](https://en.wikipedia.org/wiki/Blockchain). I read this blog
[post](https://medium.com/crypto-currently/lets-build-the-tiniest-blockchain-e70965a248b)
and followed along. I
[forked](https://gist.github.com/mkcor/d68dc506ee40651fcba610db00b5e676) the
Python script and contributed the following improvements:

* made it usable [standalone](https://www.python.org/dev/peps/pep-0299/) but
also as an importable module;
* ported this Python 2 code to Python 3
([refresher](http://www.diveintopython3.net/porting-code-to-python-3-with-2to3.html));
* made it [PEP 8](https://www.python.org/dev/peps/pep-0008/)-compliant;
* abstracted functionality of adding blocks with a function definition;
* rewrote for loop as a list comprehension.

I am interested in blockchain in the context of doing Open Science. Blocks
which make up the chain can contain any type of data, so these data could be
(raw) datasets used in human subject research. Since the blockchain is
*immutable*, once a block is added to the chain, it cannot be modified or
removed.

So, this could be part of a solution to the problem of
[cherry picking](https://en.wikipedia.org/wiki/Cherry_picking), which happens
(either intentionally or not) in scientific research. In the life and medical
sciences or in the social sciences, it is usually not an option to make
datasets publically available (typically because they contain information about
human subjects).

More generally, it may be difficult to publish large datasets (regardless of
their content), because of practical (if not legal) considerations. That's why
the idea of a digital ledger which everyone can look up is so appealing. I
shared this idea at the beginning of my batch with CF and,
[the other day]({% post_url 2018-05-03-day-1-at-build %}), with Melody (at
BUILD).

On a philosophical level, I must say that, unlike many people in the free
software and free culture movements, I am not enthusiastic about using
blockchain for the greater good. I do not want to make the world more
contract-based and transaction-driven than it already is. I would like to thank
Noah for listening and helping me refine my ideas.
