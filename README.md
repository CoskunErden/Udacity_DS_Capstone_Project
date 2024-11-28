# Udacity Data Science Capstone Project

[Visit the Blog for Full Details](https://coskunerden.github.io/Udacity_DS_Capstone_Project/)

## Project Overview

This project is part of the Udacity Data Science Capstone. It focuses on analyzing customer behavior using simulated Starbucks data. The goal is to determine how different demographic groups respond to various types of offers and develop strategies to target customers more effectively.

## Objective

1. Analyze customer interactions with offers.
2. Build models to predict customer responses based on demographics and behavioral data.
3. Create actionable strategies for sending targeted offers to customers.

## Key Components

The data used in this project comes from three JSON files:

- **portfolio.json**: Contains details about the offers, such as type, difficulty, reward, and duration.
- **profile.json**: Includes customer demographic information, such as age, gender, and income.
- **transcript.json**: Tracks customer transactions and interactions with offers, such as when offers were received, viewed, and completed.

## Libraries Used

The following libraries and packages were used in this project:

- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical operations.
- **Math**: For mathematical computations.
- **JSON**: For handling JSON data files.
- **Matplotlib**: For data visualization.
- **Seaborn**: For advanced data visualization.
- **Scikit-learn**:
  - **SimpleImputer**: For handling missing data.
  - **ColumnTransformer**: For preprocessing data using pipelines.
  - **OneHotEncoder**: For encoding categorical features.
  - **StandardScaler**: For feature scaling.
  - **Train-test Split**: For splitting data into training and test sets.
  - **GridSearchCV** and **RandomizedSearchCV**: For hyperparameter tuning.
  - **LogisticRegression**, **RandomForestClassifier**, **GradientBoostingClassifier**, and **SVC**: For building and evaluating machine learning models.
  - **Metrics**: For evaluating model performance (accuracy, confusion matrix, precision, recall, F1 score).
- **Scipy**:
  - **Uniform and Randint**: For generating random values during hyperparameter tuning.
- **XGBoost**: For advanced gradient boosting implementation.
- **Matplotlib Inline**: For rendering plots within Jupyter Notebook.

## Files in the Repository

- **data/portfolio.json**: Contains offer details.
- **data/profile.json**: Contains customer demographic information.
- **data/transcript.json**: Tracks customer transactions and interactions with offers.
- **notebooks/Starbucks_Capstone_notebook.ipynb**: The main Jupyter Notebook containing the project code, analysis, and visualizations.
- **README.md**: Project documentation, including objectives, key components, and results.
- **results/feature_importance.csv**: Exported feature importance scores from the model for analysis.

## Summary of Results

1. **Best Model**:
   - The **Gradient Boosting Classifier** was identified as the best-performing model.
   - **Key Metrics**:
     - F1 Score (minority class): 0.61
     - Overall accuracy: 91%

2. **Actionable Insights**:
   - Optimize offer timing: Focus on sending offers at times most likely to drive engagement.
   - Simplify offers: Reduce offer difficulty while maintaining reasonable durations.
   - Enhance rewards: Boost reward attractiveness to marginally improve outcomes.
   - Focus on behavioral patterns rather than demographics for targeting.

3. **Feature Importance**:
   - The most important features for predicting offer completion were:
     - Time since the start of the test.
     - Duration and difficulty of offers.
     - Reward amount.

## Future Work

- Extend the analysis to include additional behavioral insights, such as channel usage.
- Perform additional feature engineering to capture latent variables.
- Explore unsupervised learning techniques for customer segmentation.

## License

This project is licensed under the MIT License.


