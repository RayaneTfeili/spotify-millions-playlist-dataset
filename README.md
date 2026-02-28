# Spotify Million Playlist Dataset

![Python](https://img.shields.io/badge/Made%20with-Python-blue?logo=python&logoColor=white)
![BigData](https://img.shields.io/badge/Tools-Dask%20%7C%20PySpark-orange)
![Task](https://img.shields.io/badge/Task-Playlist%20Recommendation-purple)
![Dataset](https://img.shields.io/badge/Dataset-1M%20Playlists-green)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

Large-scale exploration and analysis of the **Million Playlist Dataset (MPD)** — a collection of 1,000,000 user-generated Spotify playlists, with scalable data processing and baseline recommendation techniques.

---

## What this project demonstrates 
- **Large-scale structured data handling**:  loading big playlists (using PySpark and Dask) → track graphs / co-occurrence signals (classic recsys setup).
- **End-to-end notebook workflow**: cleaning → feature engineering → modeling → evaluation.
- **Recommender-system thinking**: strong baselines and metrics aligned with playlist continuation tasks.
---

## Dataset

The **Spotify Million Playlist Dataset (MPD)** contains **1,000,000 playlists** created by Spotify users between January 2010 and October 2017.

Each playlist includes:

- **Playlist metadata**  
  (playlist ID, name, number of followers, number of tracks, number of edits, etc.)

- **Track metadata**  
  (track name, artist name, album name, track URI, duration, etc.)

The data is stored as JSON slice files:

```
mpd.slice.START-END.json
```

Each slice contains approximately **1000 playlists**.

###  Dataset source

The dataset was released for the RecSys 2018 Challenge and can be downloaded from the official source:

https://www.aicrowd.com/challenges/spotify-million-playlist-dataset-challenge

>  The full dataset is large (~5GB+). Make sure you have sufficient storage and memory.

---

## Technologies Used

Due to the size of the dataset, scalable data processing tools were used:

- **Dask** — for parallel and out-of-core dataframe processing  
- **PySpark** — for distributed computation and large-scale transformations  
- **Pandas / NumPy** — for local analysis and experimentation
- **scikitlearn** - for a KNN, to predict the next song of a playlist 

These tools allow efficient handling of millions of playlists and tens of millions of tracks.

---

## Key Components

### Data Preprocessing

- Reading and merging multiple JSON slices
- Cleaning and structuring playlist-track relationships
- Building tabular representations for analysis
- Aggregating statistics at playlist and track level

---

## Exploratory Data Analysis (EDA)

The exploratory analysis includes:

- Distribution of tracks per playlist
- Most frequent artists and tracks
- Playlist name patterns
- Popularity and frequency distributions
- Co-occurrence analysis between tracks

Visualizations help better understand playlist creation behavior.

---

## Recommendation Baseline

This project includes simple baseline approaches for playlist recommendation:

- **Track frequency-based recommendation**
- **Co-occurrence statistics**
- **Similarity-based methods** (track-to-track similarity)

These baselines provide a foundation for more advanced recommender systems such as collaborative filtering or embedding-based models.

---
## KNN for Playlist Continuation

A **K-Nearest Neighbors (KNN)** model was implemented as a baseline for the playlist continuation task.

### Approach

1. Represent each playlist as a track-frequency vector
2. Compute similarity between playlists (e.g., cosine similarity)
3. Retrieve the K most similar playlists
4. Recommend tracks based on aggregated neighbor frequencies

This method provides a simple yet effective baseline for collaborative filtering without requiring matrix factorization or deep learning.

### Why KNN?

- Interpretable
- Easy to implement
- Strong baseline for recommendation tasks
- Aligns with collaborative filtering principles





