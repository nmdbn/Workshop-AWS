---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Hiểu nền tảng EC2: AMI, instance type, IAM role so với access key.
* Học cách truy cập instance an toàn mà không cần SSH, dùng Systems Manager Session Manager.
* Cài Docker để chuẩn bị chạy ứng dụng dưới dạng container.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu EC2 cơ bản: AMI, instance type, EBS volume, IAM Instance Profile | 04/05/2026 | 04/05/2026 | <https://000004.awsstudygroup.com> |
| 3 | - Tìm hiểu IAM Role so với Access Key khi cấp quyền cho ứng dụng truy cập dịch vụ AWS | 05/05/2026 | 05/05/2026 | <https://000048.awsstudygroup.com> |
| 4-5 | - Tìm hiểu Systems Manager Session Manager — kết nối vào private instance không cần SSH key, không cần mở port 22 | 06/05/2026 | 07/05/2026 | <https://000058.awsstudygroup.com> |
| 6 | - **Thực hành:** <br>&emsp; + Tạo EC2 instance gắn IAM Role (không dùng key pair) <br>&emsp; + Kết nối qua Session Manager <br>&emsp; + Cài Docker + Docker Compose | 08/05/2026 | 08/05/2026 | <https://000004.awsstudygroup.com> |

### Kết quả đạt được tuần 3:

* Hiểu launch template dùng để chuẩn hóa cấu hình 1 instance (AMI, instance type, IAM profile, user data) để tái sử dụng thay vì tạo tay từng lần.
* Hiểu vì sao gắn IAM Role cho EC2 an toàn hơn hẳn so với việc gán cứng access key vào server hoặc vào code.
* Học được cách kết nối vào private instance (không có public IP, không mở port 22) hoàn toàn qua Session Manager.
* Phân biệt được user data (chỉ chạy 1 lần lúc boot) với việc tự SSH vào rồi cấu hình tay.
* Cài đặt thành công Docker trên Amazon Linux 2023, hiểu vì sao đóng gói app thành container giúp deploy nhất quán trên nhiều instance.
