# SPOTIPIE

Roger Roig - BCN Data analytics Bootcamp February 2019

### Overview

This project aims at building a model that clasifies a song on whether I like it or not.

### Repository Structure

The repository consists is structure in two folders. 
The folder 'notebooks' contains three notebooks: 
- data_preparation.ipynb --> contains the code for retrieving the features from the playlists and exporting the data.
- data_analysis.ipynb --> contains data visualization, statistical analysis and machine learning approach.
- new_data.ipynb --> consists of the code for predicting the likelihood of the songs of a new playlist and creates two playlists for good and bad songs, respectively.

### Data Preparation (data_preparation.ipynb)

All data used for this project has been retrieved using Spotipy, a lightweight Python library for the Spotify Web API.

Two playlists were created: one with over 7000 songs (good songs), obtained from saved tracks and saved playlists on my account; another with around 3000 songs (bad songs) created manually picking songs and playlists that I don't like.

The songs from the "good songs" playlist were labelled with a 1 and those from the "bad songs" playlist with a 0.

In the end, the database consists of over 10000 songs with the id of the song and main song features (including: acousticness, danceability, duration, energy, instrumentalness, key, liveness, loudness, mode, speechiness, tempo, time signature and valence) and a target value, which determines whether a song has been liked (1) or not(0).

### Data Ingestion & Database (data_preparation.ipynb)

In addition to what has been exposed above, an additional table was created to store the artists names together with their ID.
At the end, the database consists of two tables. One for all the tracks information and features (containing the artist ID) and another with the artists name and ID.

### Data Wrangling and Cleaning (data_preparation.ipynb / data_analysis.ipynb)

The data retrieved from the API was almost ready to use. It was only necessary to scale a few features, drop duplicates, and drop some NaN values.

### Data Analysis (data_analysis.ipynb)

Kernel density estimate plots were applied in order to explores the differences of the features between like and disliked songs. In addition, statistical t-tests between liked and disliked songs were carried out for each parameter.

### Model Training and Evaluation (data_analysis.ipynb / new_data.ipynb)

Over-sampling was applied to the data in order to account for imbalanced classes (3K disliked songs in front of over 7K liked songs).

Cross-validation was performed with different classification models, in order to obtain the best possible classification: logistic regression, support vector machine, K-nearest neigbhors, decision tree and random forest.

Decision tree and random forest yielded the best results. For the sake of simplicity, the decision tree was chosen as the final model.

In order to evaluate the performance of the model, performance metrics were calculated for the test data, which consisted in 30% of the original data. The overall accuracy was good (around 90%), even though the confusion matrix revealed that the model had a harder time classifying songs that I like.

### Conclusions

A personal music classifier was succesfully built with an accuracy of 90%. However, the model is not perfect and has a harder time classifying songs that I like. Factors that might have influence the performance of the model are the way the playlists were constructed, the fact that the likability of a song is subjective (and changes with mood and over time) and the problem that totally different songs might present very similar features.

### What are the next steps?

In order to improve this classifier, more songs could be added to train the model. It would also be nice to include other parameters, such as the song structure and lyrics. Finally, it would be interesting to include data from last.fm, a platform that keeps track of all the listening history in spotify, and would bring much more information, such as what songs were listened on what year, etc.
