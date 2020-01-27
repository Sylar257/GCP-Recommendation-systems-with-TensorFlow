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

There is no Machine Learning happening here.

**Content-based filtering** uses item features to recommend new items *similar* to what the user has liked in the past.

### Option II

**Collaborative Filtering**, we have **no metadata**. Instead, we learn the  learn about item similarity and user similarity from the ratings data itself.

We usually separate the large matrix into **user factors** and **item factors**. Then, if we need to find whether a particular user will like a particular movie, it's as simple as taking the row corresponding to the user and the column corresponding to the movie and multiplying them to get the predicted rating.

![collaborative_filtering](images\collaborative_filtering.png)

**Collaborative Filtering** uses similarities between users and items *simultaneously* to determine recommendations.

### Option III

![Hybrid_system](images\Hybrid_system.png)

If we have both the **meta-data** and **user interaction matrix**, we can build a **Hybrid system** that overcomes most of individual shortcomings.

For example, we could develop a few recommenders and then use one or the other **depending on the scenario**. If a user has already rated a large number of items, perhaps we can rely on a **content-based** method. However, if the user has rated only a few items, we may instead prefer to use a **collaborative filtering** approach. This way, we can fully leverage the information we have about other users and their interactions with items in our database, to gain some insight into what we can recommend.

Of course, if we have no information about a user's previous item interactions or we like any information about a given user, we may instead want to rely on a **knowledge-based** approach, and ask the user directly for their preferences via a survey before making recommendations. (this is why NetFlix asks you movies/shows you like when you create a new account)

Lastly, we can build an ensemble model based on all of three outcomes.

### Option IV

![Deep_learning_approach](images\Deep_learning_approach.png)

For example, suppose we wanted to recommend videos to our users, we could approach this from a deep learning point of view by taking attributes of the user's behavior input, for example, a sequence of their previously watched videos embedded into some latent space, combined with video attributes, either genre or artists information for a given video.