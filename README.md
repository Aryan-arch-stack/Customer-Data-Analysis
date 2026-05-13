# 🛒 Customer Data Analysis — RFM Segmentation

A complete end-to-end **RFM (Recency · Frequency · Monetary)** analysis pipeline on a synthetic Indian e-commerce customer dataset of **1,000 customers** and **23,050 transactions**.

---

## 📁 Project Structure

Customer-Data-Analysis/
├── data/
│   ├── Customer_Master_Data.csv
│   └── Customer_Transactions.csv
├── src/
│   └── customer_rfm_analysis.py
├── notebooks/
│   └── Customer_RFM_Analysis.ipynb
├── outputs/
│   ├── plot1_segment_distribution.png
│   ├── plot2_monetary_pie.png
│   ├── plot3_recency_vs_monetary.png
│   ├── plot4_pareto.png
│   └── rfm_results.csv
├── requirements.txt
└── README.md

---

## 📊 Dataset Overview

| File | Rows | Columns | Key Fields |
|------|------|---------|------------|
| Customer_Master_Data.csv | 1,000 | 9 | CustomerID, Name, Gender, Age, City, MaritalStatus, JoinDate |
| Customer_Transactions.csv | 23,050 | 3 | CustomerID, TransactionDate, TransactionAmount |

---

## 🔄 Analysis Pipeline

| Step | Description |
|------|-------------|
| 1 | Load Data — read both CSVs into pandas DataFrames |
| 2 | Clean Data — parse dates, check nulls and duplicates |
| 3 | Merge — left-join transactions with customer master |
| 4 | RFM Metrics — compute Recency, Frequency, Monetary per customer |
| 5 | RFM Scoring — quintile-based 1 to 5 scores for each dimension |
| 6 | Segment Code — concatenate R+F+M scores (e.g. 555) |
| 7 | Segment Labels — map codes to business-friendly labels |
| 8 | Visualisations — bar chart, pie chart, scatter plot, Pareto curve |

---

## 🏷️ Customer Segments

| Segment | Definition | Count |
|---------|-----------|-------|
| 🏆 Champions | Score = 555 (best in all 3 dimensions) | 35 |
| 💸 Big Spenders | M-score = 5 | 165 |
| 🕐 Recent | R-score = 5 | 160 |
| 🔁 Frequent | F-score = 5 | 63 |
| ☠️ Lost | Score = 111 (worst in all 3 dimensions) | 34 |
| 🔘 Others | Everything else | 543 |

---

## 📈 Key Findings

- Top 20% of customers contribute only 27% of revenue — this dataset does not follow the classic Pareto 80/20 rule, indicating a relatively even revenue distribution.
- Big Spenders and Recent customers are the two largest named segments.
- Champions (only 35 customers) represent the highest-value, most engaged cohort — ideal targets for loyalty programmes.
- The Recency vs Monetary scatter shows that high monetary value is concentrated among customers who purchased recently.
