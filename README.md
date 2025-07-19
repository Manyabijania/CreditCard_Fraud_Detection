# Credit Card Fraud Detection

This project aims to detect fraudulent credit card transactions using **Logistic Regression**. The original dataset was **highly imbalanced**, but **undersampling** was applied to create a balanced dataset with an equal number of fraud and legitimate transactions for effective model training.

---

## **Dataset**
- **Source:** [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud)
- **Description:**  
  - **Original transactions:** 284,807  
    - **Fraudulent:** 492  
    - **Legitimate:** 284,315  
    - **Features:** 30 columns, including PCA-transformed features (V1–V28), `Time`, `Amount`, and `Class` (target variable: 0 = legitimate, 1 = fraud).

---

## **Problem Statement**
Credit card fraud is a significant challenge due to its rarity compared to legitimate transactions. A simple accuracy metric fails here because predicting all transactions as "legitimate" would yield a very high accuracy but detect no fraud cases.  

To address this, **undersampling** was applied to balance the dataset, and the focus was shifted to metrics like **Precision, Recall, and F1 Score** to ensure fraud cases are effectively detected.

---

## **Approach**

### **1. Data Preprocessing**
- **Undersampling:**
  The original dataset was **highly imbalanced**, with fraudulent transactions accounting for only **0.172%** of all transactions. 
  Selected an equal number of legitimate transactions (492) to match the fraudulent cases, resulting in a balanced dataset.  
- **Feature & Target Separation:**  
  `X` = features, `Y` = target (Class).
- **Train-Test Split:**  
  Used `train_test_split` with stratification to maintain the balance in both training and test sets.
- **Feature Scaling:**  
  Standardized numerical features using `StandardScaler`.

### **2. Model Selection**
- **Algorithm Used:** Logistic Regression.
- Fraud detection is a binary classification problem (fraud vs. legitimate).
- Logistic Regression is specifically designed for binary classification and outputs a probability (between 0 and 1), making it ideal for detecting fraud.
- Logistic Regression was chosen as a baseline classifier due to its simplicity and interpretability.

### **3. Evaluation Metrics**
- **Accuracy:** Overall correctness.  
- **Precision:** How many predicted fraud cases were correct.  
- **Recall:** How many actual fraud cases were correctly detected.  
- **F1 Score:** Harmonic mean of precision and recall, better for imbalanced datasets.

---

## **Results**
After training and testing the model:
- **Accuracy on Training Data:** 95.04%  
- **Accuracy on Testing Data:** 91.87%  
- **Precision:** 95.55%  
- **Recall:** 87.75%  
- **F1 Score:** 91.48%

These metrics indicate the model balances **false positives and false negatives effectively**.

---

## **Future Improvements**
- Use **ensemble models** like Random Forest, XGBoost for better detection performance.
- Create a **real-time fraud detection system** by deploying this model through a Flask/Django API or a Streamlit web app.
- Implement an alerting system (e.g., email or SMS notifications) whenever the model detects a high-risk transaction.

---
