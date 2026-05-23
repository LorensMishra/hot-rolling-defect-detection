# Hot Rolling Defect Detection using Machine Learning

## Project Overview

This project focuses on detecting defects in hot rolling coils using machine learning techniques. The goal is to predict whether a coil contains an Alpha defect or not based on different process parameters collected during manufacturing.

In industrial production, missing a defective coil can lead to quality issues, customer complaints, and production loss. Because of this, the main focus of this project is to improve defect detection performance and reduce the chances of missing defective samples.

This is a binary classification problem where:

Y = 1 → Defect Present

Y = 0 → No Defect

---

## Problem Statement

The objective of this project is to build a machine learning model that can identify defective coils with high reliability.

The expected performance requirements are:

- Recall = 100%
- Precision > 90%
- False Positive Rate < 10%

Since missing a defect is costly in manufacturing, this project mainly focuses on improving recall so that defective coils are not missed.

---

## Dataset Information

The dataset contains process-related parameters collected during hot rolling production.

### Files Used

### train.csv
Contains training data with input features and target values.

### test.csv
Contains test data for prediction.

### sample_submission.csv
Contains the required submission format.

---

## Features

The dataset contains:

### CoilID
Unique identifier for each coil.

### X1 to X49
Manufacturing and process-related input features.

### Y
Target column

- 1 = Defect Present
- 0 = No Defect

---

## Project Workflow

The project was completed in multiple steps.

### Step 1: Data Loading

The dataset was loaded using Pandas and checked for shape, missing values, and basic information.

### Step 2: Data Preprocessing

- Removed unnecessary columns like `CoilID` during training
- Checked missing values
- Prepared train and test data
- Performed train-validation split

### Step 3: Exploratory Data Analysis

The class distribution was analyzed because the dataset was imbalanced.

Defective samples were much fewer than non-defective samples, which made prediction more challenging.

### Step 4: Model Building

Different machine learning models were tested and compared.

Models used:

- Logistic Regression
- Random Forest Classifier
- Extra Trees Classifier
- XGBoost Classifier
- CatBoost Classifier

### Step 5: Threshold Optimization

Different probability thresholds were tested to improve defect detection.

The final threshold was selected based on:

- Maximum Recall
- Better Precision
- Lower False Negatives

A recall-first approach was used because missing a defect is more risky than predicting an extra defect.

### Step 6: Final Prediction

The best-performing model was selected and predictions were generated on the test dataset.

The final submission file was created in CSV format.

---

## Technologies Used

This project was developed using:

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- CatBoost
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Project Structure

```text
Hot-Rolling-Defect-Detection/
│──dataset/
│    │── train.csv
│    │── test.csv
│    │── sample_submission.csv
│── defect_detection_recall_first.ipynb
│── expected_submission.csv
│── README.md
│── images/
```

---

## Output Screenshots

### Dataset Overview

<img width="426" height="717" alt="image" src="https://github.com/user-attachments/assets/7b2b0713-1977-421b-97fb-8192b893309a" />

### Class Distribution

<img width="580" height="463" alt="image" src="https://github.com/user-attachments/assets/473ffcec-fe40-47a5-b97d-c7e1a04e52e6" />

### Statistical Summary

<img width="1047" height="366" alt="image" src="https://github.com/user-attachments/assets/9c6cb467-6a09-4409-a02d-d82cb70c2a79" />

### Model Performance

<img width="826" height="308" alt="image" src="https://github.com/user-attachments/assets/171e4b30-1ca3-42ae-a2cd-257dcadab7d1" />

### Selected Model Results

<img width="1225" height="613" alt="image" src="https://github.com/user-attachments/assets/9799ae87-9e70-4fe4-abeb-0c711521b6e6" />

### Threshold Comparison

<img width="1457" height="130" alt="image" src="https://github.com/user-attachments/assets/b51b35f4-235d-4010-a34f-f70df7f2bd4a" />

### Confusion Matrix

<img width="567" height="455" alt="image" src="https://github.com/user-attachments/assets/35517528-48f2-4305-bbfe-f2c95d9185de" />

### ROC Curve

<img width="448" height="455" alt="image" src="https://github.com/user-attachments/assets/fd9f3104-15e9-4134-8a30-e274db6aee4f" />

### Training Results

<img width="933" height="717" alt="image" src="https://github.com/user-attachments/assets/3535ff32-597c-4a1e-872d-1760ee32c5ee" />

### Final Prediction Output

<img width="262" height="203" alt="image" src="https://github.com/user-attachments/assets/06a66da9-38e7-4e32-a435-ce8bba6899f7" />




---

## Model Evaluation

The model was evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

The project mainly prioritized Recall because the goal was to avoid missing defective coils.

---

## Final Output

The final prediction file generated is:

```text
expected_submission.csv
```

Submission format:

```text
    CoilID  Y
0     711  1
1    1542  0
2    1232  1
3     600  0
4    1087  1
(339, 2)

---

## How to Run the Project

### Step 1

Clone the repository:

```bash
git clone https://github.com/your-username/your-repository-name.git
```

### Step 2

Install required libraries:

```bash
pip install pandas numpy scikit-learn xgboost catboost matplotlib seaborn
```

### Step 3

Open Jupyter Notebook:

```bash
jupyter notebook
```

### Step 4

Open:

```text
defect_detection_recall_first.ipynb
```

### Step 5

Run all notebook cells.

After execution, the final output file will be generated:

```text
expected_submission.csv
```

---

## Challenges Faced

One of the main challenges in this project was the imbalanced dataset because defective samples were much lower than non-defective samples.

To handle this, different models and threshold tuning techniques were tested to improve defect detection performance.

---

## Conclusion

This project helped in understanding how machine learning can be applied to industrial defect detection problems.

Different classification models were explored and compared. Since missing a defect is risky in manufacturing environments, the final approach focused more on maximizing defect detection performance while maintaining good prediction quality.

Future improvements can include advanced feature engineering, hyperparameter tuning, and deep learning-based approaches for better performance.
