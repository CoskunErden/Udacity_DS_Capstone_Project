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
Here’s how we can adjust and expand the explanation for your blog:

---

### Dataset Overview: `transcript`

The `transcript` dataset forms a critical component of the analysis by documenting customer interactions with promotional offers. It contains **306,534 entries** and four key columns:

- **`person`**: Represents a unique customer ID.
- **`event`**: Describes the type of interaction, such as `offer received`, `offer viewed`, or `transaction`.
- **`value`**: Stores additional details as a dictionary. For instance, it can include the offer ID for promotional events or the transaction amount for purchases.
- **`time`**: Records the time of the interaction in hours since the start of the test.

Notably, the dataset is complete, with no missing values, ensuring consistency in analysis.

---

### Why This Dataset Matters

This dataset provides a detailed timeline of customer behavior, offering insights into how customers engage with promotions and make transactions. By analyzing the `transcript`, we can uncover trends in offer effectiveness and customer preferences.

---

### Sample Data

Here’s a snapshot of the dataset for better understanding:

| **person**       | **event**       | **value**                                   | **time** |
|-------------------|-----------------|---------------------------------------------|----------|
| 78afa995795e4d85 | offer received  | {"offer_id": "ae264e3637204a6fb9bb56bc8210ddfd"} | 0        |
| 78afa995795e4d85 | offer viewed    | {"offer_id": "ae264e3637204a6fb9bb56bc8210ddfd"} | 6        |
| 78afa995795e4d85 | transaction     | {"amount": 9.64}                           | 12       |

The `value` column is particularly noteworthy for its nested structure, requiring parsing to extract meaningful details for further analysis.

---

### Key Observations

Observations
1. Distribution of Events
![Event Distribution](images/EventDistributions.png)
Transactions are the most common event, with 138,953 occurrences, indicating frequent customer purchases or monetary interactions.
Offer received events follow with 76,277 occurrences, suggesting widespread distribution of promotional offers.
Offer viewed and offer completed events are less frequent (57,725 and 33,579, respectively), indicating a gap between receiving offers and acting on them.


2. Time Analysis
The time column has:
Mean: 366 hours
Median: 408 hours
Range: 0 to 714 hours
A box plot of time (below) shows no extreme outliers, with data evenly distributed over the 714-hour range.
![Time Analysis](images/TimeAnalysis.png)

3. Event Timing Distribution
The histogram (below) reveals:
Peaks in offer received events occur at regular intervals, suggesting scheduled distributions.
Offer viewed and offer completed events are spread more consistently, indicating customer engagement over time.
![Event Timing](images/EventTiming.png)

4. Box Plot by Event
The box plot (below) indicates:
Offer received and offer viewed events have similar time ranges.
Transactions and offer completed events show slightly broader distributions, reflecting more variability in customer responses.
![TimeEvent](images/TimeEvent.png)

By breaking down and preprocessing this dataset, we can generate valuable insights into customer engagement patterns.

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