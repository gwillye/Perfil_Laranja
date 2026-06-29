# Perfil Laranja: Composite Patrimonial Risk Score

This project detects likely straw men ("laranjas") in financial-fraud operations using only public and registry data, without any banking information.

## Context

I built this as a Data Scientist at a large data-analytics company, between January and May 2025. The Loss Prevention team needed a way to flag individuals suspected of financial fraud, but they could not use direct banking data. The only signals available were public and registry sources: number of properties, e-mails, addresses, financing, political donations, gender, age, and other wealth indicators. The challenge was to turn that scattered information into a single, interpretable score that risk analysts could actually act on.

## Approach

The pipeline combines a few techniques on top of careful feature engineering over patrimonial, financial, and demographic variables:

- Hierarchical clustering with HDBSCAN plus a Random Forest to surface hidden patterns and atypical behavior.
- Dynamic weights derived from cluster separation, which feed an interpretable Composite Risk Score for each individual.
- Isolation Forest models stratified by income band (low, mid, high) for anomaly scoring, so that "unusual" is judged relative to peers in the same wealth range rather than across the whole population.

## Results

The model reaches around 82% average accuracy when ranking individuals by their level of suspicion. It was validated and incorporated into the company's compliance and Loss Prevention product pipeline, where it supports risk analysts in day-to-day fraud-prevention decisions.

## Pipeline

The work is organized as a sequence of notebooks:

`00_HDBSCAN` -> `01_DataCollection` -> `02_Join` -> `03_DataAnalysis` -> `04_pre_processing` -> `05_Isolation_Forest` -> `06-08_Isolation_{low,mid,high}` -> `09-11_Composite_Indicator_by_income`.

## Tech

Python, scikit-learn, HDBSCAN, Random Forest, Isolation Forest, PySpark, Pandas.

---

Part of [@gwillye](https://github.com/gwillye)'s portfolio. Author: Gabriel Willye, Data Scientist.
