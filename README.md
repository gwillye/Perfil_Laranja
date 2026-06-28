# Perfil Laranja — Composite Patrimonial Risk Score

> Detection of likely **straw men ("laranjas")** in financial-fraud operations from public & registry data — **without any banking data**.

## 🌎 Real-world context
Developed as **Data Scientist at Neoway** (B3 group — Latin America's largest Data Analytics & AI company), Jan–May 2025. The Loss Prevention team needed to flag individuals suspected of financial fraud using only public/registry data (number of properties, e-mails, addresses, financing, political donations, gender, age, wealth indicators), since direct banking information isn't available.

## 🧠 Approach
- **Feature engineering** over patrimonial / financial / demographic variables.
- **Hierarchical clustering (HDBSCAN)** + **Random Forest** to surface hidden patterns and atypical behavior.
- **Dynamic weights** from cluster separation → an **interpretable Composite Risk Score** per individual.
- **Isolation Forest** models stratified by income band (low / mid / high) for anomaly scoring.

## 📈 Result
- **~82% average accuracy**, ranking individuals by suspicion level.
- Validated and **incorporated into Neoway's compliance/Loss-Prevention product pipeline**, supporting risk analysts in fraud-prevention decisions.

## 📓 Pipeline (notebooks)
`00_HDBSCAN` → `01_DataCollection` → `02_Join` → `03_DataAnalysis` → `04_pre_processing` → `05_Isolation_Forest` → `06–08_Isolation_{low,mid,high}` → `09–11_Composite_Indicator_by_income`.

## 🛠️ Tech
Python · scikit-learn · HDBSCAN · Random Forest · Isolation Forest · PySpark · Pandas

---
*Part of [@gwillye](https://github.com/gwillye)'s portfolio. Author: Gabriel Willye — Data Scientist.*
