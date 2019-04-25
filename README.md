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

### Data Preparation

All data used for this project has been retrieved using Spotipy, a lightweight Python library for the Spotify Web API.

Two playlists were created: one with over 7000 songs (good songs), obtained from saved tracks and saved playlists on my account; another with around 3000 songs (bad songs) created manually picking songs and playlists that I don't like.

The songs from the "good songs" playlist were labelled with a 1 and those from the "bad songs" playlist with a 0.

In the end, the database consists of over 10000 songs with the id of the song and main song features (including: acousticness, danceability, duration, energy, instrumentalness, key, liveness, loudness, mode, speechiness, tempo, time signature and valence) and a target value, which determines whether a song has been liked (1) or not(0).

### Data Ingestion & Database

In addition to what has been exposed above, an additional table was created to store the artists name together with their ID.
At the end, the database consists of two tables. One for all the tracks information and features (containing the artist ID) and another with the artists name and ID.

### Data Wrangling and Cleaning

For th


### Data Analysis



### Model Training and Evaluation

Different classification models are going to be tried in order to obtain the best possible classification: logistic regression, support vector machine, decision tree and random forest.

### Conclusion


### What are the next steps?


