# Classification-Using-Ensemble-Techniques
---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Feature Description](#feature-description)
4. [Data Preprocessing](#data-preprocessing)
5. [Data Visualization Insights](#data-visualization-insights)
6. [Model Building & Performance](#model-building-&-performance)
7. [Feature Importance Analysis](#feature-importance-analysis)
8. [Conclusion](#conclusion)

---

## Project Overview

This project applies different ensemble and classification techniques to predict whether a client will subscribe to a term deposit. The models are evaluated using various metrics and compared for model selection.

---

## Dataset

The dataset used in this project is the Bank Marketing Campaign dataset available on Kaggle. It consists of various client attributes and details from marketing campaigns.

Number of Features: 17

Number of Rows: 45,211

---

## Feature Description

1. age: Age of the client.

2. job: Type of job (e.g., management, technician, entrepreneur).

3. marital: Marital status (e.g., single, married, divorced).

4. education: Level of education (e.g., primary, secondary, tertiary, unknown).

5. default: Has credit in default? (yes, no).

6. balance: Average yearly balance in euros.

7. housing: Has housing loan? (yes, no).

8. loan: Has personal loan? (yes, no).

9. contact: Contact communication type (unknown, telephone, cellular).

10. day: Last contact day of the month.

11. month: Last contact month of the year.

12. duration: Last contact duration in seconds.

13. campaign: Number of contacts performed during this campaign.

14. pdays: Number of days since the client was last contacted from a previous campaign (-1 means the client was not previously contacted).

15. previous: Number of contacts performed before this campaign.

16. poutcome: Outcome of the previous marketing campaign (unknown, other, failure, success).

17. Target: Whether the client has subscribed to a term deposit (yes, no).

---

## Data Preprocessing

### Handling Missing Values and Less Informative Outcomes

- Removed Rows: Rows where the poutcome column had the value 'other' were removed due to lack of meaningful information.

- Replaced 'Unknown' Values: In the job and education columns, instances of 'unknown' were replaced with 'other' to reduce the number of unique categories.

### Outlier Handling

- Identified Outliers: Used Z-score standardization to detect outliers in the balance column.

- Removed Outliers: Rows with outlier values were removed to prevent model performance issues.

### Encoding Categorical Variables

- Label Encoding: Converted all categorical features into numerical values for compatibility with machine learning algorithms.

---

## Data Visualization Insights

- Age Distribution: The majority of customers were aged 25-40, with a normal-like distribution.

- Balance Variability: High standard deviation in balance values indicated diverse financial standings.

- Call Duration: Most calls were short, with some long-duration calls considered as outliers.

- Campaign Effectiveness: Fewer calls correlated with higher subscription rates, indicating that excessive calls could deter potential customers.

---

## Model Building & Performance

### Classification Models Used

Six models were trained and evaluated:

#### 1. Decision Tree Classifier

- Accuracy: 87.59%

- F1 Score: 87.62%

- Prone to overfitting.

#### 2. Random Forest Classifier

- Accuracy: 89.41%

- F1 Score: 85.79%

- Reduced overfitting with ensemble learning.

#### 3. AdaBoost Classifier

- Accuracy: 89.24%

- F1 Score: 87.80%

- Improved balance between accuracy and recall.

#### 4. Bagging Classifier

- Accuracy: 89.88%

- F1 Score: 88.90%

- Reduced variance and improved model stability.

#### 5. Gradient Boosting Classifier

- Accuracy: 89.87%

- F1 Score: 87.44%

- Sequentially corrected errors for better predictions.

#### 6. Voting Classifier (Best Model)

- Accuracy: 90.50%

- F1 Score: 89.34%

- Combined strengths of multiple models for the best performance.

---

## Feature Importance Analysis

- Call duration consistently emerged as the most significant feature across all models.

- Poutcome, month, and age also contributed significantly to predictions.

- Other features like campaign, housing loan, and balance played a lesser role.

--- 

## Conclusion

- The Voting Classifier was the best-performing model, leveraging multiple classifiers for optimal predictions.

- Call duration, previous contacts, and month were the most influential features in predicting campaign success.

- Insights from this study can help banks refine their marketing strategies by optimizing contact frequency and targeting the most relevant customers.
