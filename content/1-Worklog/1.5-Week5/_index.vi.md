---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Học cách host static site trên S3 và tăng tốc/bảo vệ bằng CloudFront.
* Hiểu bucket private phục vụ qua Origin Access Control (OAC) thay vì bucket public.
* Tìm hiểu S3 Gateway VPC Endpoint để truy cập private từ EC2.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu S3 static website hosting cơ bản, Block Public Access | 18/05/2026 | 18/05/2026 | <https://000057.awsstudygroup.com> |
| 3 | - Tìm hiểu CloudFront cơ bản: origin, cache behavior, OAC so với bucket public | 19/05/2026 | 19/05/2026 | <https://000094.awsstudygroup.com> |
| 4 | - Tìm hiểu S3 Gateway VPC Endpoint — cho EC2 truy cập S3 không cần qua NAT/internet | 20/05/2026 | 20/05/2026 | <https://000111.awsstudygroup.com> |
| 5-6 | - **Thực hành:** <br>&emsp; + Tạo S3 bucket cho FE build (chặn toàn bộ public access) <br>&emsp; + Gắn CloudFront dùng OAC <br>&emsp; + Thêm bucket riêng cho ảnh sản phẩm với path pattern `/media/*` | 21/05/2026 | 22/05/2026 | <https://000057.awsstudygroup.com> |
| 7 | - Tham gia **buổi Event 1 — FCAJ Community Day** | 23/05/2026 | 23/05/2026 | [/4-EventParticipated/4.1-Event1/](/4-EventParticipated/4.1-Event1/) |

### Kết quả đạt được tuần 5:

* Hiểu vì sao bucket private kết hợp CloudFront OAC an toàn hơn hẳn bucket public — chỉ CloudFront được đọc object, người dùng không bao giờ chạm trực tiếp vào S3.
* Phân biệt được Gateway VPC Endpoint (miễn phí, chỉ dùng cho S3/DynamoDB) và Interface VPC Endpoint (tính phí, dùng PrivateLink cho các service khác).
* Hiểu cache behavior của CloudFront cho phép nhiều path pattern (`/media/*`, `/api/*`, `/*`) trỏ về nhiều origin khác nhau trên cùng 1 domain — tránh hoàn toàn lỗi CORS.
* Học cách chọn cache policy khác nhau cho nội dung tĩnh (CachingOptimized) và API động (CachingDisabled).
* Hiểu vì sao S3 Gateway Endpoint giúp EC2 upload ảnh lên S3 mà không tốn phí data-transfer của NAT Gateway.
