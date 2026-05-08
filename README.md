AWS Lambda CSV Preprocessor

This project is an AWS Lambda-based CSV preprocessing system that automatically processes CSV files uploaded to Amazon S3.

Project Overview

The Lambda function is triggered whenever a CSV file is uploaded to the raw data S3 bucket. It reads the CSV file, removes rows with missing values, and uploads the cleaned CSV file to another S3 bucket for processed data.

AWS Services Used
AWS Lambda
Amazon S3
IAM
Python (boto3)
Features
Automatically triggered on S3 file upload
Reads CSV files from S3
Removes rows containing missing values
Writes cleaned CSV data back to another S3 bucket
Serverless architecture
Fully automated preprocessing pipeline
Project Architecture
User uploads CSV file to raw S3 bucket
S3 event triggers AWS Lambda function
Lambda reads CSV file
Rows with missing values are filtered
Cleaned CSV is uploaded to processed S3 bucket
File Structure

lambda-csv-project/

lambda_function.py
README.md
requirements.txt
Python Libraries Used
boto3
csv
io
Lambda Function Workflow
Input Bucket

rk-csv-raw-data02

Output Bucket

rk-csv-processed-data02

Processing Logic
Reads uploaded CSV file
Extracts header row
Checks each row
Removes rows with empty or missing values
Saves cleaned data
Sample CSV Input

Name, Age, City
Ravi, 21, Pune
Aman, , Mumbai
Shiv, 22, Nashik

Sample Processed Output

Name, Age, City
Ravi, 21, Pune
Shiv, 22, Nashik

Deployment Steps
Create S3 buckets
Create AWS Lambda function
Upload Python code
Add S3 trigger to Lambda
Configure IAM permissions
Upload CSV file to raw bucket
IAM Permissions Required
AmazonS3FullAccess
AWSLambdaBasicExecutionRole
Future Improvements
Data validation
Duplicate row removal
Logging and monitoring using CloudWatch
File format conversion
Integration with AWS Glue or Athena
Author

Ravindra Kale

License

This project is for educational and learning purposes.