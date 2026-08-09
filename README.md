# Spotify listening history & track audio features analysis

This repository contains an analysis of my personal Spotify streaming history merged with a Spotify track audio features dataset. The goal of the project was to clean and structure raw streaming data, combine it with track-level acoustic metrics, and apply K-Means clustering to identify distinct music mood groups.



## Overview & workflow

1. **Data preprocessing:**
   * Filtered raw streaming JSON logs to remove tracks listened to for less than 30 seconds (skips/accidental clicks).
   * Extracted temporal attributes (`hour`, `day_of_week`) for time-based analysis.
   * Standardized track and artist names (lowercasing, whitespace cleanup) for reliable merging.

2. **Dataset merging:**
   * Joined the cleaned personal streaming logs with Kaggle's Spotify tracks dataset (`maharshipandya/spotify-tracks-dataset`).
   * Matched tracks on normalized title and artist pairs to append acoustic features (*danceability*, *energy*, *valence*, *acousticness*, *loudness*, *tempo*).

3. **Clustering (K-Means):**
   * Scaled selected numerical features using `StandardScaler`.
   * Used the Elbow Method to evaluate optimal cluster counts.
   * Trained a 3-cluster K-Means model to segment the matched tracks into listening categories (e.g., upbeat, chill/acoustic, low-energy focus).



## Tech stack

* **Language:** Python 3.12
* **Libraries:** Pandas, Scikit-Learn, Matplotlib, Seaborn, Kagglehub

## Setup & running
git clone [https://github.com/olixxns/spotify-music-behavior-clustering.git](https://github.com/olixxns/spotify-music-behavior-clustering.git)
cd spotify-music-behavior-clustering

pip install -r requirements.txt

## Repository structure

```text
├── Spotify_Analysis.ipynb         # Main analysis and modeling notebook
├── requirements.txt               # Python package dependencies
└── README.md                      # Project documentation



jupyter notebook Spotify_Analysis.ipynb
