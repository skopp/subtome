Subscribe Button
================

[SubToMe](http://www.subtome.com/) is a **universal subscribe button**.
It decouples the content to which a user can susbcribe from the application this user may want to use to perform the subscription.
It's losely inspired by [WebIntents](http://webintents.org/).

The spec is the code, and the code is open source. Feel free to contribute to it. You could very well run your own instance, but that means users may have to reselect his favorite subscription tool over and over again.

By design, all state is kept in the user's browser.

This is intented at running as a bookmarklet or an embedded button.

# Workflow.

1. A user visits a site that is able to povide some kind of subscription mechanism. That site will then embed in its page some JS that will register this application on behalf of the user.

2. The subscription button script will store in the user's session the fact that he can use the previously described app for subscriptions.

3. Later, when on another site, the user wants to follow a given resource and clicks on the bookmarklet.

4. The user is then showed the list of service that may be able to handle his subscription.

5. Once the user picks a service, he's sent to that service to complete the subscription.

Build
=====

Install dependencies (you need to have node.js installed):

<code>$ npm install</code>

Compiling the code:

<pre><code>$ browserify src/settings.js -o build/settings.subtome.js
$ browserify src/register.js -o build/register.subtome.js
$ browserify src/subscribe.js -o build/subscribe.subtome.js
</code></pre>

Check Also
==========

[Ant0ine](http://blog.ant0ine.com/) very kindly contributed a [SubToMe Chrome Extension](https://chrome.google.com/webstore/detail/subtome/cjkhnlmkkfheepafpgppmpdahbjgkjfc) to add a little button next to your address bar. Quite convenient when you don't want to show your bookmark bar. [Source code](https://github.com/ant0ine/subtome-chrome-extension).

[Wordpress plugin](https://raw.github.com/superfeedr/subtome/master/goodies/wordpress/subtome.zip). Install it by following [these instructions](https://github.com/superfeedr/subtome/tree/master/goodies/wordpress/subtome). 

Todo
====

* Create a better icon/logo
* <del>Wordpress Plugin (button)</del>
* Browser extensions ( <del>Chrome</del> [install](https://chrome.google.com/webstore/detail/subtome/cjkhnlmkkfheepafpgppmpdahbjgkjfc), Firefox, Safari, IE).
* Integrate into more readers (RSS to email, RSS to xx... etc)
* Find ways to support non web based readers
* <del>Implement all the ideas from this [Ask HN](http://news.ycombinator.com/item?id=5197995) thread.</del>
* Find a hack to allow of a complete redirect with default settings. At this point, it seems extremely complex, as we would need a direct user action to do such. Most browsers tested at this point will opening of new windows as popups at this point :/

Going Further
=============

We intentionaly pushed the complexity down to the subscribing application, which should be smart enough to handle subscriptions if it has registered as such.

The subscribing application is in charge of extracting the data to which the user can subscribe (RSS or Atom feed, Social network handle, ... etc), from the page URL.

Known Supported Readers
=======================
* [The Old Reader](http://theoldreader.com/): a very nice new reader (despite its name).
* [Google Reader](http://www.google.com/reader): who doesn't know it?
* [NewsBlur](http://www.newsblur.com/): an advanced feed reader
* [Bloglovin](http://www.bloglovin.com/): a free feed reader
* [Blogtrottr](http://blogtrottr.com/): an RSS to email tool

Feel free to add yours (fork this page) if you implemented registration.




Discussions
===========

[The Mozilla Hacks](https://hacks.mozilla.org/2013/02/subtome-a-better-subscribe-button/)

Thanks
======
[Ant0ine](http://blog.ant0ine.com/)

