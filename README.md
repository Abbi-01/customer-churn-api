# customer-churn-api

A machine learning application that predicts customer churn probability using a pre-trained model, available both as a REST API endpoint and a batch processing script.

## Overview

This project provides a solution for predicting whether customers are likely to churn based on various customer attributes. The system includes:

- Flask-based REST API for real-time predictions
- Batch processing script for scoring multiple customers
- Pre-trained machine learning model and data transformer
- Logging capabilities for monitoring performance

## Installation

1. Clone the repository and navigate to the project directory
2. Create a virtual environment: `python -m venv venv`
3. Activate it: `source venv/bin/activate`
4. Install dependencies: `pip install -r requirements.txt`

## Usage

### REST API
```bash
cd app
python main.py
```
API available at `http://localhost:8000/predict`

Send POST requests with customer data:
```bash
curl -X POST http://localhost:8000/predict \
  -H "Content-Type: application/json" \
  -d @test_data/sample_input.json
```

### Batch Processing
```bash
python batch.py --input test_data/all_customers.csv
```
Results saved to `scored_customers.csv`

## Requirements

- Python 3.6+
- Flask, pandas, scikit-learn
- Additional dependencies in `requirements.txt`

## Contributors

Made with ❤️ by Abhishek.
