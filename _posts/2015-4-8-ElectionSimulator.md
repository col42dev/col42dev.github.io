---
layout: post
title: [Election Simulator](http://ec2-54-201-237-107.us-west-2.compute.amazonaws.com/stv/#/elect)
---

[Repository](https://github.com/col42dev/STV)

U.K. election season is in full flow, one interest of mine is in the mechanics of the electorial system itself. This web application is intended to show how the main voting systems work and how the same set of votes can generate different results depending on which system is being used. 

I have started with the [single transferable vote](http://en.wikipedia.org/wiki/Single_transferable_vote) system, this is a form of proportional voting which is typically used for elections where there are multiple seats to be allocated. 

In this simulator you can setup the conditions for the election - the number of candidates, the number of seats up for election and the number of votes to be cast. The simulator will randomly generate the set of votes based of these inputs, then it processes and display each of the voting resolution rounds which STV uses to determine the elected candidates. At each resolution round candidates may be eliminated or elected, it ends once the required number of candidates have been elected. 

[Election Simulator](http://ec2-54-201-237-107.us-west-2.compute.amazonaws.com/stv/#/elect)



