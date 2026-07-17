---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

- Học nền tảng NoSQL với DynamoDB.
- Áp dụng trực tiếp vào project Maison Édition: xây tính năng activity-log/audit-trail.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                          | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                                                        |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | --------------------------------------------------------------------------------------------------------------------- |
| 2   | - Tìm hiểu khái niệm cơ bản DynamoDB: partition key, sort key, billing mode (on-demand so với provisioned), TTL <br> - Tham gia học tập trên văn phòng                                             | 22/06/2026   | 22/06/2026      | <https://000060.awsstudygroup.com>                                                                                    |
| 3-4 | - Tìm hiểu Global Secondary Index — khi nào cần dùng, khác gì so với primary key                                                                                                                   | 23/06/2026   | 24/06/2026      | <https://000060.awsstudygroup.com>                                                                                    |
| 5   | - **Áp dụng vào project:** tạo bảng `activity-log` cho Maison Édition (hash `userId`, range `timestamp`), bật TTL để tự xoá sau 90 ngày                                                            | 25/06/2026   | 25/06/2026      | <https://000060.awsstudygroup.com> · [/5-Workshop/5.6-DynamoDB-Activity-Log/](/5-Workshop/5.6-DynamoDB-Activity-Log/) |
| 6   | - **Áp dụng vào project:** viết code ghi log bất đồng bộ (`@Async`) từ Spring Boot khi user xem sản phẩm/tìm kiếm, và từ Lambda khi đơn hàng được tạo; làm endpoint admin để xem lại log theo user | 26/06/2026   | 26/06/2026      | [/5-Workshop/5.6-DynamoDB-Activity-Log/](/5-Workshop/5.6-DynamoDB-Activity-Log/)                                      |
| 7   | - Tham gia **buổi Event 3 — FCAJ Community Day** (tham dự online)                                                                                                                                  | 27/06/2026   | 27/06/2026      | [/4-EventParticipated/4.3-Event3/](/4-EventParticipated/4.3-Event3/)                                                  |

### Kết quả đạt được tuần 10:

- Hiểu partition key kết hợp sort key quyết định cách dữ liệu được phân vùng và truy vấn hiệu quả (query đúng theo `userId` cộng khoảng thời gian).
- Hiểu TTL của DynamoDB giúp tự động dọn dữ liệu cũ mà không cần viết job cleanup riêng.
- Học được cách ghi log "best-effort, bất đồng bộ" — nếu DynamoDB tạm thời trục trặc, thao tác chính của khách (xem sản phẩm, tìm kiếm) hoàn toàn không bị ảnh hưởng.
- Áp dụng thành công vào project: xác nhận trên Console thấy đúng record `VIEW_PRODUCT`/`SEARCH` (từ backend) và `ORDER_CREATED` (từ Lambda) cho cùng 1 user.
