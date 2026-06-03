# Toolkit — Từ Evidence Đến Build Slice

Dùng sau khi nhóm đã có evidence. Mục tiêu là chốt một build slice đủ nhỏ cho Day 06.

## 1. Gom evidence thành cụm

Gom theo **workflow/pain**, không gom theo tên feature.

- **Cụm 1: "Quy trình đặt lịch bằng voucher thủ công & rườm rà"**  
  *Evidence:* Voucher đặt phòng bắt buộc phải đặt trước tối thiểu 10 ngày, gửi thông tin qua hotline/email và đợi nhân viên CSKH xác nhận thủ công, giao diện web không cho phép khách tự áp mã đặt phòng trực tiếp một cách nhanh chóng.
- **Cụm 2: "Khách bối rối và gặp rắc rối khi muốn đổi/trả phòng"**  
  *Evidence:* Chính sách voucher quy định "không hoàn, không hủy", đổi tên mất phí 300k, không thể thay đổi lịch trình khi gặp sự cố thiên tai/chuyến bay đổi dẫn đến khiếu nại chưa được xử lý thỏa đáng.
- **Cụm 3: "Thiếu thông tin và khó tiếp cận tiện ích nội khu resort"**  
  *Evidence:* Thông tin giờ mở cửa công viên nước (10h-18h), Safari, nhà hàng, xe điện nằm rải rác ở các trang con khác nhau khiến khách khó tìm kiếm, hoặc xe điện đón muộn vào giờ cao điểm mà khách không biết tiến độ xe.
- **Cụm 4: "CSKH tổng đài phản hồi quá chậm và mang tính rập khuôn"**  
  *Evidence:* Khách hàng nhận phản hồi trì hoãn "đang kiểm tra lại" sau nhiều lần khiếu nại, thời gian chờ phản hồi từ tổng đài CSKH rất lâu, đặc biệt là ban đêm.

## 2. Viết insight

Form:

```text
User [segment] không chỉ cần [surface need].
Họ thật ra cần [deeper need],
vì [evidence pattern].
```

Ví dụ thực tế của nhóm:

```text
Khách hàng mua voucher nghỉ dưỡng Vinpearl không chỉ cần một ô nhập mã voucher thông thường trên trang thanh toán.
Họ thật ra cần một quy trình tự phục vụ (self-service) tức thì để đối chiếu điều kiện voucher, hỗ trợ đặt lịch phòng nhanh, tự động hướng dẫn quy trình đổi trả phòng và trả lời thắc mắc tiện ích nội khu 24/7,
vì nhiều review và quan sát thực tế cho thấy họ cực kỳ ức chế khi phải gọi hotline/gửi email chờ đợi lâu chỉ để hỏi các thông tin điều khoản cơ bản hoặc bị động khi thay đổi lịch trình lưu trú.
```

## 3. Viết opportunity

Form:

```text
Cơ hội là dùng AI để [augment/automate hành động hẹp],
giúp user [kết quả],
trong khi vẫn kiểm soát [failure/risk].
```

Ví dụ thực tế của nhóm:

```text
Cơ hội là dùng AI để tự động hóa hoạt động trả lời câu hỏi voucher, hỗ trợ đặt lịch, hướng dẫn đổi trả phòng và giải đáp thắc mắc tiện ích nội khu resort (automate hành động hẹp),
giúp user nhận được thông tin hướng dẫn và phản hồi ngay lập tức 24/7 trên giao diện chat (kết quả),
trong khi vẫn kiểm soát rủi ro AI phát ngôn sai chính sách hoặc hứa hẹn hoàn hủy tiền sai quy định bằng cơ chế tự động chuyển tiếp cuộc trò chuyện sang nhân viên CSKH thật xử lý khi gặp ca phức tạp/rủi ro cao (failure/risk).
```

## 4. Chọn build slice

Build slice tốt phải qua 5 câu hỏi:

| Câu hỏi | Đạt khi | Đánh giá của nhóm StayMate AI Concierge |
|---|---|---|
| User cụ thể chưa? | Nói được ai dùng, trong bối cảnh nào. | Đạt: Khách hàng sử dụng voucher Vinpearl đang truy cập website để đặt phòng hoặc cần hỗ trợ thông tin tiện ích resort. |
| Task đủ hẹp chưa? | Demo được trong 3-5 phút. | Đạt: Khách hỏi cách dùng voucher, hỗ trợ lên lịch đặt, hỏi chính sách đổi trả phòng và giờ mở cửa công viên nước/Safari. |
| AI decision rõ chưa? | AI gợi ý/tự làm một việc cụ thể. | Đạt: AI tự hiểu ngôn ngữ tự nhiên để phân loại ý định (intent) của khách, tra cứu chính sách/tiện ích nội khu để trả lời trực tiếp cho khách. |
| Failure path rõ chưa? | Có một case AI không chắc hoặc sai để test. | Đạt: AI hướng dẫn sai quy định hoàn hủy voucher hoặc gặp các khiếu nại khẩn cấp nguy hiểm (ngộ độc thực phẩm) cần kích hoạt chuyển tiếp người thật (Red Flag). |
| Có evidence không? | Có bằng chứng từ self-use/review/user/competitor. | Đạt: Rất nhiều bằng chứng thực tế trong `review.txt` và ảnh chụp giao diện lưu trú trong folder `cap/`. |

## 5. Quyết định: giữ, giảm scope, hay đổi hướng?

| Tình huống | Quyết định | Hành động cụ thể của nhóm |
|---|---|---|
| Evidence yếu, user mơ hồ | Dừng build sâu; quay lại research 20 phút. | Không áp dụng (Evidence từ review và cap rất mạnh). |
| Ý tưởng quá rộng | Giữ domain, cắt xuống một flow. | **Áp dụng:** Loại bỏ tính năng tính toán số tiền phụ phí cụ thể (nhận phòng sớm, trả phòng muộn) để giảm độ phức tạp về tài chính và tích hợp dữ liệu giá phòng, tập trung tối đa vào luồng hỏi đáp voucher, đặt lịch, đổi phòng và Q&A tiện ích resort. |
| AI không cần thiết | Dùng rule/manual prototype; ghi rõ vì sao không dùng AI sâu. | Không áp dụng (AI cần thiết để chatbot hiểu ngôn ngữ tự nhiên của khách khi hỏi đáp các câu hỏi FAQ đa dạng). |
| Rủi ro cao | Chọn augmentation hoặc conditional automation. | **Áp dụng:** Chọn **Conditional Automation** - chatbot tự động trả lời các câu hỏi tiêu chuẩn về voucher/tiện ích và tự động chuyển giao cho nhân viên thật (human agent) xử lý đối với các yêu cầu đổi trả phòng đặc thù hoặc khiếu nại lớn. |
| Không demo được trong 1 ngày | Đưa phần lớn vào backlog, giữ một path nhỏ. | **Áp dụng:** Chỉ giả lập luồng chatbot hoạt động trực tuyến trên giao diện web (dùng mock-data API) thay vì tích hợp trực tiếp vào hệ thống Core Booking thực tế của Vinpearl. |

## 6. Câu chốt cuối

Điền câu này trước khi rời lớp:

```text
Dựa trên [các minh chứng về sự chậm trễ của tổng đài CSKH, quy trình voucher khắt khe và thông tin tiện ích resort bị dàn trải],
nhóm sẽ build [StayMate AI Concierge Chatbot],
cho [khách hàng sử dụng voucher Vinpearl],
để giải quyết [pain về việc chờ đợi hotline, bối rối về điều kiện voucher, đổi trả phòng và thiếu thông tin tiện ích nội khu],
bằng cách AI [tự động trả lời câu hỏi voucher, hỗ trợ đặt lịch/đổi phòng và giải đáp nhanh các FAQ tiện ích 24/7 (Conditional Automation)],
và sẽ test failure path [AI hướng dẫn sai quy định hoàn hủy voucher hoặc gặp khiếu nại ngộ độc thực phẩm (Red Flag) -> tự động chuyển tiếp cuộc gọi sang nhân viên thật].
```

## 7. Backlog

Những thứ **không build trong Day 06**:

- Tích hợp API thật vào hệ thống Core Booking & CRM của Vinpearl (chỉ làm giả lập API bằng Mock Data).
- Tính năng tính toán số tiền phụ phí cụ thể cho việc nhận phòng sớm/muộn và phụ thu giường phụ (đã loại bỏ để giảm scope).
- Tích hợp cổng thanh toán trực tuyến để khách mua thêm dịch vụ ngay trên giao diện chat.
- Hệ thống gửi SMS/Zalo thông báo tự động sau khi hoàn tất yêu cầu đặt/đổi phòng thành công.