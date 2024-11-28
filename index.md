---
title: Starbucks Capstone Project
layout: default
---

# Starbucks Capstone Project


**Author:** Coskun Erden  
**Date:** 11/27/2024  

---

## Executive Summary  
This project focuses on the Starbucks Capstone Challenge, which simulates customer purchasing decisions influenced by promotional offers. The challenge explores how machine learning models can predict offer completion rates and provide actionable strategies to optimize marketing performance.  

- **Best Model:** Gradient Boosting, achieving an accuracy of 91% and an F1-Score of 0.61 for the minority class.  
- **Key Insights:** Behavioral factors such as timing and offer duration significantly influence completion rates, while demographic attributes like age and gender have a minimal effect.  
- **Actionable Strategies:** Recommendations include simplifying offers, targeting high-value customers, and leveraging multi-channel communication to maximize engagement.  

---

## Project Overview  

### Background  
Promotional offers are a cornerstone of marketing strategies, designed to boost customer engagement and increase sales. However, their effectiveness often depends on how well they resonate with customers. This project aims to optimize these campaigns by identifying which offers work best for different customer groups and developing a data-driven approach to improve offer completion rates.  

### Datasets  
The analysis relies on three key datasets:  

1. **Profile Dataset:**  
   - **Size:** 17,000 users  
   - **Attributes:** Age, gender, income, and membership start date  

2. **Portfolio Dataset:**  
   - **Size:** 10 promotional offers  
   - **Attributes:** Offer type, reward, difficulty, duration, and delivery channels  

3. **Transcript Dataset:**  
   - **Size:** 306,648 event logs  
   - **Attributes:** Events (e.g., offers received, viewed, completed), timestamps, user IDs, and monetary values  

The primary goal is to identify the most responsive customer groups and optimize offer presentation strategies to maximize effectiveness.  

---

## Data Preparation  

### Preprocessing  
1. **Handling Missing Values:**  
   - **Gender:** Replaced missing values with "Unknown"  
   - **Age:** Imputed median values for ages encoded as 118  
   - **Reward Earned:** Set to 0 for events without rewards  

2. **Feature Engineering:**  
   - **Channel Indicators:** Created binary variables for delivery channels (web, email, mobile, social)  
   - **Age Categories:** Grouped ages into bins such as 'Young Adult,' 'Mid-Career,' and 'Senior'  
   - **Offer Completed:** Added a binary indicator for successful offer completions  

3. **Scaling and Encoding:**  
   - Normalized continuous variables such as income and duration using StandardScaler  
   - One-hot encoded categorical features like gender and offer type  

### Exploratory Data Analysis  
- **Correlations:**  
![Correlation Heatmap](images/CorrelationReport.png)
  Timing and duration exhibited strong correlations with offer completion rates. Longer durations and well-timed offers are more likely to succeed.  

- **Event Analysis:**  
  A significant drop-off was observed between offers viewed and completed, highlighting areas for optimization.  

- **Demographic Trends:**  
  - Gender distribution was nearly even, with males completing slightly more discount offers.  
  - Customers in the 'Mid-Career' age group demonstrated higher completion rates.  

---

## Methodology  

### Feature Selection  
Key features included:  
- **Continuous:** Time, duration, difficulty, income  
- **Categorical:** Offer type, age categories, gender, channel indicators  

### Models Evaluated  
1. **Logistic Regression:** A baseline model for comparison.  
2. **Random Forest:** Robust but less effective with imbalanced datasets.  
3. **Gradient Boosting:** Best performer with balanced metrics.  
4. **SVM:** Struggled with class imbalance.  
5. **XGBoost:** Strong alternative with high recall.  

### Evaluation Metrics  
1. **Accuracy:** Measures overall correctness but can be misleading in imbalanced datasets.  
2. **F1-Score:** Balances precision and recall, critical for the minority class.  
3. **Precision & Recall:** Evaluate false positives and negatives, respectively.  

---

## Results  

### Model Performance  

![Model Performance](images/ModelPerformanceSummary.png)

### Insights  
1. Gradient Boosting achieved the best balance between precision, recall, and F1-Score, making it ideal for handling class imbalance.  
2. Timing and duration emerged as the most important factors influencing offer completion.  

---

## Recommendations  

### Short-Term Actions  
1. Deploy Gradient Boosting predictions for upcoming campaigns.  
2. Simplify offers to reduce difficulty levels and extend durations.  
3. Optimize timing based on customer activity patterns.  

### Long-Term Strategies  
1. Incorporate advanced sampling techniques like SMOTE to address class imbalance.  
2. Develop dynamic recommendation systems for personalized offer targeting.  
3. Analyze seasonal trends to align campaigns with peak activity periods.  

---

## Conclusion  
This project demonstrates the effectiveness of using machine learning to enhance marketing strategies. By focusing on behavioral insights and deploying Gradient Boosting, businesses can improve offer completion rates and achieve higher ROI. Future efforts should explore advanced techniques like dynamic personalization and external data integration to refine predictions further.  

---

## References  
- [Scikit-learn Documentation](https://scikit-learn.org/)  
- [Dataset Source](https://github.com/CoskunErden/Udacity_DS_Capstone_Project)  

---