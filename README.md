# customer-churn-api

A machine learning app to predict the probability of customer churn using a pre-trained model. Available via REST API and batch processing.

Overview

This project helps predict if a customer will leave a service using:

A Flask REST API for real-time predictions

A batch script to handle multiple customers

Pre-trained model and transformer

Logs to monitor processing

Folder Structure
bash
Copy
Edit
customer-churn-api/
├── app/               # API code & model
├── logs/              # Logs from batch runs
├── test_data/         # Sample input files
├── batch.py           # Batch prediction script
├── requirements.txt   # Required packages
├── scored_customers.csv
└── README.md

Setup

Clone the repo:

bash
Copy
Edit
git clone [repository-url]
cd customer-churn-api
Create a virtual environment:

bash
Copy
Edit
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate (Windows)
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
How to Use
API (Real-time Prediction)
Run the API:

bash
Copy
Edit
cd app
python main.py
API URL: http://localhost:8000/predict

Send POST request with customer data:

bash
Copy
Edit
curl -X POST http://localhost:8000/predict \
  -H "Content-Type: application/json" \
  -d @test_data/sample_input.json
Response:

json
Copy
Edit
{
  "churn_probability": 0.72,
  "churn_prediction": "Yes"
}
Batch Mode
Run batch predictions:

bash
Copy
Edit
python batch.py --input test_data/all_customers.csv
Results saved in scored_customers.csv
Logs saved in logs/batch_log.txt

Input Format
Sample JSON input:

json
Copy
Edit
{
  "customer": {
    "gender": "Female",
    "SeniorCitizen": 0,
    ...
    "MonthlyCharges": 29.85
  }
}
Model Info
Model: model.pkl

Transformer: transformer.pkl

Threshold: 0.5 for Yes/No

Notes
Use Python 3.6+

Troubleshoot using logs/batch_log.txt

Make sure input format matches the example
