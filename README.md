# Elon Musk Tweets & Tesla Stock Analysis

## Project Overview
This project investigates the potential correlation between Elon Musk's Twitter activity, general public sentiment on Twitter regarding Tesla, and Tesla's (TSLA) stock market performance. The analysis spans data from late 2021 to early 2023, covering significant periods including Tesla's market cap hitting $1 trillion and Elon Musk's acquisition of Twitter.

## Objectives
*   **Impact of Engagement:** Determine if there is a statistical relationship between Elon Musk's tweet metrics (retweets, favorites) and TSLA stock price.
*   **Sentiment Analysis:** Analyze the sentiment of tweets specifically mentioning "TSLA" to see if public sentiment correlates with stock movements.
*   **Event Analysis:** Visualize these relationships around critical dates and news events.

## Data Sources
The project utilizes the following datasets:
*   **`elon_musk_tweets.csv`**: Dataset containing Elon Musk's tweets (2022-2023), including engagement metrics.
*   **`Tasla_Stock_Updated_V2.csv`**: Historical stock data for Tesla (TSLA), including Open, High, Low, and Close prices.
*   **`stock_tweets.csv`**: A large collection of tweets from 2021-2022 that specifically mention Tesla stocks, used for sentiment analysis.

## Methodology

### 1. Data Preprocessing
*   **Cleaning:** Removal of irrelevant metadata (user location, source, etc.) and handling of missing values.
*   **Alignment:** Filtering and aligning disparate datasets (Tweets vs. Stock Market data) by date ranges to ensure accurate comparison.
*   **Aggregation:** Grouping tweet data by day to correspond with daily stock market closings.

### 2. Sentiment Analysis (NLP)
*   Utilized **NLTK's VADER (Valence Aware Dictionary and sEntiment Reasoner)** to compute sentiment scores for individual tweets.
*   Generated a **Compound Score** (-1 to 1) for each tweet to quantify positivity or negativity.
*   Developed an **Aggregate Daily Score** metric: `(Average Daily Sentiment) * (Daily Tweet Count)` to weight sentiment by volume.

### 3. Statistical Analysis
*   **Correlation Matrices:** Calculated Pearson correlation coefficients to quantify relationships:
    *   Elon's Tweet Engagement (Retweets/Favorites) vs. TSLA Stock Price.
    *   Aggregate Public Sentiment vs. TSLA Stock Price.
*   **Normalization:** Applied **Min-Max Scaling** (via Scikit-learn) to normalize stock prices and sentiment scores to a 0-1 scale, allowing for direct visual comparison of trends.

## Key Findings
*   **Elon's Tweets:** Analysis showed a relatively weak correlation (approx. **0.27 - 0.30**) between the raw number of retweets/favorites on Elon Musk's tweets and the stock price.
*   **Public Sentiment:** A moderate correlation (approx. **0.417**) was observed between the aggregated sentiment of general public tweets and TSLA's daily high stock price.
*   **Visual Trends:** Graphical analysis highlights that sentiment trends often mirror stock performance, with notable peaks coinciding with major news events (e.g., Oct 2021 Market Cap milestone).

## Technologies Used
*   **Python 3.x**
*   **Pandas & NumPy:** Data manipulation and numerical operations.
*   **Matplotlib & Seaborn:** Visualization (Time-series plots, Heatmaps, Scatter plots).
*   **NLTK (Natural Language Toolkit):** Sentiment analysis.
*   **Scikit-learn:** Data preprocessing (MinMaxScaler).

## How to Run
1.  Clone the repository.
2.  Install dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn nltk scikit-learn
    ```
3.  Open the main analysis notebook:
    ```bash
    jupyter notebook "312 Final.ipynb"
    ```
4.  Run the cells sequentially to reproduce the analysis and visualizations.
