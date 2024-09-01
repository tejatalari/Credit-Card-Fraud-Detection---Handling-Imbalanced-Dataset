
# Credit Card Fraud Detection - Handling Imbalanced Dataset

## Overview

This project focuses on detecting fraudulent credit card transactions by handling imbalanced datasets. The dataset used in this project is highly imbalanced, with the majority of transactions being legitimate and a small fraction being fraudulent. This project implements various techniques to address the imbalance issue and improve the accuracy of the fraud detection model.

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Preprocessing](#preprocessing)
- [Modeling](#modeling)
- [Evaluation](#evaluation)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Dataset

The dataset used in this project is the [Credit Card Fraud Detection dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud) from Kaggle. It contains transactions made by European cardholders in September 2013. The dataset includes 284,807 transactions, out of which 492 are fraudulent, making it a highly imbalanced dataset.

**Features:**
- **V1 to V28:** Result of PCA transformation (features are anonymized)
- **Time:** Number of seconds elapsed between this transaction and the first transaction in the dataset
- **Amount:** Transaction amount
- **Class:** Target variable (1 for fraudulent transactions, 0 for legitimate transactions)

## Project Structure

```bash
├── data
│   ├── creditcard.csv       # Raw dataset
├── notebooks
│   ├── 1_data_exploration.ipynb  # Exploratory Data Analysis (EDA)
│   ├── 2_data_preprocessing.ipynb # Data Preprocessing & Handling Imbalance
│   ├── 3_modeling.ipynb       # Model Training
│   ├── 4_evaluation.ipynb     # Model Evaluation
├── models
│   ├── trained_model.pkl     # Saved Model
├── README.md                 # Project README file
└── requirements.txt          # Python packages required
```

## Installation

To run this project locally, follow these steps:

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/credit-card-fraud-detection.git
   cd credit-card-fraud-detection
   ```

2. Create and activate a virtual environment (optional but recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows use `venv\Scripts\activate`
   ```

3. Install the required Python packages:

   ```bash
   pip install -r requirements.txt
   ```

## Preprocessing

In this step, we handle the imbalance in the dataset using various techniques:

- **Resampling Techniques:** 
  - **Oversampling:** Synthetic Minority Over-sampling Technique (SMOTE)
  - **Undersampling:** Random undersampling of majority class
- **Anomaly Detection:** Treating fraudulent transactions as anomalies and using isolation forests
- **Feature Scaling:** Standardizing features using `StandardScaler`.

## Modeling

We train several machine learning models to predict fraudulent transactions:

- **Logistic Regression**
- **Random Forest Classifier**
- **XGBoost Classifier**
- **Support Vector Machine (SVM)**

Hyperparameter tuning is performed using GridSearchCV to optimize model performance.

## Evaluation

The models are evaluated using the following metrics to account for the imbalanced dataset:

- **Precision:** Indicates the proportion of positive identifications that were actually correct.
- **Recall (Sensitivity):** Indicates the proportion of actual positives that were identified correctly.
- **F1 Score:** The harmonic mean of Precision and Recall, providing a balance between the two.
- **ROC-AUC Score:** Measures the ability of the classifier to distinguish between classes.

## Results

- The best-performing model achieved a high **ROC-AUC score** and **F1 Score** after handling the imbalance using SMOTE and undersampling techniques.
- **Confusion Matrix** results show that the model effectively reduces false negatives, crucial in fraud detection.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please feel free to create a pull request or open an issue.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

