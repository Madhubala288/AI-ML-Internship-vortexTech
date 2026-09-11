VORTEXTECH AI & ML Internship – Week 2

Binary Classification Model

This project was completed as part of the VORTEXTECH AI & ML Internship Track – Week 2.

The objective was to move from data analysis into machine learning by building and evaluating a binary classification model using Scikit-learn.

Project Objective

The cleaned Café Sales dataset was used to build a binary classification problem.

A new target variable, High_Quantity, was created:

0 = Low quantity purchase (Quantity < 3)

1 = High quantity purchase (Quantity >= 3)

The original Quantity column was not used as a model feature because it was used to create the target variable.

Dataset

The dataset contains 10,000 café transaction records and originally includes:

Transaction ID

Item

Quantity

Price Per Unit

Total Spent

Payment Method

Location

Transaction Date

After removing rows with missing target/feature information during preparation, 9,540 records were used for modeling.

Data Preparation

The following preprocessing steps were performed:

Loaded the cleaned Café Sales dataset using Pandas.

Created the binary High_Quantity target.

Converted Transaction Date into useful date-based features:

Transaction Year

Transaction Month

Transaction Day

Transaction Day of Week

Removed the original date column.

Converted categorical variables using pd.get_dummies().

Checked for remaining missing values.

Split the data into 80% training and 20% testing sets.

Train/Test Split

Training samples: 7,632

Testing samples: 1,908

Features: 22

Machine Learning Models

Two classification algorithms were tested:

Logistic Regression

Decision Tree Classifier

Evaluation Metrics

The models were evaluated using:

Accuracy

Precision

Recall

F1-Score

Results

Logistic Regression

Accuracy: 61.58%

Precision: 37.92%

Recall: 61.58%

F1-Score: 46.94%

The classification report showed that Logistic Regression struggled to identify Class 0, while it predicted Class 1 very frequently.

Decision Tree

Accuracy: 51.00%

Weighted Precision: 52.00%

Weighted Recall: 51.00%

Weighted F1-Score: 52.00%

The Decision Tree produced more balanced predictions between the two classes, but its overall accuracy was lower than Logistic Regression.

Performance Summary

The Logistic Regression model achieved an accuracy of 61.58%, while the Decision Tree achieved an accuracy of 51.00%. Logistic Regression performed better overall based on accuracy, although its classification report showed that it struggled to identify the low-quantity class. The Decision Tree provided more balanced predictions between the two classes but had lower overall accuracy. Future improvements could include addressing class imbalance, creating more informative features, tuning model hyperparameters, and testing additional classification algorithms.

Technologies Used

Python

Pandas

NumPy

Scikit-learn

Matplotlib

Seaborn

Jupyter Notebook

Project Structure

vortextech-aiml-week2/
│
├── data/
│   └── cleaned_cafe_sales.csv
│
├── VORTEXTECH_Week2_Classification_Model.ipynb
│
└── README.md

How to Run

1. Install the required libraries

pip install pandas numpy matplotlib seaborn scikit-learn jupyter

2. Open the notebook

Open:

VORTEXTECH_Week2_Classification_Model.ipynb

in Jupyter Notebook or VS Code.

3. Run the cells

Run the notebook cells sequentially from data loading through model evaluation.

Learning Outcomes

Through this task, I practiced:

Preparing data for machine learning

Creating a binary target variable

Feature selection

Date feature extraction

Categorical feature encoding

Train/test splitting

Logistic Regression

Decision Tree Classification

Model prediction

Accuracy, precision, recall, and F1-score

Comparing classification models

Interpreting model limitations

Internship Task

VORTEXTECH AI & ML Internship Track
Week 2 of 4 – Beginner-Intermediate: Build a Classification Model