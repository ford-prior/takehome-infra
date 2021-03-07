# Exercise 1 – Provision a Serverless API

## Problem statement

  Using the [provided Python application code](fortune_handler/) as a starting point, deploy an AWS Lambda-backed API behind an Application Load Balancer. Deploy all infrastructure using an Infrastructure as Code tool (CloudFormation/SAM/CDK or Terraform are strongly preferred). The API should be publicly accessible. Consider how to increase the application's observability (metrics and logs).

## Terraform vs. CDK

Terraform & the CDK were the top 2 choices:

* both are declarative, which is ideal for creating cloud resources
* both support Python, which makes life easier
* both are super well-documented with entire tutorials([terraform](https://learn.hashicorp.com/tutorials/terraform/lambda-api-gateway?in=terraform/aws)|[cdk](https://docs.aws.amazon.com/cdk/latest/guide/serverless_example.html)) just for this specific use case

I chose the CDK because:
* I was short on time & it's designed for quick ramp-up
* it's native to AWS, which _usually_ means:
    * less time-consuming configuration
    * less chance I'll run into an unexpected limitation

##  Pre-Requisites (macOS)

1. [aws-cli](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
1. Python 3.6 or later including `pip` and `virtualenv`
1. npm (to install `cdk`)

## Before you start
1. run `aws configure` to configure AWS access
2. run `cdk --version` to check that CDK is installed (I'm at `1.92.0`)

## Step 1
1. `mkdir MyApp` then `cd MyApp`
1. let the CDK give you a basic app by issuing `cdk init --language python`.

  > NOTE: When you run cdk init --language [language], an initial application with basic boilerplate code is created for you in the project root, under app.py.

2.
