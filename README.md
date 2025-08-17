# Analysis of Trading Behavior and Market Sentiment

## 📌 Overview
This project explores the relationship between **cryptocurrency trader performance** and **market sentiment** using historical trading data and the **Bitcoin Fear & Greed Index**.  

The analysis includes:
- Data preprocessing  
- Feature engineering  
- Exploratory Data Analysis (EDA)  
- Predictive modeling (Logistic Regression)  

The goal is to uncover patterns that influence trading profitability and derive insights that can inform **smarter, data-driven trading strategies**.

---

## 📂 Project Directory Structure
```

ds\_/
├── notebook\_1.ipynb           # Main notebook containing the core analysis
├── notebook\_2.ipynb           # (Optional) Additional Colab notebook for supplementary analysis
├── csv\_files/                 # Directory to store all CSV files or data outputs
│   └── \*.csv
├── outputs/                   # Directory to store all visual outputs, graphs, or charts
│   └── \*.png / \*.jpg
├── ds\_report.pdf              # Final summarized insights and explanations
└── README.md                  # Instructions and notes (this file)

````

---

## ⚙️ Prerequisites
To run and validate this project, ensure you have the following installed:

- Python **3.8 or higher**  
- Jupyter Notebook or Google Colab  
- Required Python libraries:  
  ```bash
  pip install pandas numpy matplotlib seaborn scikit-learn
````

* Git (for cloning the repository)
* Access to Google Drive (if datasets are stored there)

---

## 🚀 How to Clone and Run the Project

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/kishankumar1047/ds_Kishan-kumar.git
cd ds_Kishan-kumar
```

### 2️⃣ Set Up the Environment

Create and activate a virtual environment (optional but recommended):

```bash
python -m venv venv
source venv/bin/activate     # On Windows: venv\Scripts\activate
```

Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 3️⃣ Access the Datasets

#### If using **Google Colab**:

* Upload `notebook_1.ipynb` (and `notebook_2.ipynb` if applicable) to Colab.
* Mount Google Drive to access datasets:

  ```python
  from google.colab import drive
  drive.mount('/content/drive')
  ```
* Update file paths in the notebooks to point to:

  ```
  /content/drive/MyDrive/ds_/csv_files/
  ```

#### If running **locally**:

* Place your CSV files in the `csv_files/` directory.
* Update file paths in the notebooks to:

  ```
  ./csv_files/
  ```

---

### 4️⃣ Run the Notebooks

Open `market_sentiment.ipynb` in **Jupyter Notebook** or **Google Colab**:

```bash
jupyter market_sentiment.ipynb
```

Execute the cells in sequence to:

* Load and preprocess datasets
* Perform feature engineering
* Conduct EDA
* Train and evaluate the Logistic Regression model

Visual outputs (boxplots, heatmaps, scatter plots, etc.) will be saved in the **outputs/** directory.


---

## ✅ Validation

To validate the results:

* Cross-check EDA outputs in **outputs/** with findings in the **report**.
* Verify Logistic Regression performance via:

  * Classification Report
  * ROC-AUC Score
* Ensure dataset merging is correct by inspecting the merged DataFrame.
* Re-run specific cells to validate key insights (e.g., relationship between profitability and sentiment).

---

## 📝 Notes

* `ds_report.pdf` contains a summarized version of insights and methodology.
* Save any modified outputs (graphs, CSVs, reports) to the `outputs/` directory to maintain structure.
* For issues or questions, contact the project author: **Kishan Kumar**.

