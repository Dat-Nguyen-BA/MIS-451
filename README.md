📘 Hotel Booking Cancellation Prediction

# MIS 451 – Machine Learning for Business
## Becamex Business School

# 📌 Overview

This project builds predictive Machine Learning and Deep Learning models to determine whether a hotel booking will be canceled or completed. With a cancellation rate of nearly 37%, hotels experience significant revenue loss and operational inefficiencies. By developing a robust prediction system, hotels can optimize inventory, reduce overbooking risks, and improve revenue management.

This repository contains the full pipeline, from data preprocessing and EDA to machine learning models, deep learning models, and business recommendations.

📂 Repository Structure

📁 Hotel-Cancellation-Prediction

├── [📄 Group 3A_MIS 451_Code.ipynb]([url](https://github.com/Dat-Nguyen-BA/MIS-451/blob/main/Group%203A_MIS%20451_Final%20Project/Group%203A_MIS%20451_Code.ipynb))

├── [📄 Group 3A_MIS 451_Report.pdf]([url](https://github.com/Dat-Nguyen-BA/MIS-451/blob/main/Group%203A_MIS%20451_Final%20Project/Group%203A_MIS%20451_Report.pdf))

├── 📄 README.md                      # Project documentation

# 🎯 Project Objectives

Predict hotel booking cancellations using ML and DL models.

Help hotels implement:

  - Smarter overbooking strategies
  
  - Targeted retention incentives
  
  - Better resource planning
  
  - Reduce lost revenue caused by unexpected cancellations.

# 🧠 Business Context

The hospitality industry faces:

  - Volatile cancellation rates
  
  - Overbooking risks
  
  - Revenue leakage from unused inventory
  
  - Misalignment between forecasted and actual check-ins

Stakeholders affected:

  - Hotel Management – occupancy, ADR
  
  - Revenue Managers – pricing, yield management
  
  - Operations/Front Desk – staffing, room assignment
  
  - This project provides data-driven insight to strengthen decision-making.

# 📊 Dataset

Source: Antonio et al. (2019), “Hotel booking demand datasets”

Period: July 2015–August 2017

Size: 119,390 bookings

Variables: 32 features

Target variable: is_canceled (0 = not canceled, 1 = canceled)

Key variables include:

  - Lead time
  
  - Market segment
  
  - Deposit type
  
  - Customer history
  
  - Special requests
  
  - Assigned room type

# 🔎 Exploratory Data Analysis (EDA)
Key Findings:

Cancellation rate: ~37%

High-risk sources: Online TA, Groups

Q2 anomaly: Highest cancellation in April–June

Lead time effect: Long-term bookings (>90 days) show highest risk

Deposit anomaly: Some “Non-refundable” segments reached 99% cancellation

Passive guests: Bookings with zero changes are the most unstable

Customer history: Past cancellations strongly predict future ones

# 🛠️ Data Preprocessing

Steps performed:

1. Removed 31,994 duplicates

2. Handled missing values using:

3. Mean imputation

4. Random Forest imputation

5. Dropping columns with >90% missing (e.g., company)

6. Removed unrealistic outliers

7. One-hot encoded 10 categorical variables → dataset expanded to 231 features

8. Train/test split: 80/20

9. Scaling applied for Logistic Regression models

10. Handled imbalance via monitoring precision/recall trade-offs

# 🤖 Machine Learning Models
## 1️⃣ Random Forest

Accuracy: 76%

Strong recall (detecting cancellations)

Lower precision → many false positives

## 2️⃣ XGBoost

Accuracy: 82% (best ML model)

Balanced precision & recall

Handles high-dimensional data effectively

## 3️⃣ Logistic Regression

Accuracy: 74%

Performs moderately, limited by nonlinear relationships

## 🧬 Deep Learning Model
Architecture

Feedforward Neural Network (4 layers)

Dropout (0.3)

Adam optimizer

Binary Cross-entropy loss

Early stopping (patience: 5 epochs)

Performance

Test Accuracy: 83.15%

Class 0 (Not canceled): Precision 0.87 | Recall 0.90  
Class 1 (Canceled):     Precision 0.71 | Recall 0.65  


The DL model is competitive with XGBoost but still suffers from lower recall for cancellation cases.

📈 Model Comparison
Model	Accuracy	Strength
XGBoost	⭐ 82%	Best performing, balanced metrics
Random Forest	76%	High recall, lower precision
Logistic Regression	74%	Simple baseline model
Deep Learning	⭐ 83.15%	Best overall accuracy
