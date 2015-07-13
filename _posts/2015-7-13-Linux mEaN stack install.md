---
layout: post
title: Linux mEaN stack install
---


Install instructions for NodeJS and ExpressJS on an AWS Linux EC2 instance.


Identify the OS.

    [ec2-user@ip-172-31-38-189 html]$ uname -a
    Linux ip-172-31-38-189 3.10.48-55.140.amzn1.x86_64 #1 SMP Wed Jul 9 23:32:19 UTC 2014 x86_64 x86_64 x86_64 GNUx

Identity and update the npm and node install versions

    [ec2-user@ip-172-31-38-189 html]$ node -v
    v0.9.9

    [ec2-user@ip-172-31-38-189 html]$ npm -v
    1.3.4

    ec2-user@ip-172-31-38-189 html]$ sudo npm install npm -g
    npm http GET https://registry.npmjs.org/npm
    npm http 200 https://registry.npmjs.org/npm
    npm http GET https://registry.npmjs.org/npm/-/npm-2.13.0.tgz
    npm http 200 https://registry.npmjs.org/npm/-/npm-2.13.0.tgz
    /usr/local/bin/npm -> /usr/local/lib/node_modules/npm/bin/npm-cli.js
    npm@2.13.0 /usr/local/lib/node_modules/npm

    ec2-user@ip-172-31-38-189 html]$ npm -v
    2.13.0

Update nodeJS [http://stackoverflow.com/questions/8191459/how-to-update-node-js](http://stackoverflow.com/questions/8191459/how-to-update-node-js)


    [ec2-user@ip-172-31-38-189 html]$ sudo npm cache clean -f
    npm WARN using --force I sure hope you know what you are doing.

    [ec2-user@ip-172-31-38-189 html]$ sudo npm install -g n
    /usr/local/bin/n -> /usr/local/lib/node_modules/n/bin/n
    n@1.3.0 /usr/local/lib/node_modules/n
    [ec2-user@ip-172-31-38-189 html]$ sudo n stable

         install : node-v0.12.7
           mkdir : /usr/local/n/versions/node/0.12.7
           fetch : https://nodejs.org/dist/v0.12.7/node-v0.12.7-linux-x64.tar.gz
       installed : v0.12.7

    [ec2-user@ip-172-31-38-189 html]$ node -v
    0.12.7

The following modules need to be installed locally for the app.

    [ec2-user@ip-172-31-38-189 craftydb]$ npm install express
    [ec2-user@ip-172-31-38-189 craftydb]$ npm install body-parser
    [ec2-user@ip-172-31-38-189 craftydb]$ npm install mongojs
