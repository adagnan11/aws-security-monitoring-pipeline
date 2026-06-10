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
