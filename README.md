# 📊 Employee Attrition Prediction System

## 🎯 Project Overview
Every company loses employees—but losing the wrong employees at the wrong time costs businesses heavily in hiring, training, and lost productivity. 
HR departments spend significant capital every year trying to figure out who is likely to leave and why *before* it happens.

This repository contains an end-to-end Machine Learning system designed to solve the **Employee Attrition Prediction** problem 
using a historical dataset of 1,470 employees. The goal is to identify hidden patterns driving staff departures and translate 
complex machine learning data into actionable corporate policies.

## 📦 Dataset
The project utilizes the widely referenced **IBM HR Analytics Employee Attrition & Performance Dataset**.
* **Source:** [Kaggle Dataset Link](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
* **Scale:** 1,470 rows (employees) and 35 initial data features.

---

## 🚀 Key Pipeline Workflow

### 1. Data Exploration & Imbalance Discovery
* Analyzed data landscape across numeric and text categories.
* Discovered a heavily skewed baseline: **16.12% Attrition Rate (Highly Imbalanced)**. 
* *Why it matters:* Standard models would easily score ~84% accuracy by simply guessing "nobody leaves."
* The code implements explicit adjustments to counteract this bias.

### 2. Preprocessing & Data Cleaning
* Stripped useless/constant features providing zero clue variance (`EmployeeCount`, `Over18`, `StandardHours`, `EmployeeNumber`).
* Converted text targets (`Attrition: Yes/No`) into machine-readable integers (`1/0`).
* Executed **One-Hot Encoding** across categorical text blocks (`Department`, `JobRole`, `MaritalStatus`, etc.).

### 3. Exploratory Data Analysis (EDA)
* Identified that the **Sales Department** sustains the highest departures (~20.6%).
* Isolated **Sales Representatives** as the single highest flight risk role across the company, facing a staggering **~40% exit rate**.
* Uncovered that terminating staff average significantly less income (~$4,787/mo) than long-term stayers (~$6,843/mo).

### 4. Predictive Modeling & Evaluation
Split the data into an 80/20 train/test split (stratified to protect the class ratio) and trained three distinct classifiers:
1. **Logistic Regression** (Baseline & Highly Explainable to Executive Leadership)
2. **Random Forest Classifier** (Ensemble of multi-branch Decision Trees)
3. **Gradient Boosting Classifier** (Sequential Error-Correcting Trees)
   <img width="1692" height="634" alt="Screenshot 2026-06-27 115113" src="https://github.com/user-attachments/assets/6ac04203-fce7-4c6b-8388-fe581dc927c0" />
<img width="1646" height="509" alt="Screenshot 2026-06-27 115127" src="https://github.com/user-attachments/assets/7287fe86-f2e1-4411-a456-bcacaa89f9b0" />
