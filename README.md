

# 💳 Fraud Detection System

**A real-time, machine learning-powered web application to identify fraudulent financial transactions.**
Built with **Python**, **Streamlit**, and **scikit-learn**, this solution delivers instant fraud predictions through an intuitive user interface.

---

## 🚀 Overview

The **Fraud Detection System** is designed to detect potentially fraudulent financial activities based on transactional patterns. It provides a seamless user experience via a web interface and leverages a pre-trained machine learning model for accurate, real-time results.

---

## 🔑 Key Features

* **🧠 Real-Time Prediction**
  Instantly identify suspicious transactions based on transaction type, amount, and account balances.

* **🌐 Interactive Web Interface**
  Powered by **Streamlit** for a smooth, intuitive user experience.

* **📦 Pre-Trained Model**
  Utilizes a ready-to-use `fraud_detection_model.pkl` for accurate classification.

* **📊 Data Analysis Tools**
  Includes a Jupyter Notebook (`analysis_model.ipynb`) for EDA, model training, and customization.

---

## 📁 Project Structure

```
fraud-detection-system/
│
├── fraud_detection.py         # Core Streamlit app for fraud prediction
├── requirements.txt           # Project dependencies
├── analysis_model.ipynb       # Jupyter notebook for EDA and model training
├── fraud_detection_model.pkl  # Pre-trained ML model for fraud detection
```

---

## 📊 Dataset: `fraud_dataset.csv`

This dataset is the foundation for training and evaluating the machine learning model. It contains synthetic but realistic financial transaction records. Below are the key details:

* **Total Records:** \~600,000 transactions
* **File Name:** `fraud_dataset.csv`
* **Format:** CSV (Comma-Separated Values)

### 📌 Features:

| Column Name      | Description                                                         |
| ---------------- | ------------------------------------------------------------------- |
| `step`           | Time step unit (e.g., 1 unit = 1 hour)                              |
| `type`           | Type of transaction (e.g., PAYMENT, TRANSFER, CASH\_OUT, DEPOSIT)   |
| `amount`         | Transaction amount                                                  |
| `oldbalanceOrg`  | Balance of the origin account before the transaction                |
| `newbalanceOrig` | Balance of the origin account after the transaction                 |
| `oldbalanceDest` | Balance of the destination account before the transaction           |
| `newbalanceDest` | Balance of the destination account after the transaction            |
| `isFraud`        | Label: `1` if fraudulent, `0` if legitimate                         |
| `isFlaggedFraud` | System-flagged fraud detection flag (not used for model prediction) |

### 🔍 Usage in Model Training:

* Target variable: `isFraud`
* Selected features for training: `type`, `amount`, `oldbalanceOrg`, `newbalanceOrig`, `oldbalanceDest`, `newbalanceDest`

> **Note**: The dataset was preprocessed in `analysis_model.ipynb` to encode categorical variables, handle imbalances, and split into training/testing sets.


>**Note**: The dataset is too large in size, download it from here : https://www.kaggle.com/datasets/amanalisiddiqui/fraud-detection-dataset?resource=download


---

## ⚙️ Prerequisites

Ensure the following tools are installed:

* **Python** ≥ 3.13.3
* **[uv](https://github.com/astral-sh/uv)**: For virtual environment & dependency management
* **Modern Web Browser** (e.g., Chrome, Firefox)

---

## 🧪 Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-username/fraud-detection-system.git
   cd fraud-detection-system
   ```

2. **Create a Virtual Environment**

   ```bash
   uv venv
   ```

3. **Activate the Environment**

   * On **Windows**:

     ```bash
     .venv\Scripts\activate
     ```

   * On **macOS/Linux**:

     ```bash
     source .venv/bin/activate
     ```

4. **Install Dependencies**

   ```bash
   uv add -r requirements.txt
   ```

5. **(Optional) Install Jupyter Kernel**

   ```bash
   uv pip install ipykernel
   python -m ipykernel install --user --name=.venv --display-name="Fraud Detection Env"
   ```

---

## 🖥️ Usage

### 🟢 Running the Web App

```bash
streamlit run web_app.py
``

* Open the URL provided in the terminal (usually `http://localhost:8501`)
* Fill in transaction details:

  * **Transaction Type:** PAYMENT, TRANSFER, CASH_OUT, DEPOSIT
  * **Transaction Amount**
  * **Sender & Receiver Balances**
* Click **Predict** to get fraud analysis.

---

### 📊 Running Data Analysis

```bash
jupyter notebook
```

* Open `EDA_and_Model_Trainer.ipynb`
* Explore data, visualize patterns, or retrain the model

---

## 📦 Dependencies

Listed in `requirements.txt`:

* `pandas` – Data wrangling
* `numpy` – Numerical operations
* `matplotlib` & `seaborn` – Data visualization
* `scikit-learn` – ML modeling
* `streamlit` – Web app interface
* `ipykernel` – Jupyter kernel support

---

## 📝 Notes

* **Model Compatibility**: Ensure any retrained model aligns with the features expected by `web_app.py`.
* **Customization**: Modify `EDA_and_Model_Trainer.ipynb` to fine-tune model features or add new metrics.

---

## 🤝 Contributing

We welcome contributions to improve the Fraud Detection System!

1. **Fork** the repository
2. **Create a branch**:

   ```bash
   git checkout -b feature/your-feature
   ```
3. **Commit changes**:

   ```bash
   git commit -m "Add your feature"
   ```
4. **Push and open a Pull Request**

✅ Please follow **PEP 8** standards and document your code.

---
