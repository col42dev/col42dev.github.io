---
layout: post
title: AngularJS-App-Template-Setup-Using-Yeoman-Grunt-And-Bower
---



* ####[Yeoman](http://yeoman.io/)####
This workflow is a robust and opinionated client-side stack, comprising tools and frameworks that can help developers quickly build beautiful web applications

* ####[Grunt](http://gruntjs.com/)####
A task runner for minification, compilation, unit testing, linting etc.

* ####[Bower](http://bower.io/)####
Bower works by fetching and installing packages from all over, taking care of hunting, finding, downloading, and saving the stuff youre looking for.


Ensure node package manager is updated.

    >npm install -g npm

Use npm to install Yeoman, Grunt and Bower

    >npm install -g yo grunt-cli bower

Use npm to install angular generator

    >npm install -g generator-angular

Use Yeoman to create an Angular app framework.

    >yo angular

Use bower to add angular bootstrap dependancy.

    >bower install angular-bootstrap --save

Use grunt to test and run the app


    >grunt test
    >grunt serve

Yeoman can also be used to create Angular scripts.

    >yo angular:controller user
    >yo angular:view user
    >yo angular:route myroute //Generates a controller and view, and configures a route in app/scripts/app.js connecting them
    >yo angular:directive myDirective
    >yo angular:route myroute
    >yo angular:filter myFilter
    >yo angular:service myService
    >yo angular:decorator serviceName