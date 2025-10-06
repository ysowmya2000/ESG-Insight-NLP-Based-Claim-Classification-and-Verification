# ESG-Insight: NLP-Based Claim Classification and Verification

This project focuses on analyzing sustainability claims made by companies in their ESG (Environmental, Social, and Governance) reports. Using Natural Language Processing (NLP), it classifies statements into ESG categories (e.g., carbon, renewable energy, diversity) and flags unverifiable claims to support transparency and accountability in corporate reporting.

---
## Project Overview

Corporate ESG reports are rich in textual claims about sustainability initiatives, but verifying and categorizing these claims manually is time-consuming and subjective.  
This project aims to:

- Classify ESG-related claims into predefined sustainability categories using transformer-based NLP embeddings.
- Detect unverifiable or vague claims that lack measurable evidence.
- Provide an interactive dashboard to visualize company rankings and ESG claim distribution.

---

## Dataset Description

The dataset used in this project is sourced from **Kaggle – ESG Sustainability Reports of S&P 500 Companies**. It contains textual claims extracted from corporate sustainability and ESG disclosures.

### Key Characteristics:
- Number of records: ~5,000 statements (varies by source)
- **Columns:**
  - Company: Name of the organization  
  - Text: ESG statement or claim from reports  
  - Year: Year of report publication  
  - (Optional) Category: ESG domain (if available)

If category labels are unavailable, this project uses keyword-based mapping to classify text into five categories:

1. Carbon & Emissions  
2. Renewable Energy  
3. Water & Waste Management  
4. Diversity & Inclusion  
5. Other Sustainability Claims  

**Dataset Source:**  
[Kaggle – ESG Sustainability Reports of S&P 500 Companies](https://www.kaggle.com/datasets/synful/world-esg-sustainability-reports)

---

## 🎯 Objectives

- Accurately classify sustainability-related text into ESG categories.  
- Detect unverifiable claims (e.g., “We care for the planet”) using rule-based analysis.  
- Visualize category distribution and claim verification using interactive dashboards.  

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Cleaned text by lowercasing, removing punctuation, and normalizing whitespace.  
- Prepared text for NLP embedding using a custom cleaning function.

### 2. Text Embedding
- Utilized **SentenceTransformer (all-MiniLM-L6-v2)** to convert ESG claims into 384-dimensional semantic vectors.

### 3. Model Training
- Split data into 80% training and 20% testing.  
- Trained a **Random Forest Classifier** on embeddings to predict ESG categories.  
- Saved the trained model using `pickle`.

### 4. Evaluation
- Evaluated model using **Precision, Recall, F1-score, and Confusion Matrix**.  
- Achieved **Macro F1-score = 0.81** across five ESG categories.

### 5. Visualization & Dashboard
- Created interactive charts using **Plotly** for ESG category distribution.  
- Built a **Streamlit dashboard** to:  
  - Display ESG claim categories.  
  - Rank companies based on sustainability focus.  
  - Highlight unverifiable claims for review.

---

## Libraries Used

- `pandas` – Data manipulation and preprocessing  
- `numpy` – Numerical computations  
- `matplotlib`, `seaborn`, `plotly` – Visualization  
- `scikit-learn` – ML algorithms and evaluation metrics  
- `sentence-transformers` – Text embeddings  
- `streamlit` – Dashboard interface  
- `pickle` – Model storage and reuse  

---

## Evaluation Metrics

- **F1-Score:** Balances precision and recall for fair performance evaluation.  
- **Confusion Matrix:** Evaluates per-class prediction accuracy.  
- **Macro F1-Score (0.81):** Demonstrates balanced classification across ESG categories.

---

## Results

- Random Forest model achieved **Macro F1-score = 0.81**.  
- Dashboard visualizes ESG claim distribution and identifies unverifiable statements.  
- Demonstrates potential of NLP to automate ESG data analysis and enhance transparency in sustainability reporting.

---

## 📚 Dataset
[Kaggle – ESG Sustainability Reports of S&P 500 Companies](https://www.kaggle.com/datasets/synful/world-esg-sustainability-reports)

---

## Author
**Sowmya Yerraguntla**  
Developed as part of a Data Science portfolio project.
