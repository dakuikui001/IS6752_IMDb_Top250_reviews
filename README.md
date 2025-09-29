# IMDB Review Sentiment Analysis

## Project Overview

This project analyzes sentiment in movie reviews from IMDB's Top 250 Movies list. It combines web scraping, natural language processing, and machine learning to classify movie reviews as positive, neutral, or negative.

## Features

- **Data Scraping**: Automated collection of movie metadata and reviews from IMDB Top 250
- **Data Preprocessing**: Comprehensive text cleaning, tokenization, stemming, and lemmatization
- **Sentiment Analysis**: VADER sentiment scoring and classification using machine learning models
- **Data Visualization**: Interactive visualizations including word clouds, distribution plots, and genre analysis
- **Machine Learning**: Multiple classifier comparison (Logistic Regression, Random Forest, XGBoost)

## Dataset

The dataset contains:
- **136,957** movie reviews from IMDB's Top 250 Movies
- Movie metadata: title, year, country, rating, genre, IMDB ID
- Review data: title, content, rating (1-10 scale)
- Sentiment labels: negative (0-4), neutral (5-7), positive (8-10)

## Project Structure

```
group_project_imdb_review/
├── data/
│   └── movies_reviews.csv          # Scraped movie and review data
├── scrape_movies.ipynb             # IMDB data scraping notebook
├── review_sentiment_analysis.ipynb # Sentiment analysis and ML notebook
├── environment.yml                 # Conda environment configuration
└── README.md                       # This file
```

## Installation

### Prerequisite

1. Conda environment manager

### Setup

1. Clone or download this repository
2. Navigate to the project directory
3. Create virtual environment ('imdb_sentiment_analysis_env') for this project and install required dependencies:
```bash
conda env create -f environment.yml
```

## Usage

### 1. Data Scraping (`scrape_movies.ipynb`)

This notebook scrapes data from IMDB Top 250 movies:

- Fetches movie metadata (rank, title, year, country, rating, genre)
- Collects up to 20 pages reviews per movie using GraphQL API
- Exports data to `data/movies_reviews.csv`

### 2. Sentiment Analysis (`review_sentiment_analysis.ipynb`)

This notebook performs comprehensive sentiment analysis:

#### Data Preparation
- Loads and splits data into train/test sets (70/30 split)
- Text preprocessing: cleaning, tokenization, stopword removal
- Stemming and lemmatization for text normalization

#### Exploratory Data Analysis
- Sentiment distribution visualization
- Word cloud generation by sentiment category
- Movie genre and country analysis
- Temporal analysis of movie ratings

#### Machine Learning Pipeline
- **Feature Engineering**: TF-IDF vectors + VADER sentiment scores
- **Class Balancing**: SMOTE for handling imbalanced classes
- **Model Training**: 
  - Logistic Regression (Balanced)
  - Random Forest (Balanced)
  - XGBoost
- **Evaluation**: Confusion matrices and classification reports

## Model Performance

The best performing model achieves the following results:

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|---------|----------|
| **XGBoost** | **82.14%** | 71% | 67% | 69% |
| Random Forest | 81.86% | 75% | 64% | 68% |
| Logistic Regression | 76.68% | 62% | 71% | 66% |

## Key Features

### Text Preprocessing Pipeline
- URL and mention removal
- Special character cleaning
- Stopword filtering
- Porter stemming + WordNet lemmatization
- VADER sentiment scoring

### Visualization Components
- **Word Clouds**: Sentiment-specific adjective visualization
- **Distribution Plots**: VADER compound score distributions
- **Bar Charts**: Genre counts and country distribution
- **Time Series**: Movie ratings by decade

### Machine Learning Features
- **TF-IDF Vectorization**: N-gram features (1-2 grams)
- **Class Balancing**: SMOTE oversampling for minority classes
- **Feature Importance**: XGBoost feature ranking analysis
- **Model Comparison**: Side-by-side performance evaluation

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is for educational purposes.
