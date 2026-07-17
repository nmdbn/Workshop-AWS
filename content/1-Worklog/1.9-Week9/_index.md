---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Learn asynchronous messaging with SQS and event-driven compute with Lambda.
* Apply it directly to the Maison Édition project: build the real order-processing flow.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn SQS concepts: standard vs FIFO queue, visibility timeout, Dead Letter Queue, `maxReceiveCount` | 06/15/2026 | 06/15/2026 | <https://000077.awsstudygroup.com> |
| 3 | - Learn AWS Lambda basics: triggers, event source mapping, a dedicated IAM role for Lambda, batch size | 06/16/2026 | 06/16/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Learn Amazon SES: sandbox mode, verifying sender/recipient email before sending is allowed | 06/17/2026 | 06/17/2026 | <https://000077.awsstudygroup.com> |
| 5 | - **Apply to the project:** implement the SQS queue + DLQ for Maison Édition's checkout flow | 06/18/2026 | 06/18/2026 | <https://000077.awsstudygroup.com> · [/5-Workshop/5.5-SQS-Lambda-Order/](/5-Workshop/5.5-SQS-Lambda-Order/) |
| 6 | - **Apply to the project:** write the Node.js `order-processor` Lambda, send the confirmation email via SES, publish the message from Spring Boot right after the order is saved to RDS (best-effort, non-blocking) | 06/19/2026 | 06/19/2026 | [/5-Workshop/5.5-SQS-Lambda-Order/](/5-Workshop/5.5-SQS-Lambda-Order/) |

### Week 9 Achievements:

* Understood why pulling email-sending out of the main request path (via SQS + Lambda) lets the customer get a fast checkout response instead of waiting on SES.
* Understood how a Dead Letter Queue plus `maxReceiveCount` isolates a message that keeps failing, instead of retrying it forever.
* Learned to distinguish a "best-effort" publish (doesn't throw if SQS is down, just logs a warning) from a publish that must succeed before an order can be considered complete.
* Learned to debug SES sandbox mode — understood why both sender and recipient must be verified while still in sandbox.
* Applied it successfully to the real project: placed an order and received the confirmation email within seconds.
