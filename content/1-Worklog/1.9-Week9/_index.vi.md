---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Học messaging bất đồng bộ với SQS và compute theo sự kiện với Lambda.
* Áp dụng trực tiếp vào project Maison Édition: xây luồng xử lý đơn hàng thật.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu khái niệm SQS: standard queue so với FIFO queue, visibility timeout, Dead Letter Queue, `maxReceiveCount` | 15/06/2026 | 15/06/2026 | <https://000077.awsstudygroup.com> |
| 3 | - Tìm hiểu AWS Lambda cơ bản: trigger, event source mapping, IAM role riêng cho Lambda, batch size | 16/06/2026 | 16/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Tìm hiểu Amazon SES: chế độ sandbox, phải verify cả email người gửi lẫn người nhận mới gửi được | 17/06/2026 | 17/06/2026 | <https://000077.awsstudygroup.com> |
| 5 | - **Áp dụng vào project:** triển khai SQS queue + DLQ cho luồng đặt hàng của Maison Édition | 18/06/2026 | 18/06/2026 | <https://000077.awsstudygroup.com> · [/5-Workshop/5.5-SQS-Lambda-Order/](/5-Workshop/5.5-SQS-Lambda-Order/) |
| 6 | - **Áp dụng vào project:** viết Lambda `order-processor` (Node.js), gửi email xác nhận qua SES, publish message từ Spring Boot ngay sau khi lưu đơn vào RDS (best-effort, không chặn phản hồi) | 19/06/2026 | 19/06/2026 | [/5-Workshop/5.5-SQS-Lambda-Order/](/5-Workshop/5.5-SQS-Lambda-Order/) |

### Kết quả đạt được tuần 9:

* Hiểu vì sao tách việc gửi email ra khỏi luồng chính (qua SQS + Lambda) giúp khách hàng nhận phản hồi checkout nhanh hơn, không phải chờ SES.
* Hiểu Dead Letter Queue kết hợp `maxReceiveCount` giúp cô lập message cứ lỗi lặp lại, thay vì retry vô hạn lần.
* Phân biệt được publish "best-effort" (không throw lỗi nếu SQS down, chỉ log warning) với việc publish bắt buộc phải thành công mới coi là hoàn tất đơn hàng.
* Học được cách debug SES ở chế độ sandbox — hiểu vì sao phải verify cả người gửi lẫn người nhận khi còn ở sandbox.
* Áp dụng thành công vào project thật: đặt 1 đơn hàng và nhận được email xác nhận chỉ trong vài chục giây.
