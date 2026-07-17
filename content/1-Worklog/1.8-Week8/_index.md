---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Learn in-memory caching with ElastiCache Redis.
* Integrate application-level caching to reduce read load on the database.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn ElastiCache Redis concepts: cluster, node type, cluster mode vs non-cluster mode | 06/08/2026 | 06/08/2026 | <https://000061.awsstudygroup.com> |
| 3 | - Learn cache TTL and eviction strategy | 06/09/2026 | 06/09/2026 | <https://000061.awsstudygroup.com> |
| 4 | - **Practice:** create a Redis cluster (single node, non-cluster mode) in a private subnet, Security Group opening port 6379 only to the EC2 Security Group | 06/10/2026 | 06/10/2026 | <https://000061.awsstudygroup.com> |
| 5 | - **Practice:** add `@Cacheable` to the Spring Boot app for product detail (short TTL, since it holds stock quantity) and categories/brands (longer TTL); test with `redis-cli` over Session Manager | 06/11/2026 | 06/11/2026 | <https://000061.awsstudygroup.com> |

### Week 8 Achievements:

* Understood the cache-aside pattern: read the cache first, on a miss read the DB then write back to cache — reducing read load on RDS for data that doesn't change often.
* Understood why different data should use different TTLs — fast-changing data (stock quantity) needs a short TTL, slow-changing data (category/brand) can use a longer one.
* Learned how to keep the app alive when Redis is down — a fallback that reads straight from the DB instead of throwing an exception.
* Practiced testing Redis from a dedicated EC2 instance inside the private subnet, using Session Manager plus `docker run redis-cli` — no need to ever expose Redis to the internet.
* Understood the difference between cluster mode (multiple shards, horizontal scaling) and non-cluster mode (a single primary node, simpler, enough for small traffic).
