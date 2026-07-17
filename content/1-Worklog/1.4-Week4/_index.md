---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

- Understand RDS fundamentals, especially Multi-AZ for automatic failover.
- Connect an application running on EC2 to an RDS database in a private subnet.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                                              | Start Date | Completion Date | Reference Material                 |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------------------------- |
| 2   | - Learn RDS concepts: engine options, storage, DB Security Group, DB Subnet Group <br> - Attend study at Office                                                                                                                                   | 05/11/2026 | 05/11/2026      | <https://000005.awsstudygroup.com> |
| 3   | - Learn Multi-AZ deployment: standby instance, automatic failover, vs Single-AZ                                                                                                                                                                   | 05/12/2026 | 05/12/2026      | <https://000005.awsstudygroup.com> |
| 4   | - Learn automated backups, retention period, final snapshot                                                                                                                                                                                       | 05/13/2026 | 05/13/2026      | <https://000005.awsstudygroup.com> |
| 5-6 | - **Practice:** <br>&emsp; + Create an RDS PostgreSQL instance in a private subnet, Multi-AZ enabled <br>&emsp; + Restrict the DB Security Group to only accept connections from the EC2 Security Group <br>&emsp; + Test the connection from EC2 | 05/14/2026 | 05/15/2026      | <https://000005.awsstudygroup.com> |

### Week 4 Achievements:

- Understood that Multi-AZ means a standby copy exists in another AZ and automatically fails over on a problem — no connection string change needed, since the same endpoint DNS re-points automatically.
- Learned to distinguish Multi-AZ (high availability, same region) from a Read Replica (read scaling, can be cross-region).
- Understood why RDS should sit in a private subnet with a Security Group that only allows the EC2 Security Group in — never `0.0.0.0/0`.
- Learned to configure automated backups with a retention period, and what a final snapshot does when an instance is deleted.
- Realized Multi-AZ costs almost double Single-AZ — a direct trade-off between uptime and money.
