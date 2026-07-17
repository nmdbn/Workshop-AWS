---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Học caching trong bộ nhớ với ElastiCache Redis.
* Tích hợp cache ở tầng ứng dụng để giảm tải đọc cho database.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu khái niệm ElastiCache Redis: cluster, node type, cluster mode so với non-cluster mode | 08/06/2026 | 08/06/2026 | <https://000061.awsstudygroup.com> |
| 3 | - Tìm hiểu TTL của cache và chiến lược eviction | 09/06/2026 | 09/06/2026 | <https://000061.awsstudygroup.com> |
| 4 | - **Thực hành:** tạo cluster Redis (1 node, non-cluster mode) trong private subnet, Security Group chỉ mở port 6379 cho Security Group của EC2 | 10/06/2026 | 10/06/2026 | <https://000061.awsstudygroup.com> |
| 5 | - **Thực hành:** thêm `@Cacheable` vào Spring Boot cho product detail (TTL ngắn vì có tồn kho) và categories/brands (TTL dài hơn); test bằng `redis-cli` qua Session Manager | 11/06/2026 | 11/06/2026 | <https://000061.awsstudygroup.com> |

### Kết quả đạt được tuần 8:

* Hiểu cơ chế cache-aside: đọc cache trước, miss thì đọc DB rồi ghi lại vào cache — giảm tải đọc cho RDS với dữ liệu ít thay đổi.
* Hiểu vì sao các loại dữ liệu khác nhau nên dùng TTL khác nhau — dữ liệu đổi nhanh (tồn kho) cần TTL ngắn, dữ liệu ít đổi (category/brand) dùng TTL dài hơn.
* Học được cách giữ app sống khi Redis bị down — cơ chế fallback đọc thẳng từ DB thay vì throw exception.
* Thực hành test Redis từ 1 EC2 riêng nằm trong private subnet, dùng Session Manager kết hợp `docker run redis-cli` — không bao giờ cần mở Redis ra internet.
* Hiểu sự khác nhau giữa cluster mode (nhiều shard, scale ngang) và non-cluster mode (1 node chính duy nhất, đơn giản hơn, đủ dùng cho traffic nhỏ).
