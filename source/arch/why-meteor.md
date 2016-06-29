# Why Meteor?

For many years, web programming has been a drag. Developers used Javascript on
the client, and a different language on the server. Moreover, when these
different languages communicated via AJAX for dynamic pages, good software 
abstractions usually went out the window, resulting in things like jQuery 
spaghetti and therefore buggy apps.

What is a researcher to do, then, when most social science experiments actually
aren't *social* (since they study individuals), and to actually do social
experiments requires continual real-time interaction between large numbers of
participants? Meteor is at the forefront of a new generation of web technologies
aimed at tidying up the mess describe above, and can simplify building social
experiments significantly. As of now (June 2016) it is the [most popular web
framework on Github][meteor-stars], with an active community and extensive
documentation, and therefore great staying power.

[meteor-stars]: https://github.com/showcases/web-application-frameworks

Meteor's development paradigm is significantly different from almost all other
web frameworks, which generally focus on either the front-end or back-end. It is
full-stack from the ground up, using one language (Javascript), where the
server-side code runs on Node.js and the client-side runs in the browser. UI
code is mostly written declaratively rather than imperatively: instead of saying
_how_ you want to do something, you just write _what_ you want to do. Most
importantly, the core of Meteor is a distributed data framework (which the
declarative style hooks into) that greatly simplifies synchronizing state
between multiple clients and a server. This is another level of abstraction over
AJAX: instead of worrying about passing messages or calling remote procedures,
you can just specify the data that needs to be shared and it will be updated, in
real time, transparently. As a result, this can be an order of magnitude
reduction in the amount of code (and complexity) for a real-time or
collaborative app. As one article put it, [Meteor has made MVC obsolete](http://newcome.wordpress.com/2012/04/14/the-future-of-web-development-isnt-mvc-its-mvm/).
When leveraging front-end frameworks such as Twitter's Bootstrap that
integrate well with Meteor, we can also get started with much less custom CSS.

Meteor has many useful features, but the following are primarily useful for
researchers using web apps to study social behavior.
    
- **Easy development and fast prototyping.** Meteor is a one-stop shop for 
setting up development for a web app, pulling in dependencies automatically. 
It runs a local server that updates in real-time as you code. This is very 
useful for testing new research ideas and designs before committing to a 
running things at large scale.      
  
- **Real-time data synchronization.** Meteor has powerful primitives for 
synchronizing data across multiple clients, making social, collaborative apps
 almost as easy to build as single-user apps. This makes studying social 
 interactions much easier.     

- **Fast and easy deployment.** Deploying a Meteor app to a public server is 
[as easy as one command][deploy]. Getting an app accessible to the general 
public is often a lot of work for those unfamiliar with devops, and ease of 
deployment means you can get on with your research. 
   
- **Active and growing community of developers**. Meteor is one of the top 10
 frameworks on GitHub, and is built on the widely popular NodeJS. Building an
  app with TurkServer leverages these communities as much as possible. 
  Thus, you can find answers to many common issues on sites like 
  [StackOverflow][so] and [Meteor's forums][forums].

[deploy]: http://guide.meteor.com/deployment.html#galaxy   
[so]: http://stackoverflow.com/
[forums]: https://forums.meteor.com/ 

TurkServer is designed as a package (add-on) for Meteor, taking a Meteor app and
plugging it into MTurk. The advantage of this approach is that it leverages the
many examples of web apps built in Meteor and Javascript, even those not
specific to social experiments, without depending on much proprietary
functionality. Moreover, being able to contribute full-stack code makes
components such as a waiting room, chat, and other common paradigms much easier
to share. The future of online experiments is coming, and the next generation of
web technologies is a great force multiplier for getting things done!

Find out more about Meteor:

- [Getting started](http://guide.meteor.com/#quickstart)
- [Meteor Guide](http://guide.meteor.com/)
- [API Docs](https://docs.meteor.com/) 
- [Meteor on GitHub](https://github.com/meteor/meteor)
