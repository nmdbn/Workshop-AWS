---
title: "FCAJ Community Day"
date : 2026-07-16
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

# Bài thu hoạch "FCAJ Community Day 23 - 5 - 2026"

## Mục Đích Của Sự Kiện
* Chia sẻ best practice về context engineering khi làm việc với AI
* Giới thiệu các dịch vụ/nền tảng agentic AI mới của AWS (Amazon Quick Suite, CloudFront flat-rate pricing, Bedrock AgentCore)
* Trình bày kiến thức chuyên sâu về hạ tầng cloud: tối ưu chi phí, bảo mật, độ tin cậy, hiệu năng CDN
* Phân tích hành vi thực sự của LLM (tính non-determinism) và cách xây dựng hệ thống AI đáng tin cậy
* Chia sẻ kinh nghiệm xây dựng sản phẩm AI thực tế qua hackathon và ứng dụng multi-agent trong ngành ngân hàng

## Danh Sách Diễn Giả
* Tinh Truong - Platform Engineer, GoTymeX
* Pham Ngoc Hai Anh - G-Asia Pacific Vietnam, AWS Community Builder
* Nguyen Tuan Thinh - DevOps Engineer, First Cloud AI Journey (FCAJ)
* Team VIB - LotusHacks 2026
* Duc Dao - Solution Architect, Cloud Kinetics
* Vy Lam - Senior Business Systems Analyst, VPBank

## Nội Dung Nổi Bật

**1. Context Is Everything (Tinh Truong)**
Nhiều câu trả lời AI kém là do context yếu chứ không phải model tệ. Chỉ ra 3 lỗi thường gặp (nhồi quá nhiều thông tin, nói lại điều AI đã biết, không nêu rõ mục tiêu/ràng buộc), giới thiệu framework 4 bước chuẩn bị context (Goal – Relevant info – Constraints – Success criteria) và mô hình tiến hóa Prompt → Context → Memory.

**2. Friendly AI Assistant w/ Amazon Quick (Pham Ngoc Hai Anh)**
Giới thiệu Amazon Quick Suite — nền tảng agentic AI hợp nhất, kết hợp dữ liệu công ty (40+ connector), tri thức thế giới và hành động (BI, automation, chat, research) trong một trải nghiệm có governance đi kèm. Demo use case PM assistant: tự động tạo biên bản họp, gửi email stakeholder, lên lịch họp tiếp theo.

**3. From Edge to Origin: CloudFront as Your Foundation (Nguyen Tuan Thinh)**
CloudFront không chỉ là CDN mà là nền tảng bảo vệ/tối ưu ứng dụng. Điểm nhấn là gói giá cố định (flat-rate) mới thay cho pay-as-you-go để tránh bill tăng đột biến. Đi qua 4 mảng: tối ưu chi phí (nén HTTP giảm 82% dung lượng), bảo mật (chống DDoS tại edge, mTLS, origin cloaking, signed URL), độ tin cậy (origin failover, cache khi origin sập) và hiệu năng (cache đa lớp, HTTP/3, xử lý logic tại edge).

**4. UTMorpho — Building from Idea to Reality (Team VIB)**
Hành trình 36 giờ tại hackathon LotusHacks xây dựng UTMorpho — AI agent sinh UI và cho chỉnh sửa trực tiếp trên canvas (WYSIWYG cho UI do AI tạo ra), giải quyết vấn đề "re-prompt làm lệch design" của các công cụ gen-UI hiện tại. Chia sẻ khó khăn (AI sinh dư thừa, giới hạn token, kiệt sức) và bài học: ý tưởng tốt đến từ sự bực bội thật sự, team chemistry quan trọng hơn kỹ năng, AI là đồng đội chứ không chỉ công cụ.

**5. Non-Determinism of "Deterministic" LLM Settings (Duc Dao)**
Phản biện niềm tin phổ biến rằng temperature = 0 đảm bảo output LLM tái lập 100%. Nghiên cứu trên 5 LLM, 8 tác vụ cho thấy độ chính xác có thể lệch tới 70% giữa các lần chạy giống hệt nhau, do phép tính dấu phẩy động trên GPU không có tính kết hợp và cơ chế inference batching. Đề xuất: chạy nhiều lần lấy đa số phiếu, dùng structured output, và thiết kế hệ thống chấp nhận LLM là xác suất chứ không tất định.

**6. Enterprise-Grade Multi-Agent System: Startup Credit Scoring (Vy Lam)**
Mô hình chấm điểm tín dụng ngân hàng truyền thống không phù hợp với startup vì dữ liệu đa chiều và phi cấu trúc. Đề xuất kiến trúc "virtual credit committee" gồm nhiều agent chuyên biệt (Financial, Market, Team, Risk, Compliance) do 1 Manager điều phối, cho ra credit score, risk rating và audit trail đầy đủ. Kèm 6 trụ cột enterprise-grade, guardrail nhiều lớp, và ROI ước tính: giảm 95% thời gian xử lý, tăng gấp đôi tỷ lệ duyệt, tiết kiệm 95% chi phí.

## Những Gì Học Được

**Tư duy thiết kế AI**
* Chất lượng context quan trọng hơn số lượng — nên chuẩn bị goal, constraints, success criteria trước khi giao việc cho AI
* AI nên được xem như một cộng sự cần được cung cấp đúng thông tin, không phải một "cỗ máy đọc được ý nghĩ"
* Ý tưởng sản phẩm tốt thường đến từ nỗi bực bội thực tế trong công việc hàng ngày, không phải chạy theo xu hướng

**Kiến trúc kỹ thuật**
* Multi-agent architecture (chuyên môn hóa, checks & balances, audit trail) vượt trội single-agent cho các quyết định phức tạp, rủi ro cao
* Bảo mật và hạ tầng cần thiết kế nhiều lớp: từ perimeter/edge đến network, identity, application, data
* LLM ở temp = 0 vẫn có thể cho kết quả không nhất quán — cần thiết kế hệ thống chấp nhận tính xác suất của AI, không giả định deterministic tuyệt đối

**Chiến lược triển khai**
* Ưu tiên các "quick win" chi phí thấp, hiệu quả cao (compression, HTTP/3, structured output) trước khi đầu tư lớn
* Triển khai hệ thống AI/cloud nên đi theo roadmap phân pha (Foundation → Integration → Pilot → Scale), đo lường ROI rõ ràng
* Enterprise-grade là tư duy cần có từ ngày đầu (bảo mật, compliance, vận hành), không phải bổ sung sau

**Ứng dụng vào công việc**
* Áp dụng framework chuẩn bị context khi làm việc với AI trong công việc hàng ngày
* Rà soát lại các hệ thống dùng CDN/LLM production để tối ưu chi phí và giảm rủi ro (bill spike, non-determinism)
* Cân nhắc mô hình multi-agent cho các bài toán ra quyết định nhiều chiều dữ liệu
* Thử nghiệm các nền tảng agentic AI (Amazon Quick Suite, Bedrock AgentCore) để tự động hóa tác vụ lặp lại
