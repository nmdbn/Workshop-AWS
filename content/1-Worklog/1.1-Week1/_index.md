---
title: "Week 1 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Week 1 Objectives:

- Onboard with the First Cloud AI Journey team and get oriented with the internship's rules.
- Build a mental map of what AWS actually is, before touching any service in depth.
- Get a working AWS account plus a configured CLI, and take the first hands-on steps with EC2.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                      | Start Date | Completion Date | Reference Material                        |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ----------------------------------------- |
| 2   | - Onboarding: Attend event at school, meet the FCAJ team, read through internship rules and expectations                                                                                  | 04/20/2026 | 04/20/2026      |                                           |
| 3   | - Survey the main AWS service categories (Compute, Storage, Networking, Database, ...) and how they map to a typical web system                                                           | 04/21/2026 | 04/21/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Sign up for an AWS Free Tier account <br> - Install and configure the AWS CLI (Access Key, Secret Key, default region)                                                                  | 04/22/2026 | 04/22/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 5-6 | - Learn EC2 fundamentals: instance types, AMI, EBS, Elastic IP, and the classic SSH connection method <br> - **Practice:** launch an EC2 instance, connect over SSH, attach an EBS volume | 04/23/2026 | 04/24/2026      | <https://cloudjourney.awsstudygroup.com/> |

### Week 1 Achievements:

- Got a working mental model of AWS as a set of building blocks (Compute, Storage, Networking, Database, ...) rather than a single product — this framing made every later week easier to place.
- Have an active AWS Free Tier account, ready to use for the rest of the internship.
- Comfortable navigating the AWS Console to locate and open a service, even before knowing what it does in depth.
- Configured the AWS CLI end to end (Access Key / Secret Key / default region) and used it for basic checks: account identity, region list, EC2 status, key pair management.
- Can move between the Console and the CLI to inspect the same resource from two angles — a habit that turned out to matter a lot later when debugging.
- Launched a first EC2 instance from scratch and connected to it over SSH — the baseline experience later weeks would deliberately move away from (Session Manager instead of SSH keys).
