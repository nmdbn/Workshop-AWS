---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Learn to host a static site on S3 and accelerate/protect it with CloudFront.
* Understand private buckets served through an Origin Access Control (OAC) instead of public buckets.
* Learn the S3 Gateway VPC Endpoint for private access from EC2.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn S3 static website hosting basics, Block Public Access | 05/18/2026 | 05/18/2026 | <https://000057.awsstudygroup.com> |
| 3 | - Learn CloudFront basics: origin, cache behavior, OAC vs a public bucket | 05/19/2026 | 05/19/2026 | <https://000094.awsstudygroup.com> |
| 4 | - Learn the S3 Gateway VPC Endpoint — lets EC2 reach S3 without going through NAT/internet | 05/20/2026 | 05/20/2026 | <https://000111.awsstudygroup.com> |
| 5-6 | - **Practice:** <br>&emsp; + Create an S3 bucket for the FE build (fully block public access) <br>&emsp; + Attach CloudFront with OAC <br>&emsp; + Add a separate media bucket for product images with a `/media/*` path pattern | 05/21/2026 | 05/22/2026 | <https://000057.awsstudygroup.com> |
| 7 | - Attended **Event 1 — FCAJ Community Day** | 05/23/2026 | 05/23/2026 | [/4-EventParticipated/4.1-Event1/](/4-EventParticipated/4.1-Event1/) |

### Week 5 Achievements:

* Understood why a private bucket plus CloudFront OAC is far safer than a public bucket — only CloudFront can read the objects, users never touch S3 directly.
* Learned to distinguish a Gateway VPC Endpoint (free, S3/DynamoDB only) from an Interface VPC Endpoint (billed, uses PrivateLink for other services).
* Understood that CloudFront cache behaviors let multiple path patterns (`/media/*`, `/api/*`, `/*`) route to different origins under a single domain — avoiding CORS issues entirely.
* Learned to pick different cache policies for static content (CachingOptimized) versus a dynamic API (CachingDisabled).
* Understood why the S3 Gateway Endpoint lets EC2 upload images to S3 without incurring NAT Gateway data-transfer charges.
