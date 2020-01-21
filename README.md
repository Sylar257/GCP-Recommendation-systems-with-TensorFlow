# GCP Recommendation systems with TensorFlow

[***Introduction***](https://github.com/Sylar257/GCP-time-series-and-NLP#Introduction):  

[***Overview on Recommenders***](https://github.com/Sylar257/GCP-time-series-and-NLP#Overview): 

[***TensorFlow Hub***](https://github.com/Sylar257/GCP-time-series-and-NLP#TensorFlow_Hub): a collection of pre-trained machine learning models and reusable modules

[***Encoder-Decoder_networkds***](https://github.com/Sylar257/GCP-time-series-and-NLP#Encoder-Decoder-networks): often used in tasks such as language translation, question answering and text summarization

[***AutoML and DialogFlow***](https://github.com/Sylar257/GCP-time-series-and-NLP#AutoML_and_DialogFlow): A useful library that deal with all kinds of tensor-to-tensor problem setups



## Introduction

**Recommendation systems** are what behind the scenes that push YouTube videos to us that we actually find interesting.

However, Recommendation systems are not just about suggesting **products** to **users**. Sometimes they can be about suggesting **users** for **products** (this is often referred to as *targeting*).

Google Maps that suggests the *route that avoids toll roads*; smart reply suggest *possible replies* to email that we received are also **Recommendation systems**. It is about personalization for each individual user.

### Option I: 

**Content-based system**, we use the **metadata** about our products. (e.g. we know which movies are cartoons and which movies are sci-fi. Now, suppose we have a user who has seen and rated a few movie. Then we can recommend accordingly) Note that in this case, we have already segmented the **category** and know that corresponding attribute of each of our product.