---
title: "Worklog Tuần 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

- Hòa nhập với team First Cloud AI Journey, nắm rõ nội quy và kỳ vọng trong đợt thực tập.
- Hình dung được AWS thực chất là gì trước khi đi sâu vào từng dịch vụ cụ thể.
- Có 1 tài khoản AWS dùng được, CLI đã cấu hình xong, và những bước tay đầu tiên với EC2.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Onboarding: tham gia hội thảo tại trường, gặp gỡ team FCAJ, đọc kỹ nội quy và những gì đơn vị thực tập kỳ vọng                                                                | 20/04/2026   | 20/04/2026      |                                           |
| 3   | - Khảo sát các nhóm dịch vụ chính của AWS (Compute, Storage, Networking, Database, ...) và hình dung chúng khớp vào đâu trong 1 hệ thống web điển hình                          | 21/04/2026   | 21/04/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Đăng ký tài khoản AWS Free Tier <br> - Cài đặt và cấu hình AWS CLI (Access Key, Secret Key, region mặc định)                                                                  | 22/04/2026   | 22/04/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 5-6 | - Tìm hiểu nền tảng EC2: instance type, AMI, EBS, Elastic IP, và cách kết nối SSH truyền thống <br> - **Thực hành:** tạo 1 EC2 instance, kết nối qua SSH, gắn thêm 1 EBS volume | 23/04/2026   | 24/04/2026      | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 1:

- Hình dung được AWS như 1 tập hợp các khối xây dựng (Compute, Storage, Networking, Database, ...) chứ không phải 1 sản phẩm duy nhất — cách nhìn này giúp các tuần sau dễ định vị hơn.
- Có 1 tài khoản AWS Free Tier hoạt động được, sẵn sàng dùng cho suốt đợt thực tập.
- Tự tin thao tác trên AWS Console để tìm và mở đúng dịch vụ cần dùng, dù chưa hiểu sâu bên trong nó làm gì.
- Cấu hình xong AWS CLI trọn vẹn (Access Key / Secret Key / region mặc định) và dùng nó để kiểm tra vài thứ cơ bản: định danh tài khoản, danh sách region, trạng thái EC2, quản lý key pair.
- Biết cách qua lại giữa Console và CLI để soi cùng 1 resource từ 2 góc nhìn khác nhau — thói quen này về sau hóa ra rất hữu ích lúc debug.
- Tự tay dựng được 1 EC2 instance đầu tiên và kết nối qua SSH — trải nghiệm nền tảng mà các tuần sau sẽ chủ động rời bỏ (chuyển sang Session Manager thay vì SSH key).
