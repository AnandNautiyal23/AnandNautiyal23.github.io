---
layout: post
title: An E-commerce application for aftermarket auto parts
modified:
categories: blog
excerpt: Analysing the data of an e-commerce application 
tags: [Apache Spark, Zeppelin, Python, Scala]
image:
  feature:
date: 2017-12-29T11:58:29+05:30
---

Auto Parts Shop - An E-commerce application
======================


![DataEngineering](/data-engineering.png "DataEngineering")

### Table of Contents

- [Introduction](#introduction)
- [Requirements](#requirements) 
- [Installation](#installation)
- [Apache_Spark](#apachespark)




The Auto Parts Application is an an E-commerce project which deals in plethora of Aftermarket products of several vehicles. It is huge project with several teams working on it. We are supplied with raw data in various formats and we have to analyse it and make it into the desired forms.
It can involve working on Apache Spark, Scala or working it out in Python.



Requirements
------------

* Apache Spark (2.1.0)
* Java (1.8)
* Scala (2.11)
* Sbt (0.13.1)
* RAM (>= 8 GB)
* Processor (>= 2 Ghz)


Installation
-------------
* `sudo apt-get update`
* `sudo apt-get install default-jdk` 
* `sudo apt-get install scala`
* `sudo apt-get install git`
* `tar xvf spark-2.0.2-bin-hadoop2.7.tgz`
* `cd spark-2.0.2-bin-hadoop2.7.tgz`
* `cd bin`
* `./spark-shell`


Apache_Spark
-------------

If the present computing is to be analysed, data computing stands out of the crowd. Data lies at the core of the Internet era. Alongwith the product itself, a business relies a lot on the analysis of the data trends to make the product better and more wanted. And, it is a magical world out there when you see data talking to you and telling you the obvious. 

There are several tools out there for data computing. However, Apache Spark has gained a lot of popularity because of its ease to work with. It makes thing easier than hadoop. The major flaw with hadoop was the hectic process of writing out dataframes frequently after applying an operation on it. While, in spark, a series of operations can be performed on the dataframes and writing it out at the end of all the operations. 

Description
-------------

Our project involves raw data files which are unstructured. They contain a lot of scattered information which needs to be mined out for describing our product better. A single sku carries plenty of information in the form of files. All this information needs to be fetched from these files by applying various operations, as deemed necessary. The raw data, once processed acts as the source of information about that sku when it is viewed online.

The major task is to maintain the catalogue. The catalogue once live, needs to be analysed based on the sale trend. Then recommendation system sets it foot in. Recommendation models are used on the fetched data and better recommendations are provided to the client.
