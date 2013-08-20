---
layout: post
title: "Robust buildout"
date: 2013-02-03
comments: false
categories:
 - Divsie
 - WebDevelopment
---
If you followed the pyramid instructions from [a previous post][1], you have a buildout.cfg file which lists package dependencies. Unfortunately, buildout by default lacks some reproducibility. [Follow these instructions][2] to specify the exact versions of the packages to use, which can be determined with the following command:

```bash
bin/buildout -Novvvvv|sed -ne 's/^Picked: //p'|sort -u
```

[1]: http://blog.jgarrett.org/2013/01/app-engine-and-pyramid.html
[2]: http://maurits.vanrees.org/weblog/archive/2008/01/easily-creating-repeatable-buildouts
