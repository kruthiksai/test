# ExpenseLens Project Flow

1. **User Uploads Receipts:**
   - Users upload receipt images via the mobile application.

2. **Image Storage:**
   - The images are transmitted to the specified S3 bucket (`arn:aws:s3:::receiptimagesbucket`).

3. **AWS TExtract Extraction:**
   - An API call is made to AWS TExtract for extracting details from the receipts.

4. **Information Extraction:**
   - AWS TExtract identifies and extracts information, including itemized costs, payment type, total receipt amount, and tax.

5. **NLP Classification:**
   - Another API invokes an NLP model hosted on a Lambda function to classify the extracted items.

6. **Update Products Table:**
   - The products table is updated with details such as product ID, receipt ID, product name, product cost, and product category.

7. **User Information Storage:**
   - User information is stored in the user table, including user ID, name, gender, city, state, email, and password.

8. **Receipt Details Recording:**
   - Receipt details, such as receipt ID, user ID, date, total amount, tax, and payment type, are recorded in the receipts table.

9. **Purchase Data Consolidation:**
   - All customer purchases are consolidated into the `purchase_data` table in the backend, capturing invoice ID, city, gender, product category, quantity, tax, total, date, month, and payment information for business analytics.

10. **Monthly Expenditure Summary:**
    - Users receive a monthly expenditure summary presented in the form of a pie chart.

11. **Business Analytics with QuickSight:**
    - From a business perspective, the RDS database is linked to QuickSight for comprehensive insights and analytics.


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




