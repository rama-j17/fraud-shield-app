# 🛡️ FraudShield: Real-Time E-Commerce Fraud Detection

FraudShield is a real-time fraud detection dashboard built for e-commerce platforms. It uses a trained XGBoost model, PySpark batch simulation, and a custom metric called RWSI (Risk-Weighted Seller Index) to detect suspicious transactions and flag high-risk sellers.

---

## 🚀 Features

- ⚡ Batch-based real-time fraud detection
- 🧠 Trained XGBoost model for accurate predictions
- 📊 RWSI leaderboard to monitor risky sellers
- 📥 Upload CSV and download fraud logs via dashboard
- 📈 Expandable view of full results

---

## 🗂️ Folder Structure

fraud-shield-app/
├── model/
│ ├── xgb_fraud_model.json
│ └── label_encoders.pkl
├── streamlit_app/
│ ├── app.py
│ └── utils.py
├── fraud_logs/
│ └── fraud_batch.csv (auto-generated after uploads)
├── requirements.txt
└── README.md

---

## 📦 Setup Instructions

1. **Clone the repo**:
   ```bash
   git clone https://github.com/yourusername/fraud-shield-app.git
   cd fraud-shield-app
Install dependencies:
pip install -r requirements.txt
Run the app:
streamlit run streamlit_app/app.py

📂 Input CSV Format
Your file should include the following columns:
transaction_id
seller_id
amount
payment_method
device_type
location

Example:
transaction_id	seller_id	amount	payment_method	device_type	location
TX001	S123	1500	COD	Mobile	Delhi

📊 RWSI: Risk-Weighted Seller Index
Calculates risk for each seller based on historical fraud counts and total transactions.

Updated with every batch upload.

A higher score = higher fraud suspicion.

🖥️ Dashboard Functions
Upload CSV → Predict frauds
View fraudulent transactions

Download fraud logs

See RWSI leaderboard
Expand to view full results

📃 Output Example
✅ "3 fraudulent transactions detected out of 100"

🚨 Fraudulent transaction table

📊 RWSI leaderboard

📥 Download button for fraud logs

✅ Requirements
Python 3.8+
streamlit
pandas
scikit-learn
xgboost
joblib
