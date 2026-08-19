# 🎬 Predicting Movie Success

Predict whether a movie will be a **Hit**, **Average**, or **Flop** using Exploratory Data Analysis, Feature Engineering, Categorical Label Encoding, Standard Scaling, and Machine Learning Classification Models.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Rohan-Rg30/Predicting_Movie_Success/blob/main/Notebook/Predicting_Movie_Success.ipynb)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikitlearn)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)](https://pandas.pydata.org/)
![License](https://img.shields.io/badge/License-Proprietary-lightgrey)
[![Status](https://img.shields.io/badge/status-active-success)](https://github.com/Rohan-Rg30/Predicting_Movie_Success)

---

## 📌 Overview

The film industry involves high-stakes financial investments where predicting box office performance and critical reception before or upon release is invaluable for studios, distributors, and investors. This project builds a complete end-to-end Machine Learning pipeline to classify movies into success tiers based on historical metadata.

By engineering target classes from IMDb scores and analyzing key factors such as budget, gross revenue, cast popularity, and movie duration across **5,043 titles**, this repository demonstrates data cleaning, categorical encoding, feature scaling, model benchmarking, and comparative performance visualization.

---

## 🎯 Key Results

Models were evaluated on a held-out **20% stratified test set** (**1,009 movies**). Features were standardized using `StandardScaler` fitted on the training split to maintain data integrity.

| Model | Accuracy | Precision (Weighted) | Recall (Weighted) | F1-Score (Weighted) |
|---|---|---|---|---|
| $\color{cyan}{\text{**Random Forest Classifier**}}$ 🏆 | **0.730** | **0.710** | **0.730** | **0.710** |
| Logistic Regression | 0.661 | 0.486 | 0.661 | 0.550 |

**🏆 Best Model:** $\color{cyan}{\text{**Random Forest Classifier**}}$ — Achieved **73.0% overall accuracy** and an **F1-score of 0.710**, significantly outperforming baseline linear classification.

### Class-Wise Performance breakdown (Random Forest)

| Target Class | IMDb Rating Range | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|---|
| **Class 0 (Average)** | 3.0 < Score ≤ 6.0 | 0.60 | 0.38 | 0.46 | 308 |
| **Class 1 (Flop)** | Score ≤ 3.0 | 1.00 | 0.00 | 0.00 | 9 |
| **Class 2 (Hit)** | Score > 6.0 | 0.76 | 0.90 | 0.82 | 692 |

---

## 🧠 What This Project Demonstrates

- **Target Engineering**: Categorized raw `imdb_score` into meaningful discrete business classes (`Flop` ≤ 3.0, `Average` 3.0–6.0, `Hit` > 6.0).
- **Missing Value Imputation**: Handled missing entries across numerical variables (`duration`, `gross`, `budget`) using mean strategy.
- **Categorical Encoding**: Implemented `LabelEncoder` to transform high-cardinality categorical attributes (`director_name`, `actor_1_name`, `language`, `country`) into machine-readable numeric formats.
- **Data Preprocessing & Scaling**: Stratified $80/20$ train-test splitting combined with `StandardScaler` feature normalization.
- **Model Evaluation & Metrics**: Evaluated classification performance using Accuracy, Precision, Recall, F1-score, Confusion Matrix, and pairplot feature relationships.

---

## 📂 Dataset

**Dataset:** IMDb 5000 Movie Dataset (`movie_metadata.csv`)

| Property | Value |
|---|---|
| Total Entries | 5,043 movies |
| Total Columns | 30 attributes |
| Test Set Size | 1,009 samples (20%) |
| Target Variable | `Classify` (`Hit`, `Average`, `Flop`) |

### Selected Model Features (`feature_columns`)

| Feature | Description |
|---|---|
| `director_name` | Name of the lead director (Label Encoded) |
| `duration` | Total film runtime in minutes |
| `actor_1_name` | Name of the primary lead actor (Label Encoded) |
| `budget` | Estimated production budget in USD |
| `gross` | Total gross revenue in USD |
| `language` | Original language of the movie (Label Encoded) |
| `country` | Country of production origin (Label Encoded) |

---

## 🛠️ Tech Stack

| Category | Tools & Libraries |
|---|---|
| Language | Python 3.10+ |
| Data Processing | pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | scikit-learn (RandomForestClassifier, LogisticRegression) |
| Preprocessing | LabelEncoder, StandardScaler, train_test_split |
| Environment | Jupyter Notebook / Google Colab |

---

## 📁 Repository Structure

.
├── Notebook/
│   └── Predicting_Movie_Success.ipynb    # Full Data Science Pipeline Notebook
└── README.md                             # Project Documentation


---

## 🚀 Quick Start

### 1 — Run in Google Colab
Click the **"Open In Colab"** badge at the top of this README to execute the notebook instantly.

### 2 — Run Locally

```bash
# 1. Clone the repository
git clone [https://github.com/Rohan-Rg30/Predicting_Movie_Success.git](https://github.com/Rohan-Rg30/Predicting_Movie_Success.git)
cd Predicting_Movie_Success

# 2. Create and activate virtual environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# 3. Install required dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# 4. Launch Jupyter Notebook
jupyter notebook Notebook/Predicting_Movie_Success.ipynb


💡 Key Project Insights
Dominance of High Ratings: The majority of movies in the dataset fall into the Hit category (imdb_score > 6), causing class imbalance with extremely few instances of severe Flops (imdb_score ≤ 3).

Ensemble vs Linear Performance: Non-linear tree ensembles like Random Forest (73.0% accuracy) far outperform linear models like Logistic Regression (66.1% accuracy), capturing non-linear interactions between director history, budget, and revenue.

Feature Correlation: Film duration and gross revenue show strong visual separation across success categories in pairplot distributions.


🗺️ Roadmap / Future Work
[ ] Implement class imbalance handling strategies (e.g., SMOTE / Class Weights) to improve detection of minority classes (Flops).

[ ] Incorporate advanced gradient boosting algorithms (XGBoost, LightGBM, CatBoost).

[ ] Perform hyperparameter optimization using GridSearchCV / RandomizedSearchCV.

[ ] Expand feature selection to include genres, cast_total_facebook_likes, and plot_keywords.

[ ] Build a web UI dashboard using Streamlit to predict movie success for upcoming titles.

```
---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome. Feel free to check the [issues page](https://github.com/Rohan_Rg30/Predicting_Hotel_Reservation_Cancellations/issues) or open a pull request.

## 📜 License

**© Spinnaker Analytics**. All rights reserved.
This project was assigned by Spinnaker Analytics and is the property of Spinnaker Analytics. It is shared publicly on GitHub for portfolio/demonstration purposes only. No part of this code, dataset pipeline, or documentation may be copied, redistributed, or used commercially without written permission from Spinnaker Analytics.

## 🙋 Author

**Rohan Gaikwad — Data Scientist & AI Specialist** - [LinkedIn](https://www.linkedin.com/in/rohan-gaikwad-8b1976418)

---
<p align="center">⭐ If you found this project useful, consider giving it a star!</p>
