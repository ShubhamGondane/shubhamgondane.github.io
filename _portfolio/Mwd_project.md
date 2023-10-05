---
title: 'Movie Recommendation System'
permalink: /projects/movie-recommendation
tags:
  - Feature Engineering
  - Topic Modeling
  - Clustering
  - Recomendation Systems
  - Classification
---

This project served as an introduction to machine learning and feature engineering concepts. As the name suggests the project was to build a recommendation system for movies using the IMDB dataset. The project was divided into three phases with each phase focusing on an aspect of building a recomendation system.


Phase1: 
----
Focus on generating Tf-Idf based object-feature matrices and using cosine similarity to find similar movies. Objects could be movies or users and features could be anything from genres, tags, ratings etc. 
A time-weighted version of Tf-Idf was used for certain features so as to give more weight to newer tags or ratings.

Phase2: 
----
Focus on dimensionality reduction of 2-dimensional object feature matrices using Singular Value Decomposition(SVD), Principle Component Analysis(PCA) and Latent Direchlet Allocation(LDA). 

Given a set of seed actors (depending on users interest) implement a personalized page rank program to identify n related actors to the given seed actors.

Phase3:
----
1. Combination of previous phases and using all available information to build a program that recommends movies to the users

2. Use of probabilistic relevance feedback to improve accuracy of the matches provided by the recommender system using the user feedback.


