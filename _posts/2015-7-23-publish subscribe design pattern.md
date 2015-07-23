---
layout: post
title: Publish Subscribe pattern
---

## Publish-subscribe pattern


The Angular circular dependancy error [https://docs.angularjs.org/error/$injector/cdep](https://docs.angularjs.org/error/$injector/cdep) results from services with injected dependencies A <- B <- A. 

There are ways to circumvent this error. This one [http://clintberry.com/2013/modular-angularjs-application-design/](http://clintberry.com/2013/modular-angularjs-application-design/) uses a main module with all sub modules directlyinjected in to it.

    Creating a “MainAppModule” allows us to inject all our other modules which in turn allows each of our other modules to access each other. So if the Reports module needs to access something from the Patient module, it will be able to with this method without having to inject the Patient module directly into the Reports module.



"

From [http://stackoverflow.com/questions/19344214/problems-with-circular-dependency-and-oop-in-angularjs](http://stackoverflow.com/questions/19344214/problems-with-circular-dependency-and-oop-in-angularjs) A circular dependency is a the sign of mixing of concerns, which is a really bad thing."

* [http://misko.hevery.com/2008/08/01/circular-dependency-in-constructors-and-dependency-injection/](http://misko.hevery.com/2008/08/01/circular-dependency-in-constructors-and-dependency-injection/)

The publish-subscribe pattern provide a way to loosely couple modules. 

* [https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern)

Angular provide the broadcast and listener mechanism to implement this pattern. 

* [http://codingsmackdown.tv/blog/2013/04/29/hailing-all-frequencies-communicating-in-angularjs-with-the-pubsub-design-pattern/](http://codingsmackdown.tv/blog/2013/04/29/hailing-all-frequencies-communicating-in-angularjs-with-the-pubsub-design-pattern/)

* [http://eburley.github.io/2013/01/31/angularjs-watch-pub-sub-best-practices.html](http://eburley.github.io/2013/01/31/angularjs-watch-pub-sub-best-practices.html)

* [http://jsfiddle.net/eburley/N2yUF/](http://jsfiddle.net/eburley/N2yUF/)

* [http://toddmotto.com/all-about-angulars-emit-broadcast-on-publish-subscribing/](http://toddmotto.com/all-about-angulars-emit-broadcast-on-publish-subscribing/)


### When to use a watch:

* when you're writing a directive and want data binding behavior
* when you're watching a stateful service
* when it's OK for the ui and state update to happen in a non-deterministic order

### When NOT to use a watch:

* when you need to orchestrate complicated data loading patterns
* when you're watching the routeParams.


