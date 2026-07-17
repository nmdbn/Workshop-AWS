---
title: "Week 11 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Learn centralized monitoring/alerting with CloudWatch + SNS and edge protection with WAF.
* Apply both directly to harden the running Maison Édition system.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn CloudWatch: Metrics, Logs, Alarms, Dashboards | 06/29/2026 | 06/29/2026 | <https://000008.awsstudygroup.com> |
| 3 | - Learn SNS pub/sub and the email subscription confirmation flow | 06/30/2026 | 06/30/2026 | <https://000077.awsstudygroup.com> |
| 4-5 | - Learn WAF: managed rule groups, custom rules, rate-based rules; the CloudFront Web ACL must be declared in `us-east-1` | 07/01/2026 | 07/02/2026 | <https://000026.awsstudygroup.com> |
| 6 | - **Apply to the project:** configure 4 CloudWatch alarms (ASG CPU, ALB 5xx, RDS connections, SQS DLQ) sending alerts to an SNS email; enable WAF on CloudFront with 3 managed rule groups + 1 rate-based rule; test by dropping a fake message into the DLQ and sending fake SQLi/XSS requests to confirm they get blocked | 07/03/2026 | 07/03/2026 | <https://000026.awsstudygroup.com> · [/5-Workshop/5.7-CloudWatch-SNS/](/5-Workshop/5.7-CloudWatch-SNS/) · [/5-Workshop/5.8-WAF/](/5-Workshop/5.8-WAF/) |
| 7 | - Attended **Event 4 — FCAJ Community Day** | 07/04/2026 | 07/04/2026 | [/4-EventParticipated/4.4-Event4/](/4-EventParticipated/4.4-Event4/) |

### Week 11 Achievements:

* Understood the difference between CloudWatch Metrics (numbers), Logs (detailed records), and Alarms (thresholds) — three separate but complementary pieces.
* Understood why a CloudFront Web ACL must be declared in `us-east-1` even though CloudFront itself is a global service.
* Learned to test an alarm safely (dropping a fake message into the DLQ) instead of waiting for a real incident.
* Understood that a WAF rate-based rule works over a rolling 5-minute window, unlike a fixed per-IP block.
* Applied it successfully: received a real alert email after deliberately triggering an alarm, and confirmed fake SQLi/XSS requests were blocked with a `403` by WAF.
