# Why Meteor?

For many years, web programming has been a drag. Developers used Javascript on
the client, and a different language on the server. Moreover, when these
different languages communicated via AJAX for dynamic pages, good software 
abstractions usually went out the window, resulting in things like jQuery 
spaghetti and therefore buggy apps.

Meteor is at the forefront of a new generation of web technologies aimed at 
tidying up this mess. It has a many useful features, but the following are 
primarily useful for researchers using web apps to study social behavior.
    
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

Find out more about Meteor:

- [Getting started](http://guide.meteor.com/#quickstart)
- [Meteor Guide](http://guide.meteor.com/)
- [API Docs](https://docs.meteor.com/) 
- [Meteor on GitHub](https://github.com/meteor/meteor)
