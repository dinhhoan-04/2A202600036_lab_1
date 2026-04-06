# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:
```bash
python template.py
```
Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature
Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> *Có thể thấy khi temperature tăng thì câu trả lời có xu hướng đa dạng và “thoáng” hơn, ít cố định vào một mẫu duy nhất. Ở temperature = 0.0, phản hồi thường ổn định và thiên về phương án an toàn; còn từ 0.5 đến 1.5, nội dung bắt đầu sáng tạo hơn nhưng cũng dễ thay đổi chi tiết và mức độ nhất quán.*

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> *Đặt temperature khoảng 0.2 đến 0.5, ưu tiên gần 0.3. Lý do là chatbot chăm sóc khách hàng cần trả lời ổn định, chính xác, nhất quán và tránh bịa thêm hoặc diễn đạt quá ngẫu hứng*

---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
> *GPT-4o đắt hơn khoảng 16.7 lần so với GPT-4o-mini.(0.01/0.0006=16.667)*

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
> *GPT-4o phù hợp khi bài toán cần chất lượng suy luận cao, độ chính xác tốt hơn và phản hồi tinh tế hơn vì mỗi câu trả lời sai hoặc kém chất lượng có thể gây tốn kém hơn nhiều.*
> *GPT-4o-mini phù hợp cho các tác vụ khối lượng lớn, cần tốc độ và tối ưu chi phí vì rẻ hơn rất nhiều mà vẫn đủ tốt cho nhu cầu phổ thông.*

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
> *Streaming quan trọng nhất trong những tình huống người dùng phải chờ phản hồi dài hoặc mang tính tương tác cao, chẳng hạn như chatbot, trợ lý AI, hỗ trợ khách hàng, hoặc khi sinh nội dung dài; vì nó tạo cảm giác hệ thống phản hồi ngay lập tức, giảm thời gian chờ cảm nhận được và cải thiện trải nghiệm người dùng. Ngược lại, non-streaming phù hợp hơn khi kết quả ngắn, cần đầy đủ rồi mới xử lý tiếp, hoặc khi hệ thống phía sau cần nhận toàn bộ output một lần để lưu trữ, kiểm tra, phân tích hay hiển thị theo lô; trong các trường hợp đó, non-streaming đơn giản hơn và dễ quản lý hơn.*


## Danh Sách Kiểm Tra Nộp Bài
- [x] Tất cả tests pass: `pytest tests/ -v`
- [x] `call_openai` đã triển khai và kiểm thử
- [x] `call_openai_mini` đã triển khai và kiểm thử
- [x] `compare_models` đã triển khai và kiểm thử
- [x] `streaming_chatbot` đã triển khai và kiểm thử
- [x] `retry_with_backoff` đã triển khai và kiểm thử
- [x] `batch_compare` đã triển khai và kiểm thử
- [x] `format_comparison_table` đã triển khai và kiểm thử
- [x] `exercises.md` đã điền đầy đủ
- [x] Sao chép bài làm vào folder `solution` và đặt tên theo quy định
