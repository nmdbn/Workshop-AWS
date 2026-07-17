---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Học giám sát/cảnh báo tập trung với CloudWatch + SNS và bảo vệ lớp ngoài với WAF.
* Áp dụng cả hai trực tiếp để tăng cường bảo mật/giám sát cho hệ thống Maison Édition đang chạy.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu CloudWatch: Metrics, Logs, Alarms, Dashboards | 29/06/2026 | 29/06/2026 | <https://000008.awsstudygroup.com> |
| 3 | - Tìm hiểu SNS pub/sub và quy trình xác nhận subscription qua email | 30/06/2026 | 30/06/2026 | <https://000077.awsstudygroup.com> |
| 4-5 | - Tìm hiểu WAF: managed rule group, custom rule, rate-based rule; Web ACL cho CloudFront bắt buộc khai báo ở `us-east-1` | 01/07/2026 | 02/07/2026 | <https://000026.awsstudygroup.com> |
| 6 | - **Áp dụng vào project:** cấu hình 4 CloudWatch alarm (CPU của ASG, ALB 5xx, RDS connections, SQS DLQ) gửi cảnh báo qua SNS email; bật WAF cho CloudFront với 3 managed rule group + 1 rate-based rule; test bằng cách bơm message giả vào DLQ và gửi request SQLi/XSS giả để xác nhận bị chặn | 03/07/2026 | 03/07/2026 | <https://000026.awsstudygroup.com> · [/5-Workshop/5.7-CloudWatch-SNS/](/5-Workshop/5.7-CloudWatch-SNS/) · [/5-Workshop/5.8-WAF/](/5-Workshop/5.8-WAF/) |
| 7 | - Tham gia **buổi Event 4 — FCAJ Community Day** | 04/07/2026 | 04/07/2026 | [/4-EventParticipated/4.4-Event4/](/4-EventParticipated/4.4-Event4/) |

### Kết quả đạt được tuần 11:

* Hiểu sự khác nhau giữa CloudWatch Metrics (số liệu), Logs (log chi tiết), và Alarms (ngưỡng cảnh báo) — 3 mảnh riêng nhưng bổ trợ nhau.
* Hiểu vì sao Web ACL cho CloudFront bắt buộc khai báo ở `us-east-1` dù CloudFront là dịch vụ global.
* Học được cách test alarm an toàn (bơm message giả vào DLQ) thay vì phải chờ sự cố thật xảy ra.
* Hiểu rate-based rule của WAF hoạt động theo cửa sổ trượt 5 phút, khác với việc chặn cố định theo IP.
* Áp dụng thành công: nhận được email cảnh báo thật sau khi cố tình kích hoạt alarm, và xác nhận request SQLi/XSS giả bị WAF chặn trả về `403`.
