---
layout: post
title: Linux MongoDB EC2 install
---


Install MongoDB for 64 bit linux [http://docs.mongodb.org/manual/tutorial/install-mongodb-on-linux/](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-linux/)


>**$ curl -O https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-3.0.4.tgz**

      % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                     Dload  Upload   Total   Spent    Left  Speed
    100 38.4M  100 38.4M    0     0  8460k      0  0:00:04  0:00:04 --:--:-- 8461k

>**$ tar -zxvf mongodb-linux-x86_64-3.0.4.tgz**

    mongodb-linux-x86_64-3.0.4/README
    mongodb-linux-x86_64-3.0.4/THIRD-PARTY-NOTICES
    mongodb-linux-x86_64-3.0.4/GNU-AGPL-3.0
    mongodb-linux-x86_64-3.0.4/bin/mongodump
    mongodb-linux-x86_64-3.0.4/bin/mongorestore
    mongodb-linux-x86_64-3.0.4/bin/mongoexport
    mongodb-linux-x86_64-3.0.4/bin/mongoimport
    mongodb-linux-x86_64-3.0.4/bin/mongostat
    mongodb-linux-x86_64-3.0.4/bin/mongotop
    mongodb-linux-x86_64-3.0.4/bin/bsondump
    mongodb-linux-x86_64-3.0.4/bin/mongofiles
    mongodb-linux-x86_64-3.0.4/bin/mongooplog
    mongodb-linux-x86_64-3.0.4/bin/mongoperf
    mongodb-linux-x86_64-3.0.4/bin/mongod
    mongodb-linux-x86_64-3.0.4/bin/mongos
    mongodb-linux-x86_64-3.0.4/bin/mongo

>**$ mkdir -p mongodb**

>**$ cp -R -n mongodb-linux-x86_64-3.0.4/ mongodb**


Add bin dir to path

>**$ echo $PATH**

    /usr/local/bin:/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/sbin:/opt/aws/bin:/home/ec2-user/bin

>**$ export PATH=$PATH:/home/ec2-user/nginx/html/mongodb/mongodb-linux-x86_64-3.0.4/bin**


>**$ echo $PATH**

    /usr/local/bin:/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/sbin:/opt/aws/bin:/home/ec2-user/bin:/home/ec2-user/nginx/html/mongodb/mongodb-linux-x86_64-3.0.4/bin


Start instance

>**$ mongod --httpinterface --rest**

    2015-07-13T10:21:42.218+0000 I JOURNAL  [initandlisten] journal dir=/data/db/journal
    2015-07-13T10:21:42.219+0000 I JOURNAL  [initandlisten] recover : no journal files present, no recovery needed
    2015-07-13T10:21:42.236+0000 I JOURNAL  [durability] Durability thread started
    2015-07-13T10:21:42.236+0000 I JOURNAL  [journal writer] Journal writer thread started
    2015-07-13T10:21:42.250+0000 I CONTROL  [initandlisten] MongoDB starting : pid=21309 port=27017 dbpath=/data/db 64-bit host=ip-172-31-38-189
    2015-07-13T10:21:42.250+0000 I CONTROL  [initandlisten] db version v3.0.4
    2015-07-13T10:21:42.250+0000 I CONTROL  [initandlisten] git version: 0481c958daeb2969800511e7475dc66986fa9ed5
    2015-07-13T10:21:42.250+0000 I CONTROL  [initandlisten] build info: Linux build9.nj1.10gen.cc 2.6.32-431.3.1.el6.x86_64 #1 SMP Fri Jan 3 21:39:27 UTC 2014 x86_64 BOOST_LIB_VERSION=1_49
    2015-07-13T10:21:42.250+0000 I CONTROL  [initandlisten] allocator: tcmalloc
    2015-07-13T10:21:42.250+0000 I CONTROL  [initandlisten] options: {}
    2015-07-13T10:21:42.377+0000 I NETWORK  [initandlisten] waiting for connections on port 27017


Or if the default data directory is not accessible ...

>**$ /bin/mongod --dbpath /Users/colinmoore/data --httpinterface --rest**


Open Mongo shell

>**$ mongodb-osx-x86_64-3.0.4/bin/mongo**

    > db.accounts.insert({x:10})
    WriteResult({ "nInserted" : 1 })
    > db.accounts.find()
    { "_id" : ObjectId("55a39beabbb7da1442e00e78"), "x" : 10 }




