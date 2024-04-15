# Incident Response Playbook Template

### Modified Incident Type

Unintended access to an Amazon Simple Storage Service (Amazon S3) bucket

### Introduction

This playbook is provided as a template to customers using AWS products and who are building their incident response capability.  You should customize this template to suit your particular needs, risks, available tools and work processes.

Security and Compliance is a shared responsibility between you and AWS. AWS is responsible for “Security of the Cloud”, while you are responsible for “Security in the Cloud”. For more information on the shared responsibility model, [please review our documentation](https://aws.amazon.com/compliance/shared-responsibility-model/).

You are responsible for making your own independent assessment of the information in this document. This document: (a) is for informational purposes only, (b) references current AWS product offerings and practices, which are subject to change without notice, and (c) does not create any commitments or assurances from AWS and its affiliates, suppliers or licensors. This document is provided “as is” without warranties, representations, or conditions of any kind, whether express or implied. The responsibilities and liabilities of AWS to its customers are controlled by AWS agreements, and this document is not part of, nor does it modify, any agreement between AWS and its customers.

## Summary

### This Playbook
 This playbook outlines response steps for unintended access to an Amazon Simple Storage Service (Amazon S3, or S3) bucket.  These steps are based on the [NIST Computer Security Incident Handling Guide](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) (Special Publication 800-61 Revision 2) that can be used to:

* Gather evidence
* Contain and then eradicate the incident
* recover from the incident
* Conduct post-incident activities, including post-mortem and feedback processes

Interested readers may also refer to the [AWS Security Incident Response Guide]( https://docs.aws.amazon.com/whitepapers/latest/aws-security-incident-response-guide/welcome.html) which contains additional resources.

Once you have customized this playbook to meet your needs, it is important that you test the playbook (e.g., Game Days) and any automation (functional tests), update as necessary to achieve the desired results, and then publish to your knowledge management system and train all responders.

Note that some of the incident response steps noted below may incur costs in your AWS account(s) for services used in either preparing for, or responding to incidents. Customizing this runbook and testing it will help you to determine if additional costs will be incurred. You can use [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/) and look at costs incurred over a particular time frame (such as when running Game Days) to establish what the possible impact might be.
In reviewing this playbook, you will find steps that involve processes that you may not have in place today. Proactively preparing for incidents means you need the right resource configurations, tools and services in place that allow you to respond to an incident.
The next section will provide a summary of this incident type, and then cover the five steps (parts 1 - 5) for handling unintended access to an S3 bucket.

### This Incident Type
By default, all S3 buckets are private and can be accessed only by users that are explicitly granted access.  Sometimes, customers will make changes to their bucket configuration to meet their requirements, or the requirements of their application. These changes (such as changes to a bucket policy, for example) may result in unintended access being granted to IAM principals or unauthenticated users. This playbook covers steps that can be used to deal with unintended access.

## Incident Response Process
---
### Part 1: Acquire, Preserve, Document Evidence

Acquire, Preserve, Document Evidence: Determine if there has been unintended data access to an S3 bucket. Gather evidence from various sources such as internal ticketing systems, monitoring systems, CloudTrail logs, and repeated attemp. Review IAM Access Analyzer and CloudTrail logs to identify any misconfigurations or unauthorized access.


### Part 2: Contain the Incident

Contain the Incident: Disable compromised credentials or revoke permissions associated with them. Modify bucket policies to restrict access to authorized principals. Review and adjust Block Public Access settings if necessary.

### Part 3: Eradicate the Incident

Eradicate the Incident: Mitigate vulnerabilities that were exploited. Rotate compromised passwords/credentials. Mitigate attack vectors related to systems interacting with the S3 bucket(s). Implement security best practices for S3, such as configuring IMDSv2, rotating SSH credentials, revoking credentials for existing role sessions, etc.


### Part 4: Recover from the Incident

Recover from the Incident: Review pre- and post-mitigation logs to assess the impact of the incident and identify any remaining attack signatures. Restore lost or modified data if necessary, using S3 Versioning, lifecycle policies, Cross-Region Replication, or other means.

