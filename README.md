# AIML_Internship_Task4
# Breast Cancer Classification using Logistic Regression

This task implements a binary classification model to predict whether a breast tumor is **benign** or **malignant**.

## Steps Performed

### 1. Data Loading and Preprocessing

- Loaded the dataset and separated features (`X`) and target labels (`y`).
- Removed outliers from numerical features using the **Interquartile Range (IQR) method** to improve model performance.
- Split the data into **training** and **test** sets (e.g., 80% train, 20% test).
- Standardized the feature values using **StandardScaler** to ensure all features have mean = 0 and variance = 1.

### 2. Model Training

- Used **Logistic Regression**, a linear model suited for binary classification.
- Trained the model on the standardized training data.

### 3. Model Evaluation

- Predicted class labels on the test data.
- Evaluated performance using:
  - **Confusion Matrix**: Shows counts of True Positives, True Negatives, False Positives, and False Negatives.
  - **Precision**: Proportion of positive identifications that were actually correct.
  - **Recall (Sensitivity)**: Proportion of actual positives correctly identified.
  - **ROC Curve and AUC (Area Under Curve)**: Measures the model's ability to distinguish between classes across all classification thresholds.

## Sigmoid Function Explanation

The Logistic Regression model outputs the probability that a given input belongs to the positive class using the **sigmoid function**:

\[
\sigma(z) = \frac{1}{1 + e^{-z}}
\]

- Here, \( z = \mathbf{w}^\top \mathbf{x} + b \) is the linear combination of input features and weights.
- The sigmoid function maps any real-valued number \( z \) into a value between 0 and 1, which can be interpreted as a probability.
- If the probability is greater than a chosen threshold (commonly 0.5), the model classifies the sample as positive (malignant).

---

## Threshold Tuning

- The default classification threshold is 0.5.
- By adjusting the threshold, you can trade off between **precision** and **recall**.
- For example, lowering the threshold increases recall (catching more positive cases) but may increase false positives.
- Threshold tuning is especially important in medical diagnosis to reduce **false negatives** (missing malignant tumors).
