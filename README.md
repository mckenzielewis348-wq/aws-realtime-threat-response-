# AWS Real-Time Threat Response Automation

An automated cloud incident response pipeline built on AWS. This project detects unauthorized changes and security threats in real time and automatically triggers remediation actions using AWS Lambda and EventBridge.

## Architecture & Workflow
1. **Detection:** AWS GuardDuty or AWS CloudTrail logs a security event or unauthorized API call.
2. **Routing:** AWS EventBridge catches the specific security event pattern.
3. **Remediation:** EventBridge triggers a Python (boto3) AWS Lambda function.
4. **Action:** The Lambda function isolates the compromised resource (e.g., revokes IAM session, revokes insecure Security Group rules, or disables public S3 access).

## Tech Stack
* **Cloud Provider:** AWS (GuardDuty, EventBridge, Lambda, IAM)
* **Automation:** Python (`boto3`)
* **Infrastructure as Code:** Terraform
* **CI/CD:** GitHub Actions & Checkov
