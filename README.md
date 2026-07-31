# ME204 Final Project: [Your project title]


| GitHub username                           | LSE ID            |
| ----------------------------------------- | ----------------- |
| Emily-glitch                              | 250100428        |


# Major Studio Halo Effect in Movie Ratings

## Overview

This project investigates whether major film studios benefit from a potential **"halo effect"** in audience evaluations.

The main research question is:

> **Do major studio films show larger audience–critic rating gaps than non-major studio films?**

To explore this question, I combine movie information from TMDB and OMDb APIs, compare audience ratings with professional critic ratings, and create an **audience–critic gap** measure.

The main findings are:

- Major studio films show slightly larger audience–critic gaps than non-major films, although the overall difference is modest.
- Genre differences appear to be stronger than the overall studio effect, with some genres showing larger variations between major and non-major films.
- Budget and release year do not provide clear explanations for the observed rating gap patterns.

The results suggest that major studios may have some influence on audience perception, but the effect is limited and cannot be explained by studio status alone.

---

## Data Sources

### TMDB API

Source: The Movie Database (TMDB) API

TMDB provides:

- Movie candidate lists through the Discover endpoint
- Movie metadata through the Movie Details endpoint
- Production company information used to classify major and non-major studios
- Audience-related information, including vote average and vote count
- Financial information, including budget and revenue
- IMDb IDs used to connect TMDB records with OMDb data

Movies were collected based on the following criteria:

- Release period: 2015–2024
- Minimum vote count: 2,000

Major studios were identified using the Big Five major film studios definition from Wikipedia, and TMDB production company IDs were used for classification.

### OMDb API

Source: OMDb API

OMDb provides additional movie information not available from TMDB, including:

- Professional critic score (`Metascore`)
- IMDb audience rating (`imdbRating`)
- Genre
- Year
- IMDb ID

IMDb IDs obtained from TMDB were used as identifiers when requesting OMDb data.

## How to Reproduce

### 1. Clone the repository

Clone this repository and navigate to the project folder.

### 2. Install required packages

Import the required Python libraries:

```bash
import requests
import json
import os
from dotenv import load_dotenv
import pandas as pd
import plotly.express as px
```

### 3. Obtain API keys

This project requires API keys from:

- TMDB API
- OMDb API

Create a `.env` file in the project directory and add:

```text
TMDB_API_KEY=your_tmdb_api_key
OMDB_API_KEY=your_omdb_api_key
```

The API keys are loaded using `python-dotenv`.

### 4. Run the notebooks in order

Run the notebooks sequentially:

```
NB01a_TMDB_API_Data_Collection.ipynb
NB01b_OMDb_API_Data_Collection.ipynb
NB02a_TMDB_Data_Processing.ipynb
NB02b_OMDb_Data_Processing_and_Feature_Engineering.ipynb
NB03_Exploratory_Analysis.ipynb
```

The workflow is:

```
TMDB API
    ↓
Raw TMDB JSON files

OMDb API
    ↓
Raw OMDb JSON files

Raw data processing
    ↓
movie_clean dataset

Exploratory analysis
    ↓
Figures and findings
```

### Notes

- OMDb has a daily API request limit of 1000 calls per day. The movie collection process is separated into major and non-major batches to reduce the risk of exceeding the limit.
- API keys are required to reproduce the data collection steps.
- Raw API outputs are not included in the repository and need to be regenerated using the provided notebooks.

