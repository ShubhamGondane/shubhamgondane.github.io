---
title: 'Geospark: Hotspot Analysis'

permalink: /projects/hotspot-analysis
tags:
  - Big Data
  - Apache Spark
  - Hadoop
  - AWS
---

This project is to process and analyze NYC Yellow Taxi data set for identifying top 50 spatial hotspots using the Getis-Ord metric to find hotspots among cells.

We used GeoSpark which is a cluster computing system built on top of Apache spark for processing large-scale spatial data.

GeoSpark consists of three layers: Apache Spark Layer, Spatial RDD Layer and Spatial Query Processing Layer. GeoSpark provides a geometrical operations library that accesses Spatial RDDs to perform basic
geometrical operations (e.g. Overlap, Intersect).

We use the GeoSpark SpatialRDD and write spatial queries to perform various operations.

We used two datasets - points dataset which contains X,Y pairs and rectangles dataset which contains tuples of (X1,Y1, X2,Y2) which represent end points of a rectangle.

Example queries:

Range Query: To find which points from a given input set lie inside the rectangle
Range Join Query: Return number of pairs of Rectangles and Points such that the points lie completely inside the rectangle. Input is a list of rectangles and a list of points

Distance Query: Find number of points that lie within the given distance range from an input point
Distance Join Query: Given two points and a distance 'd' find the number of points are within d distance away from the given input points.

We setup a hadoop cluster on the AWS for running these operations. At every query execution we also monitored the network, CPU and memory load at different stages of the spark job execution.

More details can be found 
[here](https://shubhamgondane.github.io/files/CASCADE_Report.pdf "Project Report")