# AWS Security Monitoring Pipeline

## Overview

Built a cloud-native security monitoring pipeline on AWS that detects IAM user creation events and generates automated alerts using CloudTrail, CloudWatch, and SNS.

This project demonstrates security monitoring, log analysis, event detection, metric generation, and automated alerting within AWS.

---

## Architecture

IAM Activity
    ↓
CloudTrail
    ↓
CloudWatch Log Group
    ↓
Metric Filter
(CreateUser)
## Services Used

- AWS CloudTrail
- Amazon CloudWatch
- CloudWatch Logs
- CloudWatch Metric Filters
- CloudWatch Alarms
- Amazon SNS
- IAM

---

## Security Use Case

This monitoring pipeline detects IAM user creation activity within an AWS account.

When a CreateUser API event occurs:

1. CloudTrail records the event.
2. CloudWatch Logs receives the log entry.
3. A metric filter detects the CreateUser event.
4. A custom metric (CreateUserCount) is generated.
5. CloudWatch Alarm evaluates the metric.
6. SNS sends a notification when the alarm threshold is reached.

---

## Skills Demonstrated

- AWS Security Monitoring
- CloudTrail Log Analysis
- CloudWatch Metrics and Alarms
- Event Detection and Alerting
- SNS Notifications
- IAM Monitoring
- Cloud Security Operations
- Security Automation
