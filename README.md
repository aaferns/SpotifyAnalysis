# Spotify Tracks Dataset Statistical Analysis

A comprehensive statistical analysis of the Spotify Tracks Dataset (114,000 tracks across 125 genres) using **base R**. This project explores the relationship between audio characteristics, genre, explicit content, and Spotify popularity through exploratory analysis, hypothesis testing, regression modeling, and classification.

## Overview

This project was completed as part of a university statistics course using only **base R** for data manipulation and visualization (with the exception of the required packages for multinomial regression and KNN classification). The objective was to apply statistical methods to a real-world dataset while interpreting results in a practical context.

The analysis demonstrates that although several audio features are statistically associated with popularity, they explain only a small proportion of its variation, suggesting that external factors such as artist recognition, playlist placement, marketing, and listener behavior likely play a much larger role.

## Dataset

- **Source:** Kaggle – Spotify Tracks Dataset
- **Uploader:** maharshipandya
- **Original Data:** Spotify Web API
- **Observations:** 114,000 tracks
- **Genres:** 125 (1,000 tracks per genre)

### Variables Used

- Popularity (0–100)
- Explicit content
- Track genre
- Danceability
- Energy
- Loudness
- Valence
- Acousticness
- Speechiness
- Tempo

## Data Preparation

The following preprocessing steps were performed before analysis:

- Removed tracks with popularity equal to 0
- Converted explicit content to a logical variable
- Selected five representative genres for comparative analyses:
  - Dancehall
  - Death Metal
  - Funk
  - Hip-Hop
  - Latino
- Used a reproducible random sample (`set.seed(123)`) of 10,000 observations for regression analysis

## Statistical Analysis

### Exploratory Data Analysis

- Summary statistics
- Histograms of audio features
- Popularity distributions
- Genre comparison boxplots
- Explicit-content frequency tables
- Correlation matrix

### Two-Way ANOVA

Model:

```R
popularity ~ track_genre * explicit
```

Evaluated:

- Genre effects
- Explicit-content effects
- Interaction effects
- Tukey HSD post-hoc comparisons

### Multiple Linear Regression

Model:

```R
popularity ~ danceability + energy + loudness +
             valence + acousticness +
             speechiness + tempo
```

Included:

- Backward stepwise model selection (AIC)
- Residual diagnostics
- Prediction intervals
- Model interpretation

### Classification

Genre classification using:

- Multinomial Logistic Regression
- K-Nearest Neighbors (KNN)

Model performance evaluated using an 80/20 train-test split.

## Key Findings

- Audio features exhibit very weak correlations with Spotify popularity.
- Genre significantly influences popularity.
- Explicit content alone has little overall effect on popularity, although certain genres exhibit significant differences.
- Audio characteristics explain less than 4% of popularity variance.
- Genre classification is substantially more successful than popularity prediction.
- Death Metal is highly distinguishable using audio features, while Dancehall, Funk, Hip-Hop, and Latino exhibit considerable overlap.

## Technologies

- R
- Base R graphics
- nnet
- class

## Repository Structure

```
Spotify-Statistics-Project/
│
├── data/
│   └── spotify.csv
│
├── R/
│   └── spotify_analysis.R
│
├── figures/
│
├── report/
│   └── Final_Report.pdf
│
├── powerbi/
│   └── (future dashboard)
│
└── README.md
```

## Future Improvements

- Export statistical summaries for Power BI dashboards
- Interactive visualization of genre comparisons
- Additional model validation and robustness analyses
- Expanded predictive modeling using additional Spotify metadata

## Author

**Aaron**

## Acknowledgements

- Spotify Web API
- Kaggle
- Purdue University
