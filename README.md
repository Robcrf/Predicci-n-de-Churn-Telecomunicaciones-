# Telecom Customer Churn Prediction

This repository contains a data science project focused on predicting customer churn for a telecommunications company. The goal is to build a Machine Learning model that identifies customers with a high probability of canceling their service, allowing the company to implement proactive retention strategies.

---

## 📋 Table of Contents
- [Project Objective](#-project-objective)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [Results and Conclusions](#-results-and-conclusions)
- [How to Use this Repository](#-how-to-use-this-repository)
- [Technologies Used](#-technologies-used)

---

## 🎯 Project Objective

The main objective is to reduce revenue loss caused by customer churn. This is achieved through:
1.  **Exploratory Data Analysis (EDA):** Identifying the key factors and characteristics that most influence a customer's decision to leave the company.
2.  **Predictive Modeling:** Developing and evaluating multiple classification models to find the one that best predicts churn.
3.  **Strategic Recommendations:** Providing the company with actionable insights based on the findings to improve customer retention.

---

## 💾 Dataset

The data is segmented into four CSV files, containing information about customer contracts, internet services, personal data, and phone services.

- `contract.csv`: Contract details, payment method, and charges.
- `internet.csv`: Information on internet services such as online security, tech support, etc.
- `personal.csv`: Customer demographic data (gender, senior citizen status, etc.).
- `phone.csv`: Information on whether the customer has phone service and multiple lines.

The `Telecom_Churn_Prediction_Portfolio_v2.ipynb` notebook unifies and processes these files for analysis.

---

## ⚙️ Methodology

The project follows a structured data science workflow:

1.  **Data Loading and Cleaning:** The 4 datasets are loaded, data types are corrected, and they are merged into a single DataFrame.
2.  **Feature Engineering:** New variables such as `churn` (our target variable) and `tenure_months` are created.
3.  **Exploratory Data Analysis (EDA):** Visualizations are used to understand the data distribution and the relationship between variables and the churn rate.
4.  **Preprocessing for Modeling:** The dataset is prepared for training by applying scaling to numerical variables and One-Hot Encoding to categorical ones.
5.  **Handling Class Imbalance:** The SMOTENC technique is used to oversample the minority class (customers who churn) to ensure the model learns to identify it correctly.
6.  **Training and Evaluation:** 5 different classification models are trained and evaluated (Dummy, Logistic Regression, Decision Tree, Random Forest, and XGBoost). Performance is measured using metrics like F1-Score, Precision, and Recall, in addition to the confusion matrix.

---

## 📊 Results and Conclusions

### Key Findings from the Analysis
- **Contract Type:** Customers with `Month-to-month` contracts are drastically more likely to churn.
- **Tenure:** New customers have a much higher probability of leaving. Loyalty increases significantly over time.
- **Support Services:** The lack of services like `Tech Support` and `Online Security` is strongly correlated with a higher churn rate.

### Model Performance
The **Random Forest** model was selected as the best overall performer, achieving an **F1-Score of 0.61** for the minority class (Churn). This model offers an excellent balance between the ability to correctly identify customers who will leave (Recall) and not misclassifying loyal customers (Precision).

### Strategic Recommendations
1.  **Retain New Customers:** Implement welcome and follow-up campaigns during the first few months.
2.  **Incentivize Long-Term Contracts:** Offer discounts or benefits to customers with `Month-to-month` contracts to encourage them to switch to annual plans.
3.  **Promote Value-Added Services:** Offer packages that include `Tech Support` and `Online Security` to high-risk customers.

---

## 🚀 How to Use this Repository

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Robcrf/Prediccion-de-Churn-Telecomunicaciones-.git
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd Prediccion-de-Churn-Telecomunicaciones-
    ```
3.  **Install the dependencies:**
    Make sure you have the libraries listed in the technologies section. You can install them using pip:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn
    ```
4.  **Run the Jupyter Notebook:**
    Open and run the cells in `Telecom_Churn_Prediction_Portfolio_v2.ipynb` to replicate the analysis and results.

---

## 🛠️ Technologies Used

- **Python 3**
- **Pandas:** For data manipulation and analysis.
- **NumPy:** For numerical operations.
- **Matplotlib & Seaborn:** For data visualization.
- **Scikit-learn:** For preprocessing, modeling, and evaluation.
- **Imbalanced-learn:** For handling class imbalance (SMOTENC).
- **XGBoost:** For the Gradient Boosting model.
- **Jupyter Notebook:** As a development environment.

---

*Last updated: December 11, 2025*
