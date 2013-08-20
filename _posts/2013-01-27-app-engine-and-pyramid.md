---
layout: post
title: "App Engine and Pyramid"
date: 2013-01-27
comments: false
categories:
 - OSX
 - GoogleAppEngine
 - Divsie
 - Pyramid
 - WebDevelopment
---
There are so many interesting libraries and frameworks which help bootstrap and start building modern web apps. I decided to explore some of the choices for a personal project. I want this project to run on Google's App Engine, using python on the server. Everything else is negotiable.

__Setting up OS/X__
Because I'm new to OS/X, I didn't know the ins and outs of developing on it. This is a digression from the topic of this post, but here are a few tips which would have helped me. Firstly, you must&nbsp;<a href="http://blog.cingusoft.org/mac-osx-lion-virtualenv-and-could-not-call-in">install the command-line development tools</a>&nbsp;because oddly, they aren't installed (even _after_ installing Xcode). Secondly, save yourself some trouble and avoid Apple's pre-installed python. Use the&nbsp;<a href="http://mxcl.github.com/homebrew/">Homebrew version of python</a>&nbsp;instead.

__Choosing a framework__
There is no shortage of python-based web frameworks, including many which work on App Engine. Wikipedia has a <a href="http://en.wikipedia.org/wiki/Comparison_of_web_application_frameworks#Python_2">comparison</a>. Two very popular choices are Django and Pyramid. I've used Django before in a toy project, and its biggest selling point is its ORM. The Pylons (predecessor to Pyramid) creator thoughtfully described the differences in a <a href="http://stackoverflow.com/questions/48681/pros-cons-of-django-vs-pylons">StackOverflow answer</a>. Here are a few talks worth watching discussing the options:

<iframe allowfullscreen="" frameborder="0" height="315" src="http://www.youtube.com/embed/EKS-Y2lT2BQ" width="547"></iframe>
<iframe allowfullscreen="" frameborder="0" height="315" src="http://www.youtube.com/embed/DBV0MsRu72M" width="547"></iframe>

I chose Pyramid. It is flexible, popular, lightweight, and works on App Engine.

__Getting started__
Follow <a href="http://docs.pylonsproject.org/projects/pyramid_cookbook/en/latest/deployment/gae_buildout.html">these instructions</a>&nbsp;to create a Pyramid-based App Engine project.&nbsp;Remember to use the Homebrew version of python!

Next, you'll want some boilerplate...&nbsp;<a href="https://github.com/h5bp/html5-boilerplate">HTML5 boilerplate</a>. Alternatively, check out&nbsp;<a href="http://www.initializr.com/">Initializr</a>, which has responsive and bootstrap-included versions of HTML5 boilerplate. This boilerplate also pulls in jQuery and a few other useful Javascript libraries.

_Note:_ Check out&nbsp;<a href="https://github.com/coto/gae-boilerplate">GAE boilerplate</a>. It uses webapp2 instead of Pyramid, so it's not directly applicable if you must have Pyramid. But it has basic user authentication and management which could give you a head start. The user authentication doesn't suit my purposes. I want to require user accounts to be tied to an <a href="https://github.com/coto/gae-boilerplate/issues/226">external identity provider</a>&nbsp;(no local passwords). And I want to handle multiple external accounts easily. For example, I would like to display <a href="https://account-chooser.appspot.com/">the account chooser</a> when logging in via Google. GAE boilerplate uses the App Engine users service which doesn't display the account chooser. Even worse, logging out logs the user out of more than just the app. <a href="https://code.google.com/p/googleappengine/issues/detail?id=5602">It logs the user out of all Google services</a> (Gmail and so on)! A better solution seems to be to avoid the App Engine users API completely, and instead use <a href="https://developers.google.com/identity-toolkit/v2/acguide">GITkit</a>.

_Stay tuned for more..._
