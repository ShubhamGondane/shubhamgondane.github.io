---
title: 'Image Recognition as a Service'

permalink: /projects/aws-cloud1
tags:
  - AWS
  - Cloud
  - AutoScaling
  - IaaS
---

The idea of this project was to build an application that can automatically scale out and in on demand and also in a cost effective manner using the resources available on the AWS. 

The application would provide an image recognition service to the users using a deep learning model. This can be  broken down into parts as follows:

Users would send an image to the application using HTTP service. The application will spin up a worker server to processs this image using the deep learning model and return the recogniton result back to the user via HTTP.

An important part of the project was to write an autoscaling mechanism that would allow the application to scale in and out efficiently. This algorithm was designed using two important metrics - The number of requests in an SQS queue waiting to be processed and the average CPU utilization of the worker instances.

The recognition results were also stored in a S3 bucket for persistence.

You can see the overall workflow of the system in the image below.
<br/><img src='/images/image-recognition.png'>


Object Detection as a service
------
Another variation of the above IaaS application

The application would provide an object detection service to the users using a deep learning model. This can be  broken down into parts as follows:

Users would send a request to the application using HTTP service. Upon receiving this request the application would send another HTTP request to a Raspberry PI cluster hosted in a lab in my school. The raspberry Pi cluster would then record some object and send the video back to the application for further processing. The application will then spin up a worker instance to processs this video using the deep learning model and return the recogniton result back to the user via HTTP.

You can see the overall workflow of the system in the image below.
<br/><img src='/images/Object-detection2.png'>

Technologies used
------
1. PHP
2. Java
3. Apache server
4. AWS Components
	1. EC2
	2. Simple Queue Service
	3. S3
	4. CloudWatch
	5. DeepLearning community AMI
