# Configuring-CloudTrail-Logs-for-EC2-Events
#### What is AWS CloudTrail?

AWS CloudTrail is a governance, compliance, and auditing service that records AWS account activity across your infrastructure.

CloudTrail logs actions taken via:

AWS Management Console

AWS CLI

AWS SDKs

AWS services

It provides a historical record of activity, simplifying:

Security investigations

Compliance validation

Operational troubleshooting

Resource change tracking

### Benefits of CloudTrail

Improved Security – Detect unauthorized or malicious activity

Increased Compliance – Supports PCI DSS, HIPAA, SOX

Centralized Auditing – Single repository of account activity

Better Troubleshooting – Historical event analysis

### Lab Objective

Configure CloudTrail to capture EC2 activity logs and store them securely in an S3 bucket, then validate event logging.

### Task Breakdown

Configure CloudTrail and S3 Bucket

Verify S3 bucket creation

View CloudTrail logs in S3

Launch EC2 instance

Validate EC2-related event logs

Connect to EC2

Confirm logs generated in S3

Validate lab success

### Architecture Overview

User Action → CloudTrail → S3 Bucket → Log Files (JSON)

### Step-by-Step Implementation
### Step 1 — Create S3 Bucket for Logs

Amazon S3

Create unique bucket name

Block public access

Enable default encryption (recommended)

### Step 2 — Create CloudTrail

AWS CloudTrail

Configuration:

Trail Type: Single Region or Multi-Region (recommended)

Management Events: Read/Write

Data Events: Optional

Storage Location: S3 bucket created earlier

### Step 3 — Verify S3 Bucket Policy
### Step 4 — Launch EC2 Instance

Amazon EC2

Select Amazon Linux

Attach IAM role if required

Launch instance

### Step 5 — Validate EC2 Events in CloudTrail

Navigate:

CloudTrail → Event History → Filter by:

Resource name: EC2 Instance ID

Event name: RunInstances

### Do You Know?

CloudTrail logs provide detailed information about each EC2 event, including:

Timestamp of event

Identity of user/service

Specific API action performed

Affected resources

Source IP address

This level of visibility is critical for incident response and forensic analysis.

### Lessons Learned

CloudTrail is foundational for AWS security visibility

S3 bucket permissions must allow CloudTrail writes

Logs are JSON structured and investigation-ready

Event history is limited to 90 days unless archived

Centralized logging is essential for compliance

