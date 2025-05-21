# 🎶 Melodic Links: A Network-Based Study of Artist Collaborations

## 📚 Course Project – Network Science (Group 36)

**Team Members:**
- Nikhil Kumar (2022322)
- Aditya Kumar Sinha (2022034)
- Pandillapelly Harshvardhini (2022345)

---

## 🧠 Overview

In today's global music ecosystem, artist collaborations drive cultural exchange, innovation, and exposure. Yet, existing datasets (like Spotify's) are often incomplete, lacking metadata like genre, origin, and language. 

**This project builds an enriched network of 51,002 verified artists and 158,232 real collaborations** — powered by Spotify, MusicBrainz, and an LLM-powered enrichment pipeline. Through this lens, we examine:

- Structural properties of the global collaboration network
- Rich-club and assortativity patterns
- Impact of geography, language, and popularity on collaboration
- Whether collaborations predict fame and commercial success

---

## ✨ Motivation

> “With today’s interconnected music scene, we wondered: _What drives collaborations? Do popular artists stick together? Does language matter in music fame?_”

We built our own **novel, cleaned, and richly annotated dataset** to answer these. This dataset supports research across geography, language, market visibility, and network structure — enabling a complete empirical study of artistic collaboration.

---

## 📊 Project Highlights

### 1️⃣ **Novel Dataset Creation**
- **Raw Data:** 156K artists from Spotify (Jan 2025)
- **Filtering:** Used MusicBrainz API → Removed ~105K unverified entries
- **Final Nodes:** 51,002 verified artists
- **Edges:** 158,232 true collaborations (albums, tracks, features)
- **Metadata Enrichment** via:
  - Ollama-based LLM for Genre, Country, Language
  - Multithreaded validation with MusicBrainz API
- **Result:** A rich, scalable, real-world music network

---

### 2️⃣ **Network Visualization & EDA**
- **Nodes:** 51,002  
- **Edges:** 158,232  
- **Density:** 0.0001 → Sparse  
- **Connected Components:** 478  
- **Largest Component:** 49,698 nodes (~97%)  
- **Max Degree:** 780 | **Min Degree:** 1 | **Avg Degree:** 6.2

#### 🔍 Key Analyses
- Degree Distribution → **Power-law**, confirming scale-free nature  
- Clustering Coefficient vs Degree → **Negative correlation** (hubs are bridges)  
- Compared with **100 random graphs** → Real graph shows stronger community structure (high clustering)

---

### 3️⃣ **Multi-Level Assortativity**

#### 🧬 Assortativity by Degree:
- Computed knn (avg neighbor degree) vs node degree  
- Result: **Positive trend** → hubs connect with hubs  
- Confirmed via **positive degree assortativity coefficient**

#### 💡 Assortativity by Popularity:
- Measured popularity difference per edge  
- Result: **Left-skewed histogram** → artists tend to collaborate with similarly popular peers

> ✅ Evidence of both **topological** and **market-level** assortativity — a stratified structure

---

### 4️⃣ **Language vs Popularity**
- Inspired by Ronen et al. (2014) who found English dominates global fame  
- Tested across 27K English-speaking artists vs others  
- **Result:** English is numerically dominant, **but** not the most popular on average  
- **Spanish, Korean, Portuguese** showed comparable or higher average popularity

> 🎧 Music fame is **platform- and genre-driven**, not just language-centralized

---

## 🧩 Additional Insights

### 🌐 **Geographic Collaboration Patterns**
- Labelled edges as **intra-** vs **inter-country**
- **More inter-country collaborations**
- Globalization, remote tools, and cross-border appeal weaken geographic barriers

### 📈 **Collaborations vs Commercial Success**
- Found strong correlations:
  - Degree ↑ → Spotify Popularity ↑
  - Degree ↑ → Follower Count ↑
- Feedback loop evident → Collaborations ↔ Exposure ↔ Popularity ↔ More Collabs

> 🔁 Strong evidence of **preferential attachment** in creative networks

---


## 📁 Repository Structure

```plaintext
AllDeliverables/
    └── Code.ipynb                   # Combined notebook with final analyses

DataCleaning/
    ├── DataCleaning.ipynb          # Initial artist data cleaning using MusicBrainz
    ├── DataGeneration.ipynb        # Dataset enrichment using LLMs & APIs
    └── SubsetGraph.ipynb           # Extract top-1% artist subset for visualization

EDA/
    ├── Comparions.ipynb            # Real vs Random Graph Comparison
    └── CompleteEDA.ipynb           # EDA on artist degrees, clustering, language, etc.

Images/
    └── *.png                       # Visualizations and plots used in the analysis

Novel Data/
    ├── edges.csv                   # Cleaned edge list (artist collaborations)
    └── nodes.csv                   # Final enriched artist metadata

Raw Data/
    ├── edges.csv                   # Raw collaboration data from Spotify
    └── nodes.csv                   # Raw artist data (before cleaning)

NS-PPT-GROUP-36.pptx                # Project Presentation
PROJECT_REPORT_2022322_2022034_2022345.pdf   # Full project report
README.md                           # This file

---


## 🛠️ Tools & Libraries Used
- Python (Jupyter Notebooks)
  - `pandas`, `numpy`, `matplotlib`, `seaborn`, `networkx`
- Spotify API  
- MusicBrainz API  
- Ollama (local LLM inference)  
- Multithreading for API management

---


## 📌 References
- Barabási, A.-L., & Albert, R. (1999). _Emergence of scaling in random networks._  
- Newman, M. (2003). _The Structure and Function of Complex Networks._  
- Ronen et al. (2014). _Links that Speak: The Global Language Network._  
- NetworkX, Pandas, NumPy documentation  

---

## 📽️ Project Presentation
- 📊 Slides: [`NS-PPT-GROUP-36.pptx`](./NS-PPT-GROUP-36.pptx)  
- 📄 Full Report: [`PROJECT_REPORT_2022322_2022034_2022345.pdf`](./PROJECT_REPORT_2022322_2022034_2022345.pdf)  

---

## 🙌 Acknowledgements
We thank our instructors, mentors, and the creators of open APIs like Spotify and MusicBrainz, as well as the open-source community behind Python and its scientific ecosystem.

---
