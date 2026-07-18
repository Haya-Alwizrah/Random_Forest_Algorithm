# Classification Random Forest

## Project Overview
This project applies the **Random Forest Classification** algorithm to predict passenger survival on the Titanic. By leveraging demographic and ticketing information, the model identifies complex, non-linear relationships to classify whether a passenger survived (`1`) or did not survive (`0`).

---

## Dataset Specifications
* **Dataset File:** `Titanic-Dataset.csv`
* **Total Instances (Rows):** 891 passengers
* **Total Features (Columns):** 12 variables
* **Target Variable:** `Survived` (Binary Classification: `1` = Survived, `0` = Did Not Survive)
* **Key Predictors:**
  * `Pclass`: Ticket class (1st, 2nd, 3rd)
  * `Sex`: Passenger gender
  * `Age`: Age in years
  * `Fare`: Passenger ticket fare
  * `Embarked`: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)

---

## Data Preprocessing (EDA Insights)
During the Exploratory Data Analysis (EDA) phase, several data quality challenges and missing values were identified and treated:
* **`Age` (177 Missing Values):** Imputed using the median age.
* **`Cabin` (687 Missing Values):** Due to > 77% missingness, this feature was dropped.
* **`Embarked` (2 Missing Values):** Imputed using the most frequent port (mode: `'S'`).
* **Categorical Encoding:** Applied One-Hot Encoding transform text variables (`Sex`, `Embarked`) into machine-readable numerical formats.

---

## Model Training & Hyperparameter Tuning
The classification model was built using `scikit-learn`'s `RandomForestClassifier`. Key parameters explored during tuning include:
* `n_estimators`: Number of trees in the forest (e.g., `100`, `200`).
* `max_depth`: Maximum depth of the trees to control overfitting.
* `min_samples_split`: Minimum number of samples required to split an internal node.
* `max_features`: Number of features to consider when looking for the best split (default: `'sqrt'`).
* `random_state`: Set to `42` for exact reproducibility.

---

## Model Evaluation & Results

### Key Performance:
* **Precision:** `0.80`
* **recall:** `0.77`
* **F1:** `0.79`

### 🎯 Classification Report
| Class | Precision | Recall | F1-Score | Support |
| :--- | :--- | :--- | :--- | :--- |
| **0 (Did Not Survive)** | `0.85` | `0.88` | `0.86` | `110` |
| **1 (Survived)** | `0.81` | `0.77` | `0.79` | `69` |
| **Macro Avg** | `0.83` | `0.82` | `0.83` | `179` |

### 💡 Key Takeaways & Feature Importance
1. **Most Influential Features:** The Random Forest feature importance analysis revealed that `Sex`, `Fare`, and `Age` were the top three predictors of survival.
2. **Error Analysis:** The model occasionally misclassifies 3rd class female passengers with large families due to overlapping survival patterns in that demographic.
