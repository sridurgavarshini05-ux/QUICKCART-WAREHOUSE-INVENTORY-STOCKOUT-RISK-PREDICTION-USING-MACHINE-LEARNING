# QUICKCART-WAREHOUSE-INVENTORY-STOCKOUT-RISK-PREDICTION-USING-MACHINE-LEARNING
The QuickCart Warehouse Inventory Stockout Risk Prediction system uses machine learning to predict the daily stock risk of products across different stores. It classifies inventory conditions into three categories: Safe, At-Risk, and Imminent.

# 🛒 QuickCart – Warehouse Inventory Stockout Risk Prediction Using Machine Learning

## 📌 Project Overview

QuickCart is a machine learning-based inventory stockout risk prediction system designed to identify potential inventory shortages across multiple stores and products.

The project combines multiple datasets, including Inventory, Stores, SKUs, Suppliers, and Events, to analyse inventory conditions and predict stockout risk for each SKU in each store on a daily basis.

The system classifies inventory conditions into three categories:

- 🟢 **Safe** – Sufficient inventory is available.
- 🟡 **At-Risk** – Inventory requires attention.
- 🔴 **Imminent** – High risk of stock shortage.

The main objective is to support better inventory monitoring and help businesses make informed stock management decisions.

## 🎯 Project Objectives

- Integrate multiple inventory-related datasets.
- Perform data preprocessing and feature engineering.
- Predict inventory stockout risk using machine learning.
- Compare different classification algorithms.
- Improve Imminent-risk detection through threshold optimization.
- Apply SHAP for model explainability.
- Generate daily inventory-risk predictions for different stores and products.

## 📂 Datasets Used

The project uses five datasets:

| Dataset | Description |
|---|---|
| Inventory | Daily stock and sales information |
| Stores | Store details and location information |
| SKUs | Product details and categories |
| Suppliers | Supplier reliability and delivery details |
| Events | Festival and event-related demand information |

**Final merged dataset:** 21,600 records and 39 original columns.

After feature engineering, the dataset contained 42 columns.

## ⚙️ Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- SHAP
- Joblib

## 🧠 Machine Learning Models

The following models were implemented and evaluated:

1. Majority Classifier
2. Logistic Regression
3. Balanced Logistic Regression
4. Random Forest
5. XGBoost
6. Adjusted XGBoost

## 📊 Model Performance

| Model | Accuracy | Macro F1-score |
|---|---:|---:|
| Majority Classifier | 62.28% | 0.26 |
| Logistic Regression | 71.25% | 0.59 |
| Balanced Logistic Regression | 75.62% | 0.68 |
| Random Forest | 73.45% | 0.60 |
| XGBoost | 82.00% | 0.73 |
| Adjusted XGBoost | 81.65% | **0.75** |

The adjusted XGBoost model was selected to improve the detection of Imminent inventory-risk cases.

### Adjusted XGBoost Classification Results

| Class | Precision | Recall | F1-score |
|---|---:|---:|---:|
| At-Risk | 0.76 | 0.62 | 0.68 |
| Imminent | 0.59 | 0.73 | 0.65 |
| Safe | 0.90 | 0.91 | 0.91 |

## 🔍 Explainable AI – SHAP

SHAP (SHapley Additive exPlanations) was used to understand the features influencing the XGBoost predictions.

### Top Five Important Features

1. Opening Stock
2. Sales Velocity (7 Days)
3. Reorder Point
4. Expected Lead Time
5. Supplier Reliability

SHAP summary and waterfall plots were generated to understand overall feature importance and individual predictions.

## 📈 Project Workflow

1. Data Collection
2. Data Integration
3. Data Preprocessing
4. Feature Engineering
5. Feature Selection
6. Training and Testing
7. Model Implementation
8. Model Evaluation
9. Threshold Optimization
10. SHAP Explainability
11. Final Inventory-Risk Prediction

## 📁 Project Structure

```text
QuickCart/
│
├── data/
│   ├── inventory.csv
│   ├── stores.csv
│   ├── skus.csv
│   ├── suppliers.csv
│   └── events.csv
│
├── models/
│   ├── original_logistic_model.pkl
│   ├── balanced_logistic_model.pkl
│   ├── random_forest_model.pkl
│   ├── xgboost_stockout_model.pkl
│   ├── majority_classifier.pkl
│   └── quickcart_xgboost_settings.pkl
│
├── notebooks/
│   └── QuickCart_Inventory_Prediction.ipynb
│
├── outputs/
│   └── QuickCart_Inventory_Risk_Predictions.csv
│
├── graphs/
│   ├── model_accuracy.png
│   ├── f1_score_comparison.png
│   ├── confusion_matrix.png
│   └── shap_feature_importance.png
│
├── requirements.txt
└── README.md
```

*This is a suggested repository structure. Organize the files according to the actual files included in your repository.*

## 🚀 Installation and Execution

### Step 1: Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### Step 2: Navigate to the Project Folder

```bash
cd QuickCart
```

### Step 3: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap joblib
```

### Step 4: Open the Notebook

Open the project notebook using Google Colab or Jupyter Notebook.

### Step 5: Run the Notebook

Execute the notebook cells in order to:

- Load the datasets.
- Perform preprocessing.
- Train the machine learning models.
- Evaluate model performance.
- Generate SHAP explanations.
- Produce inventory-risk predictions.

## 📤 Final Output

The system generates a prediction file named:

`QuickCart_Inventory_Risk_Predictions.csv`

The output contains:

- Date
- Store ID
- SKU ID
- Opening Stock
- Reorder Point
- Actual Risk
- Predicted Risk
- At-Risk Probability
- Imminent Probability
- Safe Probability

The generated prediction dataset contains **5,040 test records**.

## 🏁 Conclusion

QuickCart demonstrates the application of machine learning and explainable AI in warehouse inventory stockout risk classification.

The XGBoost model achieved 82% original accuracy, while threshold-adjusted XGBoost achieved a macro F1-score of 0.75 and 73% recall for the Imminent category.

The project provides an analytical approach to identifying inventory-risk conditions and supporting better stock management decisions.

## 🔮 Future Enhancements

- Real-time inventory monitoring dashboard.
- Automated alerts for Imminent-risk products.
- Integration with live supplier and inventory data.
- Additional machine learning and deep learning models.
- Evaluation using longer-term real-world inventory data.

## 👩‍💻 Project Information

**Project Name:** QuickCart – Warehouse Inventory Stockout Risk Prediction Using Machine Learning

**Domain:** Data Science and Machine Learning

**Task:** Multi-Class Classification

**Primary Model:** XGBoost

**Explainability Technique:** SHAP

**Development Environment:** Google Colab

---

⭐ If you find this project interesting, consider giving the repository a star!
