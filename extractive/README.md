# Text Summarization
### Using extractive approach for creating summaries

![](https://img.shields.io/badge/license-MIT-green.svg)

This is a work in progress repository for my capstone project at Springboard Machine Learning bootcamp


## Contents
1. Project description
2. Process raw data
3. Exploratory data analysis (EDA)
4. Sentence scoring algorithm
5. Flask API on a web server

## 1. Project description

The objective of this project is to develop a text summarization tool able to create a short version of a given document retaining it most important information. This task is relevant for to access textual information and produce digests of news, social media and reviews. It can also be applied as part of other AI tasks such as answering questions and providing recommendations.

Dataset: The CNN news highlights dataset, which contains news articles and associated highlights, i.e., a few bullet points giving a brief overview of the article, with 92,579 documents.

The CNN dataset was downloaded from New York University, in the version made available by Kyunghyun Cho, which can be found [here](https://cs.nyu.edu/~kcho/DMQA/)

A description of this project development can be found on my portfolio website,

## 2. Data cleaning

Basic processing of the original dataset file separting article from summaries.

**Notebook:**
01-process-raw-data.ipynb [[launch notebook on Codelab]](https://colab.research.google.com/github/glopasso/text-summarization/blob/master/extractive/notebooks/01-process-raw-data.ipynb)

## 3. Exploratory Data Analysis (EDA)
Analysis of number of characteres, words and sentences on both articles and summaries. Identification of malformed articles and cleaning the dataset from them.

**Notebook:**
02-exploratory-data-analysis.ipynb [[launch notebook on Codelab]](https://colab.research.google.com/github/glopasso/text-summarization/blob/master/extractive/notebooks/02-exploratory-data-analysis.ipynb)

## 4. Sentence scoring algorithm

The sentence scoring algorithm was mostly based on Alfrick Opidi's article on Floydhub, named "A Gentle Introduction to Text Summarization in Machine Learning".

**Notebook:**
03-sentence-scoring-algorithm.ipynb [[launch notebook on Codelab]](https://colab.research.google.com/github/glopasso/text-summarization/blob/master/extractive/notebooks/03-sentence-scoring-algorithm.ipynb)

## 5. Flask API on a web server

#### HTTP POST calls to the API
**Format:** 
```shell
curl -X POST --data-binary @\<filename\> -d 'tokenizer=\<stem | lemma\>&n_gram=\<1-gram |2-gram | 3-gram\>&threshold_factor=\<float\>' https&#58;//summarizer-lopasso&#46;herokuapp&#46;&#8203;com/predict
```

The response is a JSON in the following format:
```shell
{"prediction" : "The generated summary"}
``` 
#### Web interface
Access the app on Heroku using the [link](https://summarizer-lopasso.herokuapp.com/).
The app has a self explanatory page, where the inputs are the text to be summarized and the algorithm parameters. The generated summary appears in the field on the bottom of the page, when the button "Submit" is pressed.

