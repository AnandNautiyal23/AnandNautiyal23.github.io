---
layout: post
title: Time efficient Disvovery of moving object groups from Trajectory data
modified:
categories: blog
excerpt: Improving time-efficiency of travelling companion approach 
tags: [Data mining, spatio-temporal data]
image:
  feature:
date: 2017-07-29T11:58:29+05:30
---

Travelling Companion Problem
============================


### Table of Contents

- [Introduction](#introduction)
- [Requirements](#requirements) 
- [Related_Work](#relatedwork)
- [Problem_Definition](#problemdefinition)
- [Algorithms](#algorithms)
- [Experiments](#experiments)
- [Results](#results)
- [Conclusion](#conclusion)


Travelling companion is a type of object group, like swarm, convoy, flock, etc. As the objects move with respect to time, they leave their traces in the form of GPS locations. This gives rise to humongous spatio-temporal data which can be used in several domains of study like, social network applications, carpooling, scientific study of migratory birds, etc. The traditional DBSCAN algorithm as used in the Travelling Companion study has O(n^2) time complexity, which can be futile for streaming data. Our approach improved the time complexity to O(n log n), which is a huge improvement. 

Requirements
------------

* Netbeans (8.1)
* Java (1.8)
* RAM (>= 4 GB)
* Processor (>= 2 Ghz)


Related_Work
============                                            

There have been many similar studies to cluster moving together object groups. Some of them are flock, convoy, gathering, swarm, etc. Flock 
discovers a group of objects which are together for ‘k’ consecutive timestamps inside a disc of radius ‘r’. Convoy uses the density connectedness and has no restriction on shape and size. Swarm relaxes the constraint of clustering objects in consecutive timestamps. It can have non-consecutive timestamps. Gathering aims to find the coming together of certain objects for a particular time period.

Problem_Definition
==================

A sequence of snapshots s1,...,sn represent the trajectory data stream. Each snapshot has the spatial information of its constituent objects in the form of their latitudes and longitudes at a particular time. A snapshot can be represented as
 s_i = {o_1, x_(1,i) , y_(1,i)},..., {o_n, x_(n,i), y_(n,i)},
 where x_(j,i) , y_(j,i) are the spatial coordinates of object o_j at snapshot s_i.

As soon as a snapshot arrives, the objective is to find a traveling companion.

Definition 1 (Traveling Companion) Let S' represents the size threshold and T' represents the duration threshold, an object set 'q' is a traveling companion if:

(1) The constituents of 'q' are density-connected to each other for a period 't' where t ≥ T';
(2) S'(q) ≥ S'.

### Algorithms

Here is the Algorithmic representation of the work. 

![Algorithm](/Algo1.png "Algorithm")

![Algorithm](/Algo2.png "Algorithm")

### Experiments

The experiments are performed on the Microsoft T-drive Taxi [9] dataset for a different number of objects. Trajectories were generated up to 5000 taxis. Three datasets D1 (500 objects), D2 (1000 objects) and D3 (5000 objects) are used for performance evaluation. The grid-based approach outperforms the buddy based companion discovery and shows very promising results with an order of reduction in time. 

Results
=======

![Results](/Results.png "Results")

## Conclusion

This work incorporates the grid-based clustering approach with the buddy-based companion discovery algorithm for finding traveling companions in streaming data. The O(n2) time complexity of clustering step in the traveling companion discovery is reduced to O(nlogn) by using the grid-based approach. The efficiency of the grid-based approach is evident by the experimental results on different datasets of varying size. This reduction in time is highly significant to meet the requirements of real life applications.
