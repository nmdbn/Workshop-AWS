---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

- Learn NoSQL fundamentals with DynamoDB.
- Apply it directly to the Maison Édition project: build an activity-log / audit-trail feature.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                         | Start Date | Completion Date | Reference Material                                                                                                    |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | --------------------------------------------------------------------------------------------------------------------- |
| 2   | - Learn DynamoDB core concepts: partition key, sort key, billing mode (on-demand vs provisioned), TTL <br> - Attend study at Office                                                                          | 06/22/2026 | 06/22/2026      | <https://000060.awsstudygroup.com>                                                                                    |
| 3-4 | - Learn Global Secondary Index — when it's needed and how it differs from the primary key                                                                                                                    | 06/23/2026 | 06/24/2026      | <https://000060.awsstudygroup.com>                                                                                    |
| 5   | - **Apply to the project:** create the `activity-log` table for Maison Édition (hash `userId`, range `timestamp`), enable TTL to auto-delete after 90 days                                                   | 06/25/2026 | 06/25/2026      | <https://000060.awsstudygroup.com> · [/5-Workshop/5.6-DynamoDB-Activity-Log/](/5-Workshop/5.6-DynamoDB-Activity-Log/) |
| 6   | - **Apply to the project:** write async (`@Async`) logging from Spring Boot when a user views a product/searches, and from Lambda when an order is created; build the admin endpoint to look up a user's log | 06/26/2026 | 06/26/2026      | [/5-Workshop/5.6-DynamoDB-Activity-Log/](/5-Workshop/5.6-DynamoDB-Activity-Log/)                                      |
| 7   | - Attended **Event 3 — FCAJ Community Day** (joined online)                                                                                                                                                   | 06/27/2026 | 06/27/2026      | [/4-EventParticipated/4.3-Event3/](/4-EventParticipated/4.3-Event3/)                                                  |

### Week 10 Achievements:

- Understood how a partition key plus a sort key decide how data is partitioned and queried efficiently (query by exact `userId` plus a time range).
- Understood that DynamoDB's TTL automatically cleans up old data without writing a separate cleanup job.
- Learned to write "best-effort, asynchronous" logging — if DynamoDB has a hiccup, the customer's core action (viewing a product, searching) is completely unaffected.
- Applied it successfully to the project: confirmed on the Console that the correct `VIEW_PRODUCT`/`SEARCH` records (from the backend) and `ORDER_CREATED` record (from Lambda) all appear for the same user.
