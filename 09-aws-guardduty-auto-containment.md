# Project 09: AWS GuardDuty auto-containment

> **Target repo:** `aws-ir-lab` | **Difficulty:** Advanced | **Time:** 2 weeks | **Cost:** Low (GuardDuty trial, Lambda free tier; tear down after)

## Goal

Build an automated response pipeline in AWS: when GuardDuty raises a high-severity finding about an EC2 instance or IAM user, an EventBridge rule triggers a Lambda function that contains it (isolates the instance or disables the access key) and sends a notification.

## Why hiring managers care

This is exactly the kind of work cloud incident response teams build. It shows AWS services, Python, infrastructure as code and response design in one project.

## Skills you'll show

- GuardDuty, EventBridge, Lambda, SNS, IAM
- Python with boto3
- Infrastructure as code (Terraform or AWS CDK)
- Response design: what to automate and what to leave to humans

## Prerequisites

- Dedicated AWS lab account with a billing alarm
- Terraform or CDK installed

## Milestones

- [ ] Turn on GuardDuty and use its sample findings feature to generate test findings
- [ ] Create an EventBridge rule that matches high-severity findings
- [ ] Write the Lambda: for EC2 findings, swap the instance's security group to an isolation group with no inbound or outbound rules; for IAM findings, deactivate the access key
- [ ] Before containing, snapshot the instance's volumes and tag everything with the finding ID
- [ ] Send an SNS email with what was done and how to undo it
- [ ] Give the Lambda a least-privilege IAM role (document every permission and why)
- [ ] Put all of it in Terraform or CDK so it deploys and destroys with one command
- [ ] Test with a sample finding and a real simulation (Stratus Red Team)

## Deliverables

- `auto-containment/` with IaC, Lambda code and tests
- README with architecture diagram, IAM policy explanation, and a demo walkthrough
- A runbook for the human follow-up after automatic containment

## Stretch goals

- Add an allowlist so production-tagged resources go to a human instead of being contained
- Use AWS Step Functions for an approval step before containment

## Interview talking points

- Why you snapshot before isolating
- Why swapping security groups doesn't kill existing tracked connections, and what you'd do about it
- The risk of automated containment (false positives taking down production) and how you limited it

## Resources

- AWS docs: GuardDuty sample findings, EventBridge integration
- AWS Security Incident Response Guide (whitepaper)
- [Stratus Red Team](https://stratus-red-team.cloud/)
