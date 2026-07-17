---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Hiểu nền tảng networking của Amazon VPC: subnet, route table, gateway, security group.
* Dựng xong nền tảng mạng multi-AZ để toàn bộ hệ thống chạy trên đó.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu khái niệm cơ bản của VPC <br>&emsp; + CIDR block, subnet <br>&emsp; + Route Table <br>&emsp; + Internet Gateway <br>&emsp; + NAT Gateway | 27/04/2026 | 27/04/2026 | <https://000003.awsstudygroup.com> |
| 3 | - Tìm hiểu Security Group so với Network ACL <br> - Tìm hiểu VPC Resource Map để xem trực quan hạ tầng mạng | 28/04/2026 | 28/04/2026 | <https://000003.awsstudygroup.com> |
| 4-6 | - **Thực hành:** <br>&emsp; + Tạo 1 VPC trải 2 Availability Zone <br>&emsp; + Tạo 2 public subnet + 2 private subnet <br>&emsp; + Tạo Internet Gateway + NAT Gateway + route table <br>&emsp; + Tạo Security Group <br>&emsp; + Kiểm tra lại toàn bộ bằng Resource Map | 29/04/2026 | 01/05/2026 | <https://000003.awsstudygroup.com> |

### Kết quả đạt được tuần 2:

* Hiểu được sự khác nhau giữa public subnet và private subnet, và vì sao EC2/RDS nên đặt ở private subnet.
* Hiểu route table là thứ quyết định traffic đi đâu — route `0.0.0.0/0` qua Internet Gateway (public) hay qua NAT Gateway (private).
* Phân biệt được Security Group (stateful, theo từng instance) và Network ACL (stateless, theo từng subnet).
* Biết cách dùng VPC Resource Map để kiểm tra nhanh toàn bộ subnet/route table/gateway có nối đúng nhau không.
* Hiểu vì sao NAT Gateway tính phí theo giờ cộng thêm theo GB dù không có traffic — một khoản chi phí cố định cần tính trước.
