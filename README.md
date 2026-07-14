# Random Forest Regression

## What is Random Forest Regression?
Random Forest Regression is an ensemble learning method that builds multiple decision trees and merges their predictions together to get a highly accurate and stable numerical estimate.

## How It Works:
1. **Bootstrap Sampling**: It creates random subsets of your dataset (with replacement) to train each individual tree.
2. **Feature Bagging**: At each split in a tree, it only considers a random subset of features. This ensures the trees are diverse and uncorrelated.
3. **Averaging**: Every tree makes its own prediction, and the final output is the mathematical average of all the trees:
 
## When to Use It:
- When your data has complex, non-linear relationships or intricate feature interactions.
- When you have high-dimensional data (lots of features).
- When your dataset has missing values or outliers.
- As a strong, "out-of-the-box" benchmark model.

## Pros & Cons:
### Advantages	
- No Overfitting: Averaging many trees prevents overfitting.	
- Robust: Handles missing data and outliers incredibly well.	
- Feature Importance: Tells you which features matter most.	
### Limitations:
- No Extrapolation: Cannot predict values outside the range of training data.
- Slow & Heavy: Can be slow to train and uses significant memory.
- Black Box: Hard to interpret compared to a single decision tree.

## Feature Scaling:
Feature scaling was not applied because Random Forest Regression is a tree-based algorithm that is not affected by the scale of the input features. Therefore, scaling is not required for this model.

## Evaluation:
1. R² Score (Coefficient of Determination) = 0.8813 (88.13%)
 - What it means: Our model successfully explains 88.13% of the variation in insurance expenses.
 - Verdict: This is an excellent and highly accurate result for real-world data!
2. Mean Absolute Error (MAE) = 2,627.26
 - What it means: On average, the model's predictions are off by about 2,627.26 (dollars/currency units) from the actual insurance expenses.
 - Verdict: This gives us a very clear, realistic idea of the average prediction error.
3. Root Mean Squared Error (RMSE) = 4,670.16
 - What it means: This also measures the average prediction error, but it penalizes larger errors more heavily.
 - Verdict: Since RMSE is higher than MAE, it shows that there are a few outlier cases where the model had larger errors.
4. Mean Squared Error (MSE) = 21,810,412.28
 - What it means: This is the average of the squared errors. It is primarily used mathematically to train the model, and a lower value is always better.
