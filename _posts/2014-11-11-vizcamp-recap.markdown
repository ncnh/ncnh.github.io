---
layout: post
title:  "#VizCamp Recap"
date:   2014-11-11 23:38:00
categories: vizcamp code event recap
---
Thanks to [@WinthropCorinne](https://twitter.com/winthropcorinne), Diego and others that showed up and spent all day hacking at the first NoCoNewsHackers #VizCamp and of course thanks to Dani Castillo and Co. for graciously hosting us at their house. We covered a lot, so I thought I'd compile all the resources we talked about into a post to reference in the future.


### The terminal and the development environment

We spent the first part of the day going over using the terminal and setting up a development environment. Unfortunately this is where we encountered the most problems...  The takeaways-

**Customization is good** - make the terminal your own and it'll be easier and more enjoyable to use.

Be sure to install **Xcode Command Line Tools** in order to instal other command line apps.

#### Git

**[Git](http://git-scm.com)** is an invaluable tool for working with code of any kind.  As soon as your code base is bigger than a simple website, or as soon as you have more than one or two developers, you ought to be using git.  On top of that, it’s probably the easiest way to download and work with other people’s code.  Use it!

I recommend using the command line version--it’s just easier, I promise--but there are several good [graphical clients](http://www.git-tower.com) as well.  [This tutorial by GitHub](https://try.github.io/levels/1/challenges/1) doesn’t even require you to have git installed on your computer to complete it, however once you’re ready to install it on your machine try [this course](http://rogerdudler.github.io/git-guide/).

#### Even more terminal stuff!

Use **[sexy-bash-prompt](https://github.com/twolfson/sexy-bash-prompt)** to customize the 'prompt' in your terminal (ie, the line of text before the cursor that tells you where you are on your computer, etc.).  This will make a lot of things, including git, a lot easier to use.

Check out [this tutorial](http://computers.tutsplus.com/tutorials/navigating-the-terminal-a-gentle-introduction--mac-3855) about the terminal if you want to learn more or go over the commands we played with.

#### Editors

My personal favorite text editor is **[Sublime Text](http://www.sublimetext.com)**.  Be sure to grab **[sublime package control](https://sublime.wbond.net/installation)** to make installing extensions super easy.  Once you have that, find a color scheme you like (my personal favorites are railscasts and solarized dark) and install **[emmet](http://emmet.io)** and the SCSS syntax mode.  SublimeCodeIntel is also super useful for autocompleting things as you type them.

### SASS (ie, SCSS) and Bootstrap

SASS is, in my opinion, an invaluable tool for doing any kind of Web development.  It allows you to save tons of time writing CSS, avoid style bugs and get to the fun part of actually building data toys.

To install SASS on a mac, type `sudo gem install sass` (you'll have to enter your password).  If it worked, you should be good to go after that.

[The SASS guide](http://sass-lang.com/guide) covers pretty much everything you’d want to know.

Another big design timesaver is **[Bootstrap by Twitter](http://getbootstrap.com)**.  It’s essentially a collection of resources to get you up and running quickly so you can focus on solving whatever problem you’re trying to solve.  It’s awesome, it’ll make you smarter, and you should use it.

### Finding data, APIs, etc

The easiest (and most common) data format you’ll work with in javascript is **JSON**, which stands for JavaScript Object Notation

Data is pulled from either files or endpoints - files only change when they're updated and endpoints are 'dynamic' meaning they give you the latest data each time you go to it.

Some endpoints are **APIs**, meaning that you can give them options to specify what kind of data you want (eg, when we specified that we wanted the 'hardcover-fiction' list from the NYTimes bestsellers API).

APIs often take an **API key**, which is kind of like a user account for your code.

### Working with data

For the curious, there’s a [course on Lynda](http://www.lynda.com/Developer-tutorials/JavaScript-and-AJAX/114900-2.html) all about getting data with javascript.

To get the data into your code, you're going to use `$.ajax` (or the shorter version, [`$.getJSON`](http://api.jquery.com/jQuery.getJSON/)).  You can see an overview of jQuery's **ajax** (which stands for **a**synchronous **j**avascript **a**nd **x**ml, basically just a way to get data) functions [here](http://learn.jquery.com/ajax/).

Once you've requested the data (getting data is called a 'request') log it to the console with `console.log()` and spend some time exploring it by hand.

#### Doing something with it

When you know what you're looking for in the data, it's time to do something to it to get it onto the page.  The most common way to do this is with an **iterator**, which is basically a fancy way of saying "do something for every item in this list of things".  The example we used was [lodash’s](https://lodash.com) `_.each()`.

As soon as you start trying to generate a lot of markup with javascript you’ll likely find that it can be *really* tedious.  That’s where **templates** come in.  I like and recommend **[EJS templates](http://www.embeddedjs.com)** because you can do *anything* you can do with javascript in them.

Using EJS templates is easy.  Once you’ve got a template created (there are examples on the EJS site so I won’t show that here), just render it by running:

{% highlight javascript %}
var html = new EJS({url: '/path/to/my/template.ejs'}).render(data);
$('.some-element').append(html);
{% endhighlight %}


