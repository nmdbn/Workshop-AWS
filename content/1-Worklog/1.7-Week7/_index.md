---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Convert the fixed 2-instance setup into a real Auto Scaling Group with target-tracking scaling.
* Understand the self-bootstrapping challenge: a new instance the ASG creates on its own must be able to run the app with zero manual steps.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn ASG concepts: min/max/desired capacity, health check type (EC2 vs ELB), scaling policy types (target tracking, step, scheduled, predictive) | 06/01/2026 | 06/01/2026 | <https://000006.awsstudygroup.com> |
| 3 | - Learn why launch template user data must be fully self-sufficient — a new instance can't depend on a manual deploy script | 06/02/2026 | 06/02/2026 | <https://000006.awsstudygroup.com> |
| 4-5 | - **Practice:** write and debug user data (ECR login, image pull, run container) — hit a bug where Terraform mistook a bash variable `${INSTANCE_ID}` for its own interpolation syntax | 06/03/2026 | 06/04/2026 | <https://000006.awsstudygroup.com> |
| 6 | - **Practice:** create the Auto Scaling Group (min 2 / max 4 / desired 2), attach a target-tracking policy at 60% average CPU, remove the manual target group attachment, verify a freshly launched instance self-bootstraps and registers healthy | 06/05/2026 | 06/05/2026 | <https://000006.awsstudygroup.com> |

### Week 7 Achievements:

* Clearly understood the difference between health check type `EC2` (hardware status checks only) and `ELB` (the target group's own health check) — critical for the ASG to know when to replace an instance.
* Understood that a target-tracking scaling policy automatically computes how many instances to add/remove to keep a metric (CPU) near a target value, instead of hand-writing an alarm plus a step-scaling policy.
* Learned the single most important lesson of the week: the launch template/user data must be "self-sufficient" — an ASG can create a new instance at any time (scale-out, replacing an unhealthy one), and if user data doesn't finish configuring the app by itself, that new instance will never pass its health check, and the ASG will loop create-and-terminate it, wasting money for nothing.
* Learned to debug a Terraform interpolation bug — `${...}` inside a heredoc gets read as Terraform syntax unless it's a plain bash `$VAR` with no braces.
* Understood why applying in two phases (bring up the new ASG alongside the old instances first, then remove the old ones) avoids a downtime gap during the cutover.
