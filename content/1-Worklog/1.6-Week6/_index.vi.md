---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Hiểu cách Application Load Balancer phân phối traffic tới nhiều EC2 instance qua target group và health check.
* Dựng xong baseline compute (launch template + 2 EC2 instance) trước khi thêm auto scaling tuần sau.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu khái niệm ALB: listener, target group, health check | 25/05/2026 | 25/05/2026 | <https://000006.awsstudygroup.com> |
| 3-4 | - Tìm hiểu Launch Template — chuẩn hóa cấu hình instance để tái sử dụng cho nhiều instance giống nhau | 26/05/2026 | 27/05/2026 | <https://000006.awsstudygroup.com> |
| 5-6 | - **Thực hành:** <br>&emsp; + Tạo Launch Template (AMI, instance type, IAM profile, user data) <br>&emsp; + Tạo ALB + Target Group (health check path `/actuator/health`) <br>&emsp; + Gắn tay 2 EC2 instance vào Target Group <br>&emsp; + Test qua tên DNS của ALB | 28/05/2026 | 29/05/2026 | <https://000006.awsstudygroup.com> |
| 7 | - Tham gia **buổi Event 2 — FCAJ Community Day** | 30/05/2026 | 30/05/2026 | [/4-EventParticipated/4.2-Event2/](/4-EventParticipated/4.2-Event2/) |

### Kết quả đạt được tuần 6:

* Hiểu ALB dùng health check theo chu kỳ để biết instance nào "khỏe" mới nhận traffic — instance lỗi tự động bị loại khỏi vòng quay.
* Hiểu Launch Template là 1 "khuôn" định nghĩa một lần, dùng lại được cho nhiều instance thay vì tạo tay từng cái.
* Học được cách chọn health check path/threshold hợp lý cho app Spring Boot (dùng endpoint `/actuator/health`).
* Nhận ra hạn chế của việc gắn tay instance vào target group (`aws_lb_target_group_attachment`) — mỗi khi số lượng instance đổi phải tự thêm/bớt, không có gì tự động cả. Đây chính là khoảng trống mà Auto Scaling Group sẽ giải quyết ở tuần sau.
