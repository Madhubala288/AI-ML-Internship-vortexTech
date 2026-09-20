# Week 3: Regression and Clustering on Real Data
**AI & ML Internship Track**

This project demonstrates two machine learning techniques — **Random Forest Regression** and **K-Means Clustering** — using a medical insurance dataset.
The project follows an end-to-end machine learning workflow, including data inspection, data cleaning, preprocessing, model training, evaluation, clustering, visualization, and interpretation.

---

## Project Objective
The main objectives of this project are:
- Predict a continuous numerical value (`charges`) using a regression model.
- Evaluate the regression model using **RMSE** and **R² score**.
- Discover hidden groups in the dataset using **K-Means Clustering**.
- Determine a reasonable number of clusters using the **Elbow Method**.
- Visualize the resulting clusters in 2D.
- Document the complete machine learning workflow.

---

## Dataset
The project uses a medical insurance dataset containing 1,000+ records and 12 columns.
The dataset contains information such as:
- Customer age, Sex, BMI, Children, Smoking status, Region
- Exercise level, Chronic condition, Annual income, Insurance claim count, Charges

*Note: The dataset was intentionally prepared with common real-world data quality issues, including missing values, duplicate records, inconsistent categorical values, invalid numerical values, and outliers.*

---

## Data Cleaning
The following preprocessing steps were performed:
- Checked dataset shape and structure.
- Identified and removed duplicate records.
- Converted numerical columns to appropriate numeric data types.
- Identified and handled invalid/negative clinical values.
- Imputed missing numerical values using median imputation and categorical values using mode.
- Standardized categorical values and removed non-predictive columns (`customer_id`).

---

## Regression Analysis

### Model
**Random Forest Regressor** (`n_estimators=100`, `random_state=42`).

### Workflow
1. Encoded categorical variables using One-Hot Encoding (`drop_first=True`).
2. Split data into 80% Training set and 20% Testing set.
3. Trained the Random Forest Regressor on the training set.
4. Evaluated predictions on the test set and plotted an Actual vs. Predicted scatter plot.

### Evaluation Results
- **RMSE:** Evaluated typical error size in charge predictions.
- **R² Score:** High variance captured by the model on unseen test data.

---

## Clustering Analysis

### Algorithm
**K-Means Clustering**.

### Features Used
- Age
- BMI
- Annual Income

### Feature Scaling
Selected features were standardized using **StandardScaler** to ensure equal weighting in distance calculations.

### Optimal K Selection
The **Elbow Method** was used across $K=1$ to $10$. An elbow bend was observed at **$K = 3$**, making 3 the optimal number of clusters.

### Cluster Insights & Interpretation
- **Cluster 0 (Middle-Aged, High BMI & High Charges):** Average age ~45.5 years, highest BMI (~35.25), and elevated medical charges (~$20,943).
- **Cluster 1 (Young Adults, Low Charges):** Youngest segment with average age ~27.2 years and lowest average medical charges (~$16,215).
- **Cluster 2 (Older Adults, Healthy BMI & Highest Charges):** Oldest segment with average age ~53.8 years and healthier BMI (~24.6), incurring the highest average medical charges (~$21,545) due to age factors.

---

## Technologies Used
- **Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Machine Learning:** Scikit-learn (`RandomForestRegressor`, `KMeans`, `StandardScaler`)
- **Visualization:** Matplotlib
- **Environment:** Google Colab / Jupyter Notebook / VS Code

---

## Project Structure
```text
vortextech-aiml-week3/
│
├── Week_3_Regression_and_Clustering.ipynb
├── medical_insurance_unclean_week3.csv
└── README.md