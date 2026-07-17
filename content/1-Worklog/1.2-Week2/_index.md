---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Understand Amazon VPC networking fundamentals: subnets, route tables, gateways, security groups.
* Build the multi-AZ network foundation the rest of the project will run on.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn VPC core concepts <br>&emsp; + CIDR block, subnet <br>&emsp; + Route Table <br>&emsp; + Internet Gateway <br>&emsp; + NAT Gateway | 04/27/2026 | 04/27/2026 | <https://000003.awsstudygroup.com> |
| 3 | - Learn Security Group vs Network ACL <br> - Learn VPC Resource Map for visualizing topology | 04/28/2026 | 04/28/2026 | <https://000003.awsstudygroup.com> |
| 4-6 | - **Practice:** <br>&emsp; + Create 1 VPC across 2 Availability Zones <br>&emsp; + Create 2 public + 2 private subnets <br>&emsp; + Create Internet Gateway + NAT Gateway + route tables <br>&emsp; + Create Security Groups <br>&emsp; + Verify topology using Resource Map | 04/29/2026 | 05/01/2026 | <https://000003.awsstudygroup.com> |

### Week 2 Achievements:

* Understood the difference between a public subnet and a private subnet, and why EC2/RDS should live in private subnets.
* Understood that a route table decides where traffic goes — `0.0.0.0/0` through the Internet Gateway (public) or through the NAT Gateway (private).
* Learned to distinguish Security Groups (stateful, per-instance) from Network ACLs (stateless, per-subnet).
* Learned to use the VPC Resource Map to quickly verify every subnet, route table, and gateway is wired up correctly.
* Understood why a NAT Gateway is billed hourly plus per-GB even with no traffic — a fixed cost to budget for.
