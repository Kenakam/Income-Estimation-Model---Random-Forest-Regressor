# Income Estimation Model

## 📌 Project Overview
This repository features a machine learning solution for **Income Estimation**. The objective is to predict the annual salary of customers based on their transaction history, demographic details, and behavioral patterns. Accurate income estimation is vital for financial institutions to assess creditworthiness and personalize marketing offers.

The project utilizes a **Random Forest Regressor**, an ensemble learning method that excels at capturing complex, non-linear relationships within financial data.

## 🛠️ Project Workflow
The notebook follows a structured end-to-end data science pipeline:

1.  **Exploratory Data Analysis (EDA)**:
    * Detailed descriptive statistics to understand feature distributions.
    * Identification of data quality issues (e.g., anomalous geographical coordinates).
2.  **Advanced Feature Engineering**:
    * Created sophisticated aggregations (Mean and Max) to capture behavioral trends:
        * `payment_period` grouped by `bin_age`.
        * `amount` grouped by `txn_description`.
        * `balance` grouped by `merchant_suburb`.
3.  **Data Pre-processing**:
    * **Dimensionality Reduction**: Removed high-cardinality columns (10+ unique values) to prevent model noise and overfitting.
    * **Imputation**: Handled missing values using the mode for categorical and numerical features.
    * **Encoding**: Transformed categorical features into numerical formats using `LabelEncoder`.
4.  **Model Optimization**:
    * Implemented **RandomizedSearchCV** to fine-tune the Random Forest hyperparameters (`n_estimators`, `max_depth`, `max_features`, etc.), balancing model complexity with performance.
5.  **Deployment Simulation**:
    * Integrated a production-ready simulation that applies the trained model to new, unseen customer data (`income_deploy.xlsx`) to generate real-time income predictions.

## ⚠️ Notes & Constraints
* **Local Machine Iteration**: This model was developed on a local machine with limited hardware resources. Due to these computational constraints, the hyperparameter search grid and iteration cycles were restricted. Further tuning on a more powerful environment could yield higher accuracy.
* **Task-Specific Methodology**: Certain pre-processing steps (e.g., using mode imputation for all features and specific column-dropping thresholds) were implemented based on **specific task requirements**. These parameters were optimized for this specific exercise and may not reflect universal industry "best practices" in every context.

## 📊 Performance Metrics
The model was evaluated using standard regression metrics, focusing on:
- **Mean Absolute Error (MAE)**
- **Mean Squared Error (MSE)**
- **R-squared ($R^2$)**

## 💻 Technologies Used
- **Python 3.x**
- **Data Processing**: Pandas, NumPy
- **Machine Learning**: Scikit-Learn
- **Visualization**: Matplotlib, Seaborn
- **File Handling**: Openpyxl (for Excel integration)

## 🚀 How to Use
1. Clone this repository.
2. Ensure `income_est.xlsx` and `income_deploy.xlsx` are in the project directory.
3. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn seaborn matplotlib openpyxl
