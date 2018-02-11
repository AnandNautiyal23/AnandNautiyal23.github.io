---
layout: post
title: Machine Learning Algorithms for Recommender System - a comparative analysis
modified:
categories: 
excerpt: An analysis of the hotshot machine learning algorithms
tags: [MachineLearning, Clustering, Classification]
image:
  feature: Machine-Learning.jpg
  thumb: 
date: 2017-04-15T18:54:48+05:30
---
A thorough analysis of the Machine Learning Algorithms
======================


### Table of Contents

- [Introduction](#introduction)
- [Requirements](#requirements) 
- [Algorithms](#algorithms) 
- [Results](#results)
- [Conclusion](#conclusion)



Recommendation system is one of the most popular applications of Artificial Intelligence which attracts many researchers all over the globe. The advent of the Internet era has brought wide implementation of recommendation system in our everyday lives. There are many machine learning techniques which can be used to realize the recommendation system. Among all these techniques we are dealing with Content Based Filtering, Collaborative Based Filtering, Hybrid Content-Collaborative Based Filtering, k-mean clustering and Naive Bayes classifier. We have exploited these algorithms to their extreme in order to achieve the best possible precision and have presented a comprehensive comparative analysis. The strength of all these algorithms can be clearly realized by the significant enhancement in the accuracy, depicted by the experimental analysis taking cold start problem into consideration.

Requirements
------------

* Netbeans (8.1)
* Java (1.8)
* RAM (>= 4 GB)
* Processor (>= 2 Ghz)



### Algorithms

1) Content Based Filtering                                            

The Content Based Filtering considers the items rated by a user to formulate the future recommendations while exploring the internet services. A user tends to rate an item which he likes or dislikes. His ratings reflect his response towards that item. If he likes an item, he rates it higher and lesser ratings denote that he is not much interested. These rated items serve as the 'content' in the Content Based Filtering. Based on this content, the user is recommended future items which he might approve of. Here, the user is recommended movies which fall in a particular
genre of his liking.

Following Algorithm describes the idea.


{% highlight content %}

Input: users X, movies m, rating r, movie genre m g , Number of movies to be recommended(μ).

Output: Recommended movies R

1. for all users do
2. Select seen movies s, unseen movies s', association
of unseen movies as_i' w.r.t X, association of each 
genre ag_j w.r.t s' , where i is 1 to n and j is 1 to m.
3. Calculate score_j .
4. Select highest three score_j
5. Select m' ⊂ s' according to highest three score_j
6. Calculate score m_e' where e ∈ m' 
7. Return top μ score recommendations.
8. end for

{% endhighlight %}

{% highlight conten1 %}

In this algorithm, the notations used have the following meaning :
association of each movie as_i represents total number of users who rated movie i Є s';
association of each genre ag_j represents total number of movie belonging to genre j.

score_j = ag_j / m
score(m_e') = am_e / total count of m'

{% endhighlight %}




2) Collaborative Filtering

There can be many users who must be having the same pattern of rating an item as the user intended. This similar pattern of their ratings with the user guides the Collaborative Filtering. The notion behind the Collaborative Filtering is the recommendation of an item based on the
preferences of like-minded users.

The Algorithm used for the implementation is given below :

{% highlight collaborative %}

Input: users X, movies m, rating r, Number of movies to be recommended(μ).

Output: Recommended movies R.
1. for all users do
2. Select seen movies s, unseen movies s'
3. Find similarity (sim_i ) w.r.t s, where i = 1 to n.
4. Select highest sim_i user
5. Select m' Є s of user obtained in step 4 and s' of i_th user.
6. Calculate weight W(m_e ') where e Є m'
7. Return top μ weight recommendations.
8. end for

{% endhighlight %}


{% highlight collaborative1 %}

In this algorithm, the notations used have the following meaning :
sim_i represents common movies between user i and other users.

weight(m e ')= rating of particular movie e / max rating.

{% endhighlight %}


3) Hybrid Filtering

To cater better precision, a hybrid filtering method is used which can provide the advantages of both the content and the collaborative approaches and can overcome their shortcomings. Suppose, the user appreciates mostly movies in g ⊂ G genres, and the collaborating users also give high ratings to the g ⊂ G genres, then g will be taken as the metric to recommend movies to the user.

The algorithm for Hybrid Filtering has been used as :

{% highlight hybrid %}

Input: users X, movies m, rating r, movie genre m g , Number of movies to be recommended(μ).

Output: Recommended movies R.

1. for all users do
2. Select seen movies s, unseen movies s', association of each genre ag_j w.r.t s', where i is 1 to n and j is 1 to m.
3. Calculate score_j .
4. Select highest three score_j
5. Select m'' Є s of the i_th user according to highest three score_j
6. Find similarity (sim_j ) w.r.t m''
7. Select highest sim_j user.
8. Select m' according to its highest three score_j Є s of user obtained in step 7 and s' of the i_th user under consideration.
9. Calculate weight W(m_e') where e Є m'
10. Return top μ weight recommendations.
11. end for

{% endhighlight %}


4) K-Mean Clustering

The k-mean is a non parametric classification technique. It distributes the items into k clusters according to their proximity to one another. In this paper, this proximity is being measured by using the Euclidean distance. For calculating the Euclidean distance we have taken rated and unrated movies as binary. Each cluster possesses a centroid which is the mean of all the items in the cluster. All the objects in a cluster move
towards the centroid and the centroid is updated in each iteration. The iteration continues until a saturation point arrives, when the centroid stops altering. By following this approach we are decreasing the search space which results in reduced computational complexity. These computations are performed off-line which helps the classification to be efficient in terms of time complexity.

The K-means clustering Algorithm is given as :

{% highlight kmeans %}

Input: users X, movies m, rating r, Number of movies to be recommended μ, value of k.

Output: Recommended movie R.

1. begin
2. Randomly select k centroids.
3. Calculate euclidean distance (eucd) for X from k centroids.
4. Allocate X to k_th cluster according to eucd.
5. Update centroid for each cluster with (summation(k_i) from 1 to p)/p, where p is the number of members in k_i cluster
6. Repeat step 3 to step 5 until centroid(t) ≠ centroid (t+1).
7. for all users do
8. Select seen movies s, unseen movies s'.
9. Find similarity (sim_i ) w.r.t s, where i = 1 to p.
10. Select highest sim_i user.
11. select m' ⊂ s of highest sim_i and s' of i_th user.
12. Calculate weight W(m_e') where e Є m'
13. Return top μ weight recommendations.
14. end for
15. end

{% endhighlight %}


5) Naive Bayes

The Naive Bayes is based on the Bayes theorem. The probabilistic approach followed by Naive Bayes Classifier determines the probability of the classification and helps in finding the uncertainty about the model. It is an efficient learning algorithm which uses the prior knowledge of the
observed data. The Naive assumption is that the features are conditionally independent.

The algorithm used is given below :

{% highlight kmeans %}

Input: users X, movies m, rating r, Number of movies to be recommended μ, value of k.

Output: Recommended movie R.

Input: users X, movies m, rating r, number of movies to be recommended(μ)

Output: Recommended movies R.

1. for all users do
2. Select seen movies s, unseen movies s' .
3. Find similarity (sim_i) w.r.t s, where i = 1 to n.
4. Select x'⊂ X where sim_i > 10.
5. Calculate association of unseen movies as i' w.r.t to x'
6. Calculate score (s_e ') where e Є s'.
7. Return top μ score recommendations.
8. end for

{% endhighlight %}


Results
------------

We now illustrate the analysis of the experiments performed and provide a comparison of all the state-of-the-art methods described above. To compare their accuracy we have used the MovieLens dataset of 10K, 50K and 100K. The dataset varies in sparsity. For example, the 100K MovieLens dataset has 100K ratings, 943 users and 1682 movies of 19 different genres. The analysis of these algorithms is demonstrated based on precision measure. For each test user, we convert 30% of the user’s seen movies into unseen movies and apply the algorithms described above. Out of the total number of recommendations (T), the ones which are also present in the converted movies are the correct recommendations(tc).

Precision = (Σ tc / Σ T) * 100
For all the experiments, we are taking value of μ = 5 and value of k = 10.

The table below shows the precision of these algorithms as calculated.

![Precision](/precision_table.png "Precision") 

The results obtained can be visualized by the following figure :

![PrecisionDiagram](/precision_diagram.png "PrecisionDiagram")


Conclusion
-----------


All the algorithms described in this paper are compared with respect to their precision rates. This comprehensive analysis depicts the strength and the weakness of each one of them in different versions of the MovieLens dataset. The experiments performed are the witness of the sparsity handling by these algorithms. Our experiments have shown promising results and this paper conforms that out of all these approaches Naive
Bayes gives the best precision.

