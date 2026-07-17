---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Learn how an Application Load Balancer distributes traffic across multiple EC2 instances via target groups and health checks.
* Build the compute baseline (launch template + 2 EC2 instances) before adding auto scaling next week.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn ALB concepts: listener, target group, health check | 05/25/2026 | 05/25/2026 | <https://000006.awsstudygroup.com> |
| 3-4 | - Learn Launch Template — standardizing instance configuration for reuse across many identical instances | 05/26/2026 | 05/27/2026 | <https://000006.awsstudygroup.com> |
| 5-6 | - **Practice:** <br>&emsp; + Create a Launch Template (AMI, instance type, IAM profile, user data) <br>&emsp; + Create an ALB + Target Group (health check path `/actuator/health`) <br>&emsp; + Manually attach 2 EC2 instances to the Target Group <br>&emsp; + Test through the ALB DNS name | 05/28/2026 | 05/29/2026 | <https://000006.awsstudygroup.com> |
| 7 | - Attended **Event 2 — FCAJ Community Day** | 05/30/2026 | 05/30/2026 | [/4-EventParticipated/4.2-Event2/](/4-EventParticipated/4.2-Event2/) |

### Week 6 Achievements:

* Understood that an ALB polls health checks on a schedule so it knows which instances are "healthy" enough to receive traffic — a failing instance is automatically pulled out of rotation.
* Understood that a Launch Template is a reusable "mold" defined once, instead of clicking through instance creation by hand every time.
* Learned to pick a sensible health check path/threshold for a Spring Boot app (using the `/actuator/health` endpoint).
* Recognized the limitation of manually attaching instances to a target group (`aws_lb_target_group_attachment`) — every time the instance count changes, the attachment has to be added/removed by hand, nothing is automatic. This is exactly the gap Auto Scaling Group solves next week.
