# Introduction

This repo is a continuation of the [flask-workshop](https://github.com/chunloy/flask-workshop).

# Getting started

## Prerequisites

1. Create an AWS account

2. Using **IAM** service, create a new user with _AdministratorAccess_ permissions. **Save the access keys `.csv` in a secure place.**

   > Note: You have one chance to save this file once the user is created. If something went wrong, you can always generate new access keys.

3. Install [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) and configure with `aws configure`. Follow the prompts to complete the configuration with your access keys. More info about configuration steps are linked [here](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-quickstart.html).

4. Install `serverless` framework with `npm i -g serverless`. Visit their [website](https://www.serverless.com/framework/docs/getting-started) for more info.

## Project setup

1. run either `serverless` or `sls` and choose `AWS - Python - Flask API` as the template.

2. Name the project whatever you'd like. This will create a new folder with most of the necessary files.

3. Create and activate a virtual environment with `python3 -m venv .venv && source .venv/bin/activate`

4. Add/replace the following files from this repo:

   - app.py
   - MOCK_DATA.json
   - requirements.txt
   - templates (folder)

5. Install dependencies with `pip3 install -r requirements.txt`

6. Run either `serverless deploy` or `sls deploy`

> Note: The auto-generated serverless.yml file contains the **bare minimum** to setup a Lambda Function. Refer to the [serverless docs](https://www.serverless.com/framework/docs/providers/aws/guide/serverless.yml) for fine-tuning.

# Workshop notes

## Agenda

- Recap of previous [workshop](https://github.com/chunloy/flask-workshop)
- Quick discussion:
  - What is AWS Lambda?
  - What are the different ways we can interface with AWS Services?
- Setup AWS account
- Install and configure AWS CLI
- Install serverless framework
- Deploy existing project

## AWS services used

- Lambda
- API Gateway
- S3

### What is a Lambda Function?

A _serverless_ comupting service that allows developers to run code without needing to build and maintain server(s) themselves. In other words, you can focus on building your app without having to worry about the infrastructure it relies on. Lambda functions are event-driven and can't execute by themselves.

### What is API Gateway?

A service for creating and maintaining REST APIs. More importantly, it's the main entry point and barrier to your app. This means clients can make requests and API Gateway will route them to other services without exposing them. Examples include triggering a Lambda or fetching data from DynamoDB.

### What is S3?

S3 stands for _Simple Storage Service_ and is used for cloud data storage. In our example, the `sls deploy` command created a bucket used to store all the Flask-related modules, configuration files, etc., needed to run the Lambda.
