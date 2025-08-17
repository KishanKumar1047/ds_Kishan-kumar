### Project Title: Analysis of Trading Behavior and Market Sentiment

#### 1\. Introduction

This project aims to explore the relationship between cryptocurrency trader performance and overall market sentiment. By integrating two primary datasets—historical trading data and a Bitcoin Fear & Greed Index—the objective is to uncover hidden patterns and derive insights that can inform smarter, data-driven trading strategies.

#### 2\. Datasets

The analysis is based on two datasets:

  - **Historical Trader Data:** Contains detailed records of individual trades, including execution prices, trade sizes, profitability (`Closed PnL`), leverage, and timestamps.
  - **Bitcoin Market Sentiment Dataset:** A daily time-series dataset providing a classification of market sentiment (e.g., Fear, Greed, Neutral) for Bitcoin.

#### 3\. Methodology

Our analysis followed a structured, step-by-step data science methodology:

**Step 1: Data Preprocessing and Merging**

  - We loaded both datasets from Google Drive into a Python environment.
  - Column names were cleaned by converting them to lowercase and replacing spaces with underscores (e.g., `Closed PnL` became `closed_pnl`).
  - Date columns in both datasets were standardized to a `datetime` format.
  - The datasets were merged on their common `date` column to create a single, unified DataFrame, linking each trade to the prevailing market sentiment on that day.

**Step 2: Feature Engineering**

  - We created new features to enrich the dataset for deeper analysis:
      - **`profitable`:** A binary flag (True/False) to indicate if a trade resulted in a profit.
      - **`risk`:** A proxy for risk, calculated as the ratio of `size_usd` to `execution_price`.
      - **Time-based Features:** `hour`, `day_of_week`, and `is_weekend` were extracted from the timestamp to capture time-of-day effects.
      - **Cumulative Metrics:** We calculated `cumulative_pnl`, `cumulative_trades`, and `avg_trade_size` per trading account to model a trader's performance history.
      - **Sentiment Features:** The categorical sentiment was mapped to a numerical scale (`sentiment_encoded`), and interaction terms (`sentiment_x_size`, `sentiment_x_pnl`) were created to analyze how trading behavior changes under different sentiment conditions.

**Step 3: Exploratory Data Analysis (EDA)**

  - We used visualizations to understand the data's core relationships:
      - A **boxplot** showed the distribution of profitability (`closed_pnl`) across different market sentiment categories, revealing if traders are more profitable during periods of "Fear" or "Greed."
      - A **correlation heatmap** was generated to quantify the linear relationships between all engineered features and the target variable.
      - **Scatter plots** explored the relationship between profitability and other key metrics like trade size, colored by sentiment, to identify visual patterns.

**Step 4: Predictive Modeling**

  - To predict trade profitability, a **Logistic Regression model** was built.
  - **Data Split:** The dataset was split into training and testing sets to evaluate model performance on unseen data.
  - **Feature Selection:** We selected relevant engineered features (excluding `closed_pnl`) to train the model.
  - **Categorical Encoding:** `side` and `direction` columns were one-hot encoded to be used by the model.
  - **Model Training and Evaluation:** The model was trained on the training data and evaluated using the test set. Key metrics, including a **Classification Report** (Precision, Recall, F1-Score) and the **ROC-AUC Score**, were used to assess its performance.

#### 4\. Key Findings & Insights

*(Note: These are sample findings; you should replace them with your actual results after running the code.)*

  - Our EDA revealed a visible difference in average trade profitability during periods of "Greed" compared to "Fear."
  - The logistic regression model achieved a ROC-AUC score of **[Your ROC-AUC Score Here]**, indicating its ability to predict a profitable trade with a certain degree of accuracy.
  - The model's coefficients suggest that factors like `cumulative_pnl` and `sentiment_encoded` are significant predictors of future trade profitability.
  - We observed that traders tend to [e.g., use higher leverage during periods of 'Fear'], which correlates with [e.g., lower average profits]. This suggests that a strategy of reducing risk during periods of high fear could be beneficial.

#### 5\. Conclusion

This project demonstrates that a trader's performance is not random but is significantly influenced by market sentiment and an individual's trading history. The insights from this analysis can be used to develop more robust trading strategies, such as adapting risk levels or trade sizes based on the prevailing market sentiment.

-----

### Project Directory Structure

```
ds_/
├── notebook_1.ipynb           # Main notebook for all work
├── notebook_2.ipynb           # (Optional) Additional Colab notebook if needed
├── csv_files/                 # Store all CSVs or data outputs here.
│   └── *.csv
├── outputs/                   # Store all visual outputs, graphs, or charts here.
│   └── *.png / *.jpg
├── ds_report.pdf              # Final summarized insights and explanations.
└── README.md                  # Instructions, notes.
```

