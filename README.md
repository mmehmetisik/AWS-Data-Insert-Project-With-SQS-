# AWS Data Insert Project (SQS)

![image](https://github.com/mmehmetisik/AWS-Data-Insert-Project-With-SQS-/assets/64706956/f328b73a-2f48-4601-9fdc-1f0dfa4935fc)


## Project Overview

This project demonstrates the real-time data handling capabilities using AWS services by inserting data from an S3 bucket into DynamoDB using AWS Lambda and SQS. The project leverages serverless architecture to simplify operations and minimize maintenance overhead, ensuring scalability and efficiency.

## Architecture

The system's architecture is designed to demonstrate serverless data manipulation without the need for server management. It utilizes the following AWS services:

- **AWS Lambda**: To handle the execution of the backend processes that process and insert data.
- **DynamoDB**: For storing the inserted data in a NoSQL database.
- **S3**: To store the text files that contain the data to be processed.
- **SQS**: To queue the data before it is inserted into DynamoDB.
- **IAM**: To securely manage access to AWS services.
- **NoSQL Workbench**: To query and analyze data stored in DynamoDB.

## Technologies Used

- **Python**: The programming language used for writing Lambda functions.
- **AWS Services**: Including but not limited to Lambda, DynamoDB, S3, SQS, IAM, and NoSQL Workbench for comprehensive cloud-based operations and data management.

## How It Works

1. **Data Upload**: A text file containing data is uploaded to an S3 bucket.
2. **Data Processing**: An S3 event triggers a Lambda function, which reads the text file, processes the data, and sends it to an SQS queue.
3. **Data Insertion**: Another Lambda function is triggered by SQS events, which reads the data from the queue and inserts it into a DynamoDB table.
4. **Verification and Monitoring**: The insertion process can be monitored and verified through AWS CloudWatch and the DynamoDB Management Console, ensuring data integrity and system performance.

## Setup and Configuration

Follow the detailed setup instructions to configure your AWS environment and deploy the project components. Ensure that all permissions and roles are properly set up for seamless operation.

### Step-by-Step Instructions

#### 1. S3 Bucket and Folder Setup
- Create an S3 bucket and a folder named `data` in it.

#### 2. SQS Setup
- Create an SQS queue (FIFO) with content-based deduplication enabled.

#### 3. Lambda Functions
- Create two Lambda functions:
  - **First Lambda**: Triggered by S3 events, processes text files, and sends messages to SQS.
  - **Second Lambda**: Triggered by SQS events, reads messages from SQS, and writes data to DynamoDB.

#### 4. IAM Roles
- Assign the necessary IAM roles and policies to the Lambda functions to allow them to interact with S3, SQS, and DynamoDB.

#### 5. DynamoDB Table
- Create a DynamoDB table named `ProcessedData`.

#### 6. NoSQL Workbench
- Use NoSQL Workbench to query and analyze the data stored in DynamoDB.

## License

This project is licensed under the MIT License, allowing for widespread use and modification.

