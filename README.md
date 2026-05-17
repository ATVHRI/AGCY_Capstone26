# Keystone Project — What Makes a Song Stream?
### Exploring the Most-Streamed Spotify Tracks of 2023

**Author:** Andy  
**Course:** Data Analytics — Module 1 Capstone  

---

## Project Question

> **What audio characteristics, release patterns, and platform factors are associated with high streaming volume among Spotify's most popular tracks?**

---

## Dataset

**Primary dataset:** Most Streamed Spotify Songs 2023  
**Author:** Nidula Elgiriyewithana  
**Source:** https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023  
**DOI:** 10.34740/KAGGLE/DSV/6367938  
**File:** `spotify-2023.csv` (included in this repo)  
**Size:** ~953 rows × 24 columns after cleaning  

### Key columns

| Column | Description |
|--------|-------------|
| `track_name` | Song title |
| `artist_name` | Artist(s) |
| `artist_count` | Number of credited artists |
| `released_year/month/day` | Release date components |
| `streams` | Total Spotify streams |
| `in_spotify_playlists` | Number of Spotify playlists the track appears in |
| `in_apple_playlists` | Same for Apple Music |
| `in_deezer_charts` | Chart presence on Deezer |
| `in_shazam_charts` | Chart presence on Shazam |
| `bpm` | Beats per minute |
| `key` / `mode` | Musical key and mode (Major/Minor) |
| `danceability_%` | How suitable for dancing (0–100) |
| `energy_%` | Intensity and activity level (0–100) |
| `valence_%` | Musical positivity/happiness (0–100) |
| `acousticness_%` | Acoustic vs. electric character (0–100) |
| `speechiness_%` | Presence of spoken words (0–100) |
| `liveness_%` | Likelihood of live recording (0–100) |

---

## Repository Structure

```
keystone/
├── keystone_capstone.ipynb   # Main analysis notebook
├── spotify-2023.csv          # Primary dataset
├── requirements.txt          # Python dependencies
└── README.md                 # This file
```

---

## How to Run

1. **Clone this repo** and open the folder in VS Code.

2. **Create and activate a virtual environment:**
   ```bash
   # Windows
   python -m venv venv
   source venv/Scripts/activate

   # Mac / Linux
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Open the notebook** (`keystone_capstone.ipynb`) and select `venv` as the kernel (top-right kernel picker in VS Code).

5. **Run all cells** from top to bottom.

---

## Notebook Structure

| Section | Contents |
|---------|----------|
| 1 — Setup | Library imports, style constants |
| 2 — Load & First Look | Raw data load, `.info()`, initial observations |
| 3 — Data Cleaning | Fixing `streams` dtype, renaming columns, building release date, handling missing values, derived columns |
| 4 — Ethics Lens | Survivorship bias, playlist advantage, streams vs. listeners, geographic gaps, recency effects |
| 5 — EDA | Summary statistics, grouped analysis by year and mode, top artists table |
| 6 — EDA Charts | Stream distribution, tracks by release year, audio feature box plots |
| 7 — Story Charts | Playlist presence vs. streams (scatter), solo vs. collab (box plots), valence by mode (KDE) |
| 8 — Summary | Key findings, data limitations, next steps |

---

## Key Findings

- Stream counts are **heavily right-skewed** — median (~0.5B) is far below mean, driven by a small number of mega-hits
- **Playlist placement correlates with streams**, but causality is unclear (popular songs may earn more playlist placements, not just the reverse)
- **Collaborations don't reliably outperform solo tracks** at the median, though 2-artist tracks show a higher ceiling
- **Major-key songs have higher median valence** than minor-key, consistent with music theory — but overlap between modes is large
- **No single audio fingerprint** defines a top-streamed song — danceability, energy, and valence vary widely

---

## Data Limitations

This dataset only includes already-successful tracks. Findings describe what top-streamed hits have in common — not what *causes* streaming success. See Section 4 of the notebook for a full ethics discussion.

---

## Planned Extensions (Full Capstone)

- Merge with Billboard Hot 100 to compare streaming vs. radio chart performance
- Release month seasonality analysis
- Cross-platform correlation (Apple, Deezer, Shazam vs. Spotify streams)
