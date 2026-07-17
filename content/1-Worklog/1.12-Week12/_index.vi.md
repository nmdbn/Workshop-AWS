---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* Rà soát lại toàn bộ kiến trúc Maison Édition đã xây trong 11 tuần qua.
* Phân tích và tối ưu chi phí, thực hành tháo dỡ hạ tầng an toàn.
* Tổng kết lại toàn bộ những gì đã học được trong đợt thực tập.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu các khái niệm tối ưu chi phí AWS: Reserved Instances, Savings Plans, right-sizing | 06/07/2026 | 06/07/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3-4 | - Rà soát lại toàn bộ kiến trúc đã làm (VPC → EC2/ASG → RDS → S3/CloudFront → Redis → SQS/Lambda → DynamoDB → CloudWatch/SNS → WAF) và liệt kê từng khoản chi phí | 07/07/2026 | 08/07/2026 | [/5-Workshop/5.9-Cost-Cleanup/](/5-Workshop/5.9-Cost-Cleanup/) |
| 5 | - **Áp dụng vào project:** phân tích bảng chi phí thật của Maison Édition (NAT Gateway là khoản lớn nhất), đề xuất phương án tối ưu (giảm số NAT Gateway, cân nhắc tắt Multi-AZ/WAF khi không cần) | 09/07/2026 | 09/07/2026 | [/2-Proposal/](/2-Proposal/) · [/5-Workshop/5.9-Cost-Cleanup/](/5-Workshop/5.9-Cost-Cleanup/) |
| 6-8 | - **Áp dụng vào project:** thực hành gỡ hạ tầng đúng thứ tự (backend trước, frontend sau) và dọn các resource dễ bị bỏ sót (image trong ECR, CloudWatch Logs cũ, các version object cũ trong S3) | 10/07/2026 | 12/07/2026 | [/5-Workshop/5.9-Cost-Cleanup/](/5-Workshop/5.9-Cost-Cleanup/) |

### Kết quả đạt được tuần 12:

* Nhìn lại được toàn cảnh 1 hệ thống multi-tier hoàn chỉnh trên AWS — từ networking, compute, database, cache, đến xử lý bất đồng bộ, NoSQL, giám sát và bảo mật lớp ngoài — và hiểu được cách các phần ghép vào nhau.
* Học được cách đọc 1 bảng chi phí AWS và nhận ra đâu là khoản lớn nhất, dễ bị bỏ qua nhất (NAT Gateway).
* Hiểu rằng tối ưu chi phí luôn đi kèm đánh đổi (Multi-AZ đổi lấy uptime, WAF đổi lấy bảo mật, số NAT Gateway đổi lấy khả năng chịu lỗi AZ) — không có lựa chọn nào hoàn toàn miễn phí.
* Học được thứ tự tháo dỡ hạ tầng an toàn và những resource "ẩn" hay bị quên khi dọn dẹp (image trong ECR, log group cũ, version cũ của object trong S3).
* Tổng kết: từ chỗ chưa biết AWS là gì (tuần 1) đến việc tự tay dựng và vận hành một hệ thống production thật cho project Maison Édition (tuần 12).
