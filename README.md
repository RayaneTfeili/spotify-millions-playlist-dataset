# Spotify Million Playlist Dataset — Analysis & Playlist Continuation 
**Notebook-driven project built on Spotify’s Million Playlist Dataset (MPD): data exploration + baseline recommenders for playlist continuation.** :contentReference[oaicite:0]{index=0}

> The **Million Playlist Dataset (MPD)** contains **1,000,000 user-created Spotify playlists** and was originally released for the RecSys Challenge on **Automatic Playlist Continuation** (predicting tracks that “belong” in a playlist). :contentReference[oaicite:1]{index=1}

---

## What this project demonstrates (AI / Data perspective)
- **Large-scale structured data handling**: playlists → track graphs / co-occurrence signals (classic recsys setup).
- **End-to-end notebook workflow**: cleaning → feature engineering → modeling → evaluation.
- **Recommender-system thinking**: strong baselines and metrics aligned with playlist continuation tasks.

---

## Repository contents
This repo is intentionally minimal and centered around a single notebook:

- `Project_final.ipynb` — end-to-end analysis + modeling workflow. :contentReference[oaicite:2]{index=2}

---

## Dataset
MPD is a large corpus of real playlists (with titles + track lists + metadata). Typical dataset structure uses **slice JSON files** (e.g., `mpd.slice.0-999.json`) containing playlist arrays. :contentReference[oaicite:3]{index=3}

**Common recsys framing**
- Treat playlists as “sessions” / “baskets”
- Learn track-to-track similarity via co-occurrence
- Recommend the next tracks that maximize relevance to the partial playlist

---

## Methods (typical baselines for playlist continuation)
Depending on what you implemented in `Project_final.ipynb`, a recruiter-friendly way to present the approach is:

### 1) Co-occurrence / Collaborative filtering baseline
- Track similarity via co-occurrence in playlists
- Score candidates by sum/mean similarity to seed tracks

### 2) TF-IDF / Bag-of-tracks playlist representation
- Represent each playlist as sparse vector (tracks)
- Use cosine similarity to retrieve nearest neighbor playlists
- Recommend tracks from neighbors not already in the seed playlist

### 3) (Optional) Hybrid signal
- Combine co-occurrence similarity + popularity priors
- Add title features if you used playlist names (NLP on titles)

> The RecSys Challenge framing and evaluation for playlist continuation is well documented and widely used in the literature. :contentReference[oaicite:4]{index=4}



## How to run
### 1) Clone
```bash
git clone https://github.com/RayaneTfeili/spotify-millions-playlist-dataset.git
cd spotify-millions-playlist-dataset
