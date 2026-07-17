---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Learn EC2 fundamentals: AMI, instance type, IAM role vs access key.
* Learn to access an instance securely without SSH, using Systems Manager Session Manager.
* Install Docker to prepare for running the application as a container.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn EC2 basics: AMI, instance type, EBS volume, IAM Instance Profile | 05/04/2026 | 05/04/2026 | <https://000004.awsstudygroup.com> |
| 3 | - Learn IAM Role vs Access Key for granting an application access to AWS services | 05/05/2026 | 05/05/2026 | <https://000048.awsstudygroup.com> |
| 4-5 | - Learn Systems Manager Session Manager — connecting to a private instance with no SSH key and no open port 22 | 05/06/2026 | 05/07/2026 | <https://000058.awsstudygroup.com> |
| 6 | - **Practice:** <br>&emsp; + Launch an EC2 instance with an IAM Role attached (no key pair) <br>&emsp; + Connect via Session Manager <br>&emsp; + Install Docker + Docker Compose | 05/08/2026 | 05/08/2026 | <https://000004.awsstudygroup.com> |

### Week 3 Achievements:

* Understood that a launch template standardizes an instance's configuration (AMI, instance type, IAM profile, user data) so it can be reused instead of clicked together by hand each time.
* Understood why attaching an IAM Role to EC2 is far safer than hardcoding an access key on the server or in the code.
* Learned to connect to a private instance (no public IP, port 22 not open) entirely through Session Manager.
* Learned to distinguish user data (runs once at boot) from manually SSHing in and configuring by hand.
* Successfully installed Docker on Amazon Linux 2023 and understood why packaging the app as a container makes deployment consistent across instances.
