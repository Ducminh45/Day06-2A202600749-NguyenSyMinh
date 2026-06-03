# Evidence Pack

Nộp kèm thin SPEC cuối Day 05.

## 1. Nhóm và track

**Tên nhóm:** StayMate AI Concierge  
**Track:** Travel & Hospitality  
**Product/app đã chọn:** Vinpearl Booking & Support System  
**Build slice đang nghĩ:** StayMate AI Concierge - Chatbot AI tương tác trực tiếp với khách hàng (Customer-facing Agent) trên website Vinpearl, tập trung hỗ trợ khách hàng giải đáp câu hỏi về voucher, hỗ trợ đặt lịch, đổi trả phòng, và hỏi đáp các thông tin tiện ích nội khu (xe điện, buffet, khu vui chơi).

## 2. Self-use evidence

Nhóm tự dùng app/workflow và ghi lại điểm gãy.

| Observation | Screenshot/link | Path liên quan | Điều học được |
|---|---|---|---|
| Giao diện đặt phòng Vinpearl yêu cầu khách hàng nhập thông tin đặt chỗ phức tạp nhưng không hỗ trợ kiểm tra điều kiện voucher hay tích hợp hỏi đáp chính sách trực quan, khiến khách phải gọi hotline hoặc gửi email chờ xác nhận thủ công. | [cap/Screenshot 16-32-39](file:///home/dholmes/AIInAction/Day5/Batch02-Day05-AI-Product-Labs/02-group-spec/cap/Screenshot%20from%202026-06-03%2016-32-39.png) <br> [cap/2026-06-03_162653.png](file:///home/dholmes/AIInAction/Day5/Batch02-Day05-AI-Product-Labs/02-group-spec/cap/2026-06-03_162653.png) | Happy / Low-confidence | Khách hàng cần chatbot hỗ trợ kiểm tra điều kiện và áp mã voucher trực tiếp khi đang xem phòng. |
| Quy định đổi trả phòng và chính sách hoàn/hủy voucher rất khắt khe, dễ dẫn tới hiểu lầm hoặc ức chế nếu không được giải thích rõ từ đầu. | [cap/Screenshot 16-37-14](file:///home/dholmes/AIInAction/Day5/Batch02-Day05-AI-Product-Labs/02-group-spec/cap/Screenshot%20from%202026-06-03%2016-37-14.png) <br> [cap/2026-06-03_162822.png](file:///home/dholmes/AIInAction/Day5/Batch02-Day05-AI-Product-Labs/02-group-spec/cap/2026-06-03_162822.png) | Failure / Correction | Chatbot cần làm rõ chính sách đổi trả phòng và hướng dẫn chính xác quy trình thực hiện ngay trong khung chat để khách hàng dễ dàng theo dõi. |
| Thông tin về các tiện ích trong resort (hồ bơi, spa, công viên nước, safari, xe điện) nằm rải rác ở nhiều trang con khác nhau, gây khó khăn cho khách muốn tra cứu nhanh giờ hoạt động hoặc đặt lịch dịch vụ. | [cap/Screenshot 16-32-58](file:///home/dholmes/AIInAction/Day5/Batch02-Day05-AI-Product-Labs/02-group-spec/cap/Screenshot%20from%202026-06-03%2016-32-58.png) <br> [cap/2026-06-03_162911.png](file:///home/dholmes/AIInAction/Day5/Batch02-Day05-AI-Product-Labs/02-group-spec/cap/2026-06-03_162911.png) | Happy | Khách hàng cần kênh hỏi đáp (Q&A) tiện ích resort tức thì 24/7 để tối ưu hóa thời gian trải nghiệm kỳ nghỉ. |

## 3. User / review / social evidence

Nguồn có thể là review App Store/Play, group, comment, phỏng vấn nhanh, hoặc nguồn public khác.

| Quote / review / observation | Nguồn | User là ai? | Pain/failure mode |
|---|---|---|---|
| "Một số khách hàng phàn nàn về việc nhận được phản hồi chung chung như 'kiểm tra lại' sau nhiều lần complaint." | `review.txt` (Dòng 114) | Khách nghỉ dưỡng tại Vinpearl có khiếu nại | CSKH phản hồi chậm và rập khuôn. Khi khách hỏi về quy trình đổi trả phòng hoặc cách dùng voucher, hệ thống không giải đáp dứt điểm. |
| "Thời gian chờ đợi nhằm phản hồi từ tổng đài CSKH lâu, đặc biệt vào ban đêm hoặc giờ cao điểm." | `review.txt` (Dòng 76, 116) | Khách hàng cần hỗ trợ gấp hoặc đặt dịch vụ | Khách hàng phải chờ đợi lâu khi gọi hotline hỏi về các tiện ích resort hoặc cách áp dụng voucher. |
| "Voucher cần đặt trước tối thiểu 10 ngày so với ngày lưu trú. Phải gửi yêu cầu qua hotline/email rồi chờ xác nhận, không thể đặt trực tiếp dễ dàng." | `review.txt` (Dòng 120-123) | Khách mua voucher/combo ưu đãi | Quy trình đặt dịch vụ bằng voucher thủ công và rắc rối, làm nản lòng khách muốn đặt phòng nhanh. |
| "Phụ thu khi nhận phòng/trả phòng sớm hoặc muộn, ở thêm đêm, nâng cấp phòng... không được bao gồm trong voucher, phải trả thêm phí phát sinh rất cao." | `review.txt` (Dòng 111, 125) | Khách sử dụng voucher | Phụ thu phát sinh và chính sách nâng hạng phòng không được giải thích rõ ràng từ đầu, gây bất ngờ khi khách làm thủ tục. |
| "Công viên nước chỉ mở 10h–18h, không phù hợp với gia đình muốn chơi sớm/muộn để tránh nắng. Chờ đợi xe điện nội khu rất lâu." | `review.txt` (Dòng 34, 70) | Khách đang lưu trú tại resort | Thiếu kênh hỏi đáp tức thì và cập nhật trực tiếp về thời gian hoạt động của các tiện ích & dịch vụ di chuyển nội khu. |

## 4. Competitor / analog evidence

| App / mô hình tham khảo | Họ xử lý task này thế nào? | Pattern học được | Có áp dụng trong 1 ngày không? |
|---|---|---|---|
| **Agoda Smart Chatbot (Customer-facing)** | Hỗ trợ khách hàng tự động kiểm tra điều kiện hoàn/hủy/đổi phòng ngay lập tức dựa trên thông tin phòng đặt trước của khách, đưa ra hướng dẫn từng bước. | - Tự động hóa xử lý yêu cầu đổi trả phòng.<br>- Hướng dẫn rõ ràng chính sách hoàn hủy phòng. | Có, có thể xây dựng kịch bản chatbot hướng dẫn quy trình đổi trả phòng trong 1 ngày. |
| **Marriott Bonvoy Mobile Assistant** | Cho phép khách lưu trú trò chuyện trực tiếp để hỏi đáp các tiện ích (giờ mở cửa hồ bơi, spa) và đặt lịch xe điện nội khu, dịch vụ phòng tức thì. | - Hỏi đáp tiện ích resort (Resort FAQ Automation).<br>- Tích hợp đặt lịch dịch vụ nội khu qua hội thoại. | Có, nạp cơ sở dữ liệu tiện ích (FAQ) của Vinpearl vào chatbot để trả lời tự động câu hỏi thông thường. |

## 5. Evidence -> Insight

```text
Evidence nổi bật nhất:
Ảnh chụp màn hình từ folder `cap/` cho thấy giao diện đặt phòng Vinpearl có nhiều điều khoản voucher khắt khe và các trang chính sách đổi trả phòng phức tạp, nhưng quy trình tra cứu lại bắt buộc khách phải tự tìm kiếm hoặc liên hệ tổng đài hỗ trợ thủ công. Đồng thời, review từ khách hàng phản ánh sự ức chế do phải chờ đợi lâu khi gọi hotline hỏi đáp tiện ích hoặc đổi trả phòng.

Insight:
User không chỉ gặp khó khăn ở các chính sách voucher và quy trình booking cứng nhắc (surface problem).
Thật ra họ cần một kênh hỗ trợ trực tuyến tức thì, hướng dẫn chi tiết quy trình đổi trả phòng và giải đáp nhanh các thông tin tiện ích nội khu (deeper need / trust / convenience) mà không cần phải trải qua quy trình gọi hotline hoặc gửi email chờ đợi mòn mỏi.

Opportunity:
AI có thể giúp bằng cách xây dựng một Chatbot Agent thông minh (StayMate AI Concierge) đặt ngay trên web Vinpearl. Chatbot này sẽ trực tiếp trả lời các câu hỏi về điều kiện voucher, hỗ trợ khách hàng các bước đặt lịch, tự động hướng dẫn tạo yêu cầu đổi trả phòng, và giải đáp nhanh mọi thắc mắc về tiện ích resort (như giờ mở cửa công viên nước, Safari, đặt xe điện).
```

## 6. Evidence đổi SPEC như thế nào?

- [x] Đổi user chính.
- [x] Đổi pain statement.
- [x] Đổi build slice.
- [x] Đổi Auto/Aug decision.
- [x] Đổi 4 paths.
- [x] Đổi failure mode.
- [ ] Đổi owner/test plan.

Ghi rõ 1-2 thay đổi quan trọng:

```text
Trước khi có phân tích chi tiết từ folder `cap/` và feedback, nhóm định xây dựng chatbot giải quyết khiếu nại CSKH chung chung và tính phụ phí trả phòng sớm/muộn.

Sau khi có yêu cầu cụ thể, nhóm quyết định loại bỏ phần tính toán phụ phí trả phòng sớm/muộn và tập trung hoàn toàn vào 4 mảng cốt lõi: hỏi đáp voucher, hỗ trợ đặt lịch, hướng dẫn đổi trả phòng, và hỏi đáp tiện ích resort.
Lý do: Giảm thiểu sự phức tạp về việc tích hợp tính toán tài chính nhạy cảm trong ngày đầu, tập trung hoàn thiện trải nghiệm hỏi đáp thông tin và luồng hội thoại đặt/đổi phòng nhanh cho khách.
```