# Random Forest Algorithm

This project serves as a comprehensive, structured exploration of the **Random Forest** algorithm across different domains of Machine Learning: **Classification** and **Regression**.
Each subfolder contains a standalone project complete with its own dataset, exploratory data analysis (EDA), model implementation, and performance evaluation.

---

## What is Random Forest?
Random Forest is a versatile, supervised ensemble learning algorithm capable of performing both regression and classification tasks. It operates by constructing a multitude of decision trees during training and outputting either the class with the majority vote (Classification) or the mean/average prediction of the individual trees (Regression).

---

## Core Operational Mechanics:
- Bootstrap Aggregating (Bagging): The algorithm creates multiple random subsets of the original training data (with replacement). A separate decision tree is trained independently on each subset.
- Feature Randomness (Feature Bagging): At each node split in a tree, only a random subset of features is considered. This injects randomness, decorrelates the trees, and significantly reduces model variance.
- Aggregation & Prediction:
  - Classification: Mode of predicted classes (Majority Voting).
  - Regression: Mean of predicted numerical values.

 ---
 
## Random Forest: Pros & Cons:
|  Advantages |  Limitations |
|--------------|---------------|
| **High Accuracy:** Combines multiple trees to outperform individual decision trees. | **Computationally Expensive:** Training dozens or hundreds of trees requires significant processing power and time. |
| **Overfitting Control:** Bagging and feature randomness prevent model overfitting on training data. | **Lower Interpretability:** Acts as a "black box" compared to a single, visualizable decision tree. |
| **Robust to Noise & Outliers:** Handles missing values, outliers, and noisy data gracefully. | **High Memory Consumption:** Storing ensemble structures consumes substantial RAM, especially with deep trees. |
| **Built-in Feature Importance:** Automatically computes and ranks the impact of each feature on predictions. | **Extrapolation Limits:** Cannot predict numerical values outside the range seen in training data (Regression). |
| **No Scaling Required:** Impervious to monotonic feature transformations; no need for StandardScaler or MinMaxScaler. | **Slow Predictions:** Evaluating new instances through hundreds of trees can be slow for real-time applications. |

---

## Classification vs. Regression: When to Use Which?
| Criteria | Random Forest Classifier | Random Forest Regressor|
|--------------|---------------|---------------|
|Target Variable | Categorical / Discrete (e.g., 0 or 1, Yes or No, Cat/Dog) | Continuous / Numerical (e.g., Price, Salary, Temperature, Sales)|
| Decision Rule | Majority Vote (Mode) across all trees | Average (Mean) across all trees |
| Key Splitting Metric | Gini Impurity or Entropy (Information Gain) | Mean Squared Error (MSE) or Mean Absolute Error (MAE) |
| Evaluation Metrics| Accuracy, Precision, Recall, F1-Score, ROC-AUC, Confusion Matrix | RMSE, MAE, R-Squared ($R^2$), MAPE|
| Example Project in Repo | Titanic Passenger Survival Prediction | Residential House Price Prediction |
