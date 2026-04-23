# Customer Churn Prediction - Lloyds Banking Group Data Science Virtual Internship

## Overview

This project is part of the Lloyds Banking Group Data Science Virtual Internship program. The goal is to build a machine learning model to predict customer churn (attrition) based on customer demographics and behavioral data. By identifying customers likely to churn, the bank can take proactive measures to retain them, improving customer satisfaction and reducing revenue loss.

## Table of Contents

- [Project Structure](#project-structure)
- [Data Description](#data-description)
- [Installation](#installation)
- [Usage](#usage)
- [Methodology](#methodology)
- [Model Evaluation](#model-evaluation)
- [Results](#results)
- [Visualizations](#visualizations)
- [Business Insights](#business-insights)


## Project Structure

```
├── Customer_Churn_Data_Large.xlsx                        # Dataset Excel file 
├── Task 2: Building a machine learning model.ipynb       # Original notebook
├── Task_1_Data_gathering_and_exploratory_analysis.ipynb  # Exploratory data analysis notebook
└── README.md                         
```

## Data Description

The dataset is provided in an Excel file (`Customer_Churn_Data_Large.xlsx`) with multiple sheets:

- **Customer_Demographics**: Contains basic customer information including CustomerID, Age, Gender, MaritalStatus, and IncomeLevel.
- **Churn_Status**: Contains the target variable ChurnStatus (0 for retained, 1 for churned) linked by CustomerID.

After merging the sheets on CustomerID, the final dataset contains the following columns:

### Dataset Columns

| Column Name     | Description |
|-----------------|-------------|
| `CustomerID`   | Unique identifier for each customer. Used for merging data and not included in model training. |
| `Age`          | Age of the customer in years. Numerical feature used in the model after standard scaling. |
| `Gender`       | Gender of the customer. Categorical feature with values: 'M' (Male) or 'F' (Female). Encoded to 0/1 for modeling. |
| `MaritalStatus`| Marital status of the customer. Categorical feature with values: 'Married', 'Single', 'Widowed', 'Divorced'. Encoded to 0/1/2/3 for modeling. |
| `IncomeLevel`  | Income level category of the customer. Categorical feature with values: 'Low', 'Medium', 'High'. Encoded to 0/1/2 for modeling. |
| `ChurnStatus`  | Target variable indicating customer churn. Binary feature where 0 = Retained (no churn) and 1 = Churned. |

### Data Preprocessing Notes
- **Categorical Encoding**: Gender, MaritalStatus, and IncomeLevel are label-encoded to numerical values for machine learning algorithms.
- **Numerical Scaling**: Age is standardized using StandardScaler to have mean 0 and variance 1.
- **Missing Values**: The dataset appears to have no missing values based on initial exploration.
- **Class Balance**: The target variable distribution should be checked for imbalance, which may affect model performance.

Key features used in the model:
- **Age**: Numerical feature representing customer age.
- **Gender**: Categorical feature (Male/Female).
- **MaritalStatus**: Categorical feature (Married/Single/Widowed/Divorced).
- **IncomeLevel**: Categorical feature (Low/Medium/High).

## Installation

### 1️⃣ Clone the repository:

```bash
https://github.com/abhinandan07-git/Lloyds-Banking-Group-Data-Science-Job-Simulation.git
```

### 2️⃣ Install dependencies:

Install the required packages using pip:

```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn
```





## Usage

1. **Clone or download the project files.**

2. **Open the Jupyter notebook:**
   ```bash
   jupyter notebook task2.0.ipynb
   ```

3. **Run the cells sequentially** to:
   - Load and explore the data
   - Preprocess features (encoding and scaling)
   - Train the XGBoost model with hyperparameter tuning
   - Evaluate model performance
   - Generate visualizations
   - Make predictions for new customers

4. **Key outputs:**
   - Model accuracy metrics (ROC-AUC, precision, recall, F1-score)
   - Confusion matrix and ROC curve
   - Feature importance analysis
   - Churn probability distributions
   - Business insights for at-risk customers

## Methodology

### Data Preprocessing
- **Categorical Encoding**: Label encoding for Gender, MaritalStatus, and IncomeLevel.
- **Numerical Scaling**: Standard scaling for Age to normalize the feature.
- **Feature Selection**: CustomerID removed as it's not predictive; ChurnStatus used as target.

### Model Selection
- **Algorithm**: XGBoost (Extreme Gradient Boosting) - chosen for its high performance on tabular data and ability to handle imbalanced classes.
- **Hyperparameter Tuning**: Grid search with 5-fold cross-validation on parameters like max_depth, learning_rate, n_estimators, and subsample.

### Train-Test Split
- 80% training, 20% testing with stratified sampling to maintain class balance.

## Model Evaluation

The model is evaluated using several metrics:

- **ROC-AUC Score**: Measures the model's ability to distinguish between churn and non-churn customers.
- **Classification Report**: Includes precision, recall, F1-score, and support for each class.
- **Confusion Matrix**: Shows true positives, false positives, true negatives, and false negatives.

## Results

### Model Performance
- **Best Hyperparameters**: [Results from grid search]
- **ROC-AUC Score**: [Score on test set]
- **Accuracy**: [Overall accuracy]
- **Precision/Recall/F1 for Churn Class**: [Detailed metrics]

### Key Findings
- Age is the most important feature in predicting churn.
- Customers in certain demographic groups (e.g., higher income levels) have lower churn rates.
- The model can identify high-risk customers with over 70% churn probability.

## Visualizations 
<img width="986" height="836" alt="image" src="https://github.com/user-attachments/assets/be8f89c3-3609-4e4d-9dc5-d26d96b2e8f5" />
<img width="764" height="682" alt="image" src="https://github.com/user-attachments/assets/2ded8181-78b3-4c1d-82d9-49003d49a656" />
<img width="489" height="316" alt="image" src="https://github.com/user-attachments/assets/2d464796-6618-471c-be60-11ed9f399623" />
<img width="691" height="545" alt="image" src="https://github.com/user-attachments/assets/80124974-28ee-4972-8e38-b6ef3b61aaa5" />
<img width="510" height="391" alt="image" src="https://github.com/user-attachments/assets/fa35e31b-2d80-4824-9604-3c506c998c78" />
<img width="761" height="545" alt="image" src="https://github.com/user-attachments/assets/3ac0ed7d-cf67-4586-9780-ff1599099ecf" />
<img width="693" height="545" alt="image" src="https://github.com/user-attachments/assets/03e6d693-0997-486c-bfc8-043965d0cdc4" />
<img width="687" height="545" alt="image" src="https://github.com/user-attachments/assets/5054d949-5a47-4e25-a921-5c6a2c8db218" />
<img width="536" height="391" alt="image" src="https://github.com/user-attachments/assets/c3bef218-7b8f-4f69-90b8-d9db44bddec2" />
<img width="536" height="432" alt="image" src="https://github.com/user-attachments/assets/a0bbd185-037f-4c61-9378-211ebcba805c" />
<img width="536" height="391" alt="image" src="https://github.com/user-attachments/assets/74e23aa8-5d1e-4e8d-97c8-a3cd4be5d0db" />




These graphics provide visual support for model performance, feature relevance, and key demographic patterns in churn behavior.

## Business Insights

- **At-Risk Customer Identification**: Customers with churn probability > 0.7 are flagged for retention efforts.
- **Targeted Interventions**: Focus retention strategies on high-risk demographic groups.
- **Revenue Impact**: Early identification of churners can prevent significant revenue loss.
- **Model Deployment**: The trained model can be integrated into banking systems for real-time churn prediction.

## Prediction for New Customers

The notebook includes functionality to predict churn for new customers:

```python
# Example for a new customer
new_customer = pd.DataFrame({
    'Age': [35],
    'Gender': [1],  # 0=Female, 1=Male
    'MaritalStatus': [0],  # 0=Married, etc.
    'IncomeLevel': [2]  # 0=Low, 1=Medium, 2=High
})

# Scale and predict
new_customer[num_cols] = scaler.transform(new_customer[num_cols])
probability = best_model.predict_proba(new_customer)[:, 1][0]
prediction = best_model.predict(new_customer)[0]

print(f"Churn Probability: {probability * 100:.2f}%")
print(f"Predicted Churn: {'Yes' if prediction == 1 else 'No'}")
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



## Acknowledgments

- Lloyds Banking Group for providing the internship opportunity
- Data sources and problem statement from the internship program
- Open-source community for the libraries used (pandas, scikit-learn, XGBoost, etc.)

