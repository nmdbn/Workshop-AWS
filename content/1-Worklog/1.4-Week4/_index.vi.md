---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

- Hiểu nền tảng RDS, đặc biệt là Multi-AZ để tự động failover.
- Kết nối ứng dụng chạy trên EC2 tới database RDS nằm trong private subnet.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                    | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                     |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | --------------- | ---------------------------------- |
| 2   | - Tìm hiểu khái niệm RDS: engine, storage, Security Group cho DB, DB Subnet Group <br> - Tham gia học tập trên văn phòng                                                                                     | 11/05/2026   | 11/05/2026      | <https://000005.awsstudygroup.com> |
| 3   | - Tìm hiểu Multi-AZ: standby instance, tự động failover, so với Single-AZ                                                                                                                                    | 12/05/2026   | 12/05/2026      | <https://000005.awsstudygroup.com> |
| 4   | - Tìm hiểu automated backup, retention period, final snapshot                                                                                                                                                | 13/05/2026   | 13/05/2026      | <https://000005.awsstudygroup.com> |
| 5-6 | - **Thực hành:** <br>&emsp; + Tạo RDS PostgreSQL trong private subnet, bật Multi-AZ <br>&emsp; + Giới hạn Security Group của DB chỉ cho phép Security Group của EC2 kết nối <br>&emsp; + Test kết nối từ EC2 | 14/05/2026   | 15/05/2026      | <https://000005.awsstudygroup.com> |

### Kết quả đạt được tuần 4:

- Hiểu Multi-AZ nghĩa là có 1 bản standby ở AZ khác, tự động failover khi có sự cố — không cần đổi connection string vì cùng 1 endpoint DNS tự trỏ lại.
- Phân biệt được Multi-AZ (high availability, cùng region) khác với Read Replica (scale đọc, có thể khác region).
- Hiểu vì sao RDS nên đặt ở private subnet với Security Group chỉ cho phép đúng Security Group của EC2, không bao giờ mở `0.0.0.0/0`.
- Học được cách cấu hình automated backup với retention period, và final snapshot dùng để làm gì khi xoá instance.
- Nhận ra Multi-AZ tốn gần gấp đôi chi phí Single-AZ — một đánh đổi trực tiếp giữa uptime và tiền.
