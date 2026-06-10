# AWS Security Monitoring Pipeline

## Overview

This project demonstrates the implementation of a cloud security monitoring and alerting solution using AWS native security services.

The solution captures IAM activity through AWS CloudTrail, forwards logs to CloudWatch Logs, detects security-relevant events using metric filters, and generates automated notifications using Amazon SNS.

## Architecture

IAM Activity
↓
CloudTrail
↓
CloudWatch Logs
↓
Metric Filter (CreateUser Event)
↓
CloudWatch Alarm
↓
Amazon SNS
↓
Email Notification

## Technologies Used

- AWS CloudTrail
- Amazon CloudWatch Logs
- CloudWatch Metrics
- CloudWatch Alarms
- Amazon SNS
- AWS IAM

## Security Use Case

Detect and alert on IAM user creation activity.

Monitoring unauthorized account creation is an important security control because attackers often establish persistence by creating new privileged accounts.

## Implementation

### CloudTrail
Created a multi-region CloudTrail trail to capture AWS management events.

### CloudWatch Logs
Connected CloudTrail to CloudWatch Logs for centralized log monitoring.

### Metric Filter

Filter Pattern:

```json
{ $.eventName = CreateUser }
```

Namespace:

```text
SecurityMonitoring
```

Metric:

```text
CreateUserCount
```

### Alarm

Alarm Name:

```text
CreateUserAlarm
```

Condition:

```text
CreateUserCount >= 1
```

### SNS Notifications

Configured Amazon SNS email notifications to alert administrators whenever a new IAM user is created.

## Skills Demonstrated

- AWS Security
- Cloud Security Monitoring
- CloudTrail
- CloudWatch
- IAM
- Security Alerting
- SOC Operations
- Detection Engineering

## Future Enhancements

- Monitor ConsoleLogin events
- Monitor Root Account activity
- Detect failed authentication attempts
- Integrate Security Hub
- Automate remediation with AWS Lambda
