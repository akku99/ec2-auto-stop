# EC2 Auto Stop using AWS Lambda

This project automatically stops EC2 instances based on tags using AWS Lambda and EventBridge.

## Architecture Overview
The standard serverless architecture for this process is as follows:
  - Amazon EventBridge (Scheduler): Triggers the workflow based on a defined time (e.g., "every Friday at 6:00 PM") using cron or rate expressions.
  - AWS Lambda (Logic): Receives the trigger and executes a script (usually Python or Node.js) to identify and stop specific instances.
  - IAM Role (Security): Provides the Lambda function with necessary permissions like ec2:StopInstances and ec2:DescribeInstances.
  - EC2 Instances (Target): The instances to be stopped, often filtered by specific Tags (e.g., autostop: true) to avoid accidentally shutting down production servers. 

# Architecture
<img width="1030" height="627" alt="image" src="https://github.com/user-attachments/assets/e95340ba-a5fd-4d9e-9bb1-e4df18ff53bb" />

## Features
- Tag-based filtering
- Cost optimization
- Serverless automation
