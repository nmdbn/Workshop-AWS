---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Chuyển từ 2 instance cố định sang Auto Scaling Group thật, có scaling policy theo CPU.
* Hiểu thử thách "self-bootstrap" — instance mới do ASG tự tạo phải tự chạy được app mà không cần thao tác tay nào.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu khái niệm ASG: min/max/desired capacity, health check type (EC2 so với ELB), các loại scaling policy (target tracking, step, scheduled, predictive) | 01/06/2026 | 01/06/2026 | <https://000006.awsstudygroup.com> |
| 3 | - Tìm hiểu vì sao user data trong launch template phải "tự đủ" — instance mới không thể phụ thuộc vào script deploy tay | 02/06/2026 | 02/06/2026 | <https://000006.awsstudygroup.com> |
| 4-5 | - **Thực hành:** viết và debug user data (login ECR, pull image, chạy container) — gặp lỗi Terraform hiểu nhầm biến bash `${INSTANCE_ID}` thành cú pháp interpolation của chính nó | 03/06/2026 | 04/06/2026 | <https://000006.awsstudygroup.com> |
| 6 | - **Thực hành:** tạo Auto Scaling Group (min 2 / max 4 / desired 2), gắn policy target-tracking theo CPU trung bình 60%, gỡ bỏ attachment thủ công, xác nhận instance mới tự bootstrap và đăng ký khỏe mạnh | 05/06/2026 | 05/06/2026 | <https://000006.awsstudygroup.com> |

### Kết quả đạt được tuần 7:

* Hiểu rõ sự khác nhau giữa health check type `EC2` (chỉ theo status check phần cứng) và `ELB` (theo đúng health check của target group) — quan trọng để ASG biết khi nào cần thay instance.
* Hiểu target-tracking scaling policy tự tính toán số instance cần thêm/bớt để giữ 1 metric (CPU) quanh 1 ngưỡng, không cần tự viết alarm cộng step-scaling policy.
* Học được bài học quan trọng nhất tuần này: launch template/user data phải "tự đủ" — ASG có thể tự tạo instance mới bất cứ lúc nào (scale-out, thay instance lỗi), nếu user data không tự cấu hình xong app thì instance đó vĩnh viễn không pass health check, ASG sẽ lặp tạo-xoá liên tục, tốn tiền vô ích.
* Học được cách debug lỗi Terraform interpolation — `${...}` trong heredoc bị Terraform hiểu là cú pháp của chính nó, trừ khi viết biến bash thuần `$VAR` không có dấu ngoặc nhọn.
* Hiểu vì sao nên apply theo 2 giai đoạn (dựng ASG mới song song với instance cũ trước, rồi mới xoá instance cũ) để tránh khoảng trống downtime lúc chuyển đổi.
