---
title: 'Coreference Resolution in Clinical Documents'

permalink: /projects/coref-resolution
tags:
  - Natural Language Processing
  - Machine Learning
  - Clinical Text
  - Feature Engineering
---

Coreference information has been shown to be beneficial in a number of NLP applications including Information Extraction, Text Summarization, Question Answering and Machine Translation. Coreference resolution of concepts, although a very active area in the natural language processing community, has not yet been widely applied to clinical documents. 

Clinical text is unique because it requires significant use of domain knowledge to support coreference resolution. The system is developed to find concept from natural language in Electronic Health records(EHR) and resolve coreference between those concepts.

Example of Coreference resolution:

<br/><img src='/images/corefexample.png'>
Source: https://nlp.stanford.edu/projects/coref.shtml

Task:
----

1. Finding concepts from natural language text.
2. Finding coreferent pairs for the discovered concepts

We have considered 5 major types of concepts: 

	• PERSON
	• PRONOUN
	• PROBLEM
	• TEST
	• TREATMENT

Every concept is identified by its phrase string, the start and end position of the concept and the concept type. 

For example:

c="patient" 42:5 42:5\|t="person"


Dataset:
----
i2b2 dataset

Methodology:
-----

Extract concepts:

To extract concepts related to the medical domain, i.e., problem, test and treatment, we used the CLAMP tool. The CLAMP System is a comprehensive clinical Natural Language Processing software that enables recognition and automatic encoding of clinical information in narrative patient reports. 

For finding non-personal pronouns in the text we used POS tagging from the python Natural Language Toolkit(NLTK). For finding concept type person we used Stanford NER tagger. Temporal concepts were also extracted using the Stanford Temporal Tagger.

Find coreferent pairs

After extracting concepts we need to form coreferring pairs by generating all possible pairs from the document and remove the ones which are not coreferential, this approach ensures that we are considering all the possible cases and would help to achieve higher values of recall.

After generating all possible pairs we annotate corefering pairs using the gold labels from the training set. We trained a classifier to classify valid coreferring pairs. We used SVM classifier to build this model.

Some of the features used for classification:
	- Concept type of the mention pair
	- Length of the common part among the two strings
	- Common first word in the concepts
	- Number of word in both concepts 
	- Number of words that are common be- tween the two concepts

Classifier results:
Precision = 0.831 Recall = 0.760

You can find the entire project here:
[Code](https://github.com/rjsadaye/Coreference-resolution "Github link")

And the report here:
[Report](https://shubhamgondane.github.io/files/coref_acl2018.pdf "Project Report")
