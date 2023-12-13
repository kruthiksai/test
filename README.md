# Project Overview

## Module 1: Product Classification Model

### Description
This module contains code to train a machine learning model for classifying products into categories.

### Libraries Required
- scikit-learn (sklearn): A machine learning library for Python.
- joblib: A library for lightweight pipelining in Python. It is often used for saving and loading machine learning models.

---

## Module 2: Receipt Scanner Android App

### Description
This module is an Android app developed using Java and Android Studio. The app captures images of bills in real-time and sends them to the backend (Module 3) for extraction and classification. The app also features a dashboard displaying a pie chart of the user's overall expenditure over a certain period.

### Tools and Libraries Required
- JDK
- Android Studio
- SDK
- Virtual Emulator

---

## Module 3: Receipt Scanner Backend

### Description
This module is a Flask application containing REST APIs. The backend receives bills from the frontend (Module 2), extracts data from the bills, and classifies them into categories using the NLP model from Module 1 for further analysis.

### Libraries Required
- Flask: A web framework for Python.
- Flask-SQLAlchemy: Flask extension for SQLAlchemy, an SQL toolkit, and Object-Relational Mapping (ORM) library.
- boto3: The Amazon Web Services (AWS) SDK for Python. Used for interacting with AWS services, such as S3.
- joblib: A library for lightweight pipelining in Python. Used for saving and loading machine learning models.
- Werkzeug: A utility library for WSGI (Web Server Gateway Interface) applications.
- Textract: The AWS Textract SDK for Python.
- trp: A Python library for parsing Amazon Textract responses.

---

## Module 4: Classification Lambda

### Description
This module contains a Lambda function that serves as a predictor with a pre-trained model for classifying products into categories.

### Tools and Libraries Required
- joblib: A library for lightweight pipelining in Python. Used for saving and loading machine learning models.

---

## Data Insights Automation Scripts

### Description
In addition to the main modules, the project includes Glue automation scripts for extracting data from the database to generate insights.

---

Feel free to update this README file with any additional information or specific instructions for setting up and running each module.
