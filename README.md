# Capstone-Guillermo

# 🎵 Capstone Project: Top Spotify Songs in Venezuela

A complete data analytics project exploring music streaming trends on Spotify's daily Top 50 chart in Venezuela — from raw data acquisition through cloud-based storage, exploratory analysis, and interactive dashboard development.

---

## 📌 Project Overview

This project analyzes daily Spotify chart data for Venezuela to uncover patterns in artist dominance, song popularity, and audio characteristics (danceability, energy) that drive chart success. The project follows a full modern data analytics workflow: raw data → BigQuery → Python/Colab EDA → cleaned data → Power BI dashboard.

The goal is to demonstrate an end-to-end analytics pipeline using industry-standard cloud and BI tools, while answering meaningful questions about music consumption trends in Venezuela.

---

## 📊 Dataset Description

- **Source:** [Top Spotify Songs in 73 Countries (Daily Updated)](https://www.kaggle.com/datasets/asaniczka/top-spotify-songs-in-73-countries-daily-updated) — Kaggle
- **Original Size:** ~497 MB, covering 73 countries
- **Filtered Subset:** Venezuela only (`country` = `VE`)
- **Rows (Venezuela):** 28,263
- **Columns:** 25, including:
  - `spotify_id`, `name`, `artists`
  - `daily_rank`, `daily_movement`, `weekly_movement`
  - `snapshot_date`, `popularity`, `is_explicit`
  - `duration_ms`, `album_name`, `album_release_date`
  - Audio features: `danceability`, `energy`, `key`, `loudness`, `mode`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`, `valence`, `tempo`, `time_signature`

The dataset is updated daily and reflects Spotify's official Top 50 chart for Venezuela across an extended date range (2023–2025).

---

## ❓ Problem Statement

Music streaming platforms generate massive amounts of behavioral data, but raw chart rankings alone don't explain *why* certain songs and artists dominate. This project investigates what characteristics — artist identity, audio features, and timing — are associated with sustained chart success in the Venezuelan market.

---

## 🔍 Business / Research Questions

1. Who are the most frequently charted artists on Spotify Venezuela, and what makes them consistently popular?
2. How does average song popularity trend over time, and which artists lead in popularity?
3. How do audio features (danceability, energy) relate to chart success?
4. What percentage of chart appearances come from local vs. international artists?

---

## 🛠️ Methodology

1. **Data Acquisition** — Downloaded the full 73-country dataset from Kaggle, filtered to Venezuela using Python/Pandas to reduce file size from 497 MB to a manageable subset.
2. **Cloud Storage** — Uploaded the filtered CSV to **Google BigQuery** (project: `capstone-guillermo`, dataset: `spotify_data`), creating the `venezuela_top_songs` table.
3. **Exploratory Data Analysis** — Connected Google Colab to BigQuery via the `google-cloud-bigquery` Python library. Performed:
   - Data quality assessment (missing values, duplicates)
   - Data cleaning and feature engineering (`year`, `month`, `duration_sec`)
   - Descriptive statistics and frequency analysis
   - Visualizations: bar charts, line charts, histograms, scatter plots, correlation heatmap
4. **Data Publishing** — Sent cleaned data back to BigQuery (`venezuela_clean` table) and created a summarized `top_songs` table.
5. **Dashboard Development** — Connected **Power BI** to BigQuery and built a 3-page interactive dashboard with KPIs, comparative charts, trend analysis, and audio feature exploration.

---

## 📈 Key Findings

- **Bad Bunny dominates** the Venezuela Spotify charts with significantly more chart appearances than any other artist, followed by KAROL G and Feid.
- **Feid** appears frequently both as a solo artist and in collaborations, making him one of the most consistent presences on the chart.
- **Danceability and energy show a positive relationship** — songs with higher danceability scores also tend to have higher energy, suggesting Venezuelan listeners favor upbeat, rhythmic tracks.
- **Average song popularity fluctuates significantly over time**, with notable peaks in late 2023 and early 2025, rather than following a steady trend.
- A small number of records contained missing song or artist names, which were removed during the cleaning process to ensure analysis accuracy.

---

## 🧰 Tools Used

| Tool | Purpose |
|------|---------|
| **Kaggle** | Dataset source |
| **Python (Pandas)** | Local data filtering and reduction |
| **Google BigQuery** | Cloud data warehouse and SQL querying |
| **Google Colab** | Exploratory Data Analysis (EDA) and Python scripting |
| **Matplotlib / Seaborn** | Data visualization during EDA |
| **Power BI** | Interactive dashboard development |
| **GitHub** | Version control and project portfolio hosting |

---

## 📂 Repository Contents

```
├── README.md                          # Project overview (this file)
├── Capstone_Guillermo.ipynb           # Full EDA notebook (BigQuery + Python)
├── /screenshots                       # Dashboard and BigQuery setup evidence
└── Final_Capstone_Report.pdf          # Final project report
```

---

## 👤 Author

**Guillermo Arcila**
TEDA 2051 — Data Technology Program
Mountainland Technical College

---

## 📜 Citation Note

This project was developed with the assistance of AI tools (Claude by Anthropic) for technical troubleshooting, code guidance, and documentation drafting, in accordance with course AI usage policies.
