---
title: "Week 12 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* Review the whole Maison Édition architecture built over the past 11 weeks.
* Analyze and optimize cost, and practice a safe teardown.
* Summarize what the internship covered end to end.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn AWS cost-optimization concepts: Reserved Instances, Savings Plans, right-sizing | 07/06/2026 | 07/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3-4 | - Review the full architecture built so far (VPC → EC2/ASG → RDS → S3/CloudFront → Redis → SQS/Lambda → DynamoDB → CloudWatch/SNS → WAF) and list out every cost item | 07/07/2026 | 07/08/2026 | [/5-Workshop/5.9-Cost-Cleanup/](/5-Workshop/5.9-Cost-Cleanup/) |
| 5 | - **Apply to the project:** analyze Maison Édition's real cost breakdown (NAT Gateway is the single biggest line item), propose optimizations (fewer NAT Gateways, weigh disabling Multi-AZ/WAF when not needed) | 07/09/2026 | 07/09/2026 | [/2-Proposal/](/2-Proposal/) · [/5-Workshop/5.9-Cost-Cleanup/](/5-Workshop/5.9-Cost-Cleanup/) |
| 6-8 | - **Apply to the project:** practice tearing down the infrastructure in the correct order (backend first, then frontend) and clean up resources that are easy to miss (ECR image, old CloudWatch Logs, versioned S3 objects) | 07/10/2026 | 07/12/2026 | [/5-Workshop/5.9-Cost-Cleanup/](/5-Workshop/5.9-Cost-Cleanup/) |

### Week 12 Achievements:

* Gained a full picture of a complete multi-tier AWS system — from networking, compute, database, and caching to async processing, NoSQL, monitoring, and edge security — and understood how every piece fits together.
* Learned to read an AWS cost breakdown and spot the biggest, most easily overlooked line item (NAT Gateway).
* Understood that every cost optimization comes with a trade-off (Multi-AZ vs. uptime, WAF vs. security, number of NAT Gateways vs. AZ fault tolerance) — nothing is free.
* Learned the safe teardown order and the "hidden" resources that are commonly forgotten during cleanup (ECR images, old log groups, old S3 object versions).
* Wrap-up: went from not knowing what AWS was (Week 1) to hands-on building and operating a real production system for the Maison Édition project (Week 12).
