---
layout: post
title:  "Installing Javascript libraries the (kind of hard) easy way"
date:   2014-11-14 12:16:00
categories: code javascript tools
---

I just wanted to make a quick mention of [this post by Colin Toh](http://colintoh.com/blog/bower-best-served-with-build-tool) that outlines a cool way of installing and managing the javascript libraries that you use in your project.

From the post:

> My ideal package manager can install and inject my required packages in the right order with the correct file path reference automatically.

It seems like Colin's found a pretty good workflow to doing that that that would make a lot of tedious web development work a lot easier.

It relies on several other tools including [NPM](http://npmjs.org), [Bower](http://bower.io) and [Grunt](http://gruntjs.com) so it does take a bit of setting up the first time (and then a little bit of doing for each project...) but once you get it working grabbing a javascript library and using it in your project is as simple as running:

1. `bower install -S lodash`
2. `grunt`