# Thin SPEC

Thin SPEC không phải PRD đầy đủ. Đây là bản cam kết đủ rõ để sáng Day 06 nhóm build ngay.

## 1. Track, product/app và user

**Track:** Travel & Hospitality  
**Product/app thật:** Vinpearl
**User cụ thể:** Khách hàng (Guests) của Vinpearl truy cập website hoặc ứng dụng để đặt phòng bằng voucher, yêu cầu đổi/trả phòng, hoặc đặt câu hỏi về tiện ích nội khu resort.  
**Nhóm có phải user thật không? Nếu không, khác ở đâu?**  
Nhóm không phải là khách hàng thực tế của Vinpearl. Sự khác biệt lớn nhất là khách hàng thực sự chi tiền thật cho các dịch vụ cao cấp và có mức độ nhạy cảm cao về tài chính cũng như trải nghiệm lưu trú. Khách hàng thật sẽ trò chuyện tự nhiên, sử dụng ngôn ngữ không chuẩn hóa (chát nhanh, viết tắt, gửi ảnh mờ). Nhóm sẽ mô phỏng điều này bằng cách tạo ra các bộ dữ liệu test chứa các mẫu câu chat thực tế của khách hàng lấy từ `review.txt`.

## 2. Evidence summary

| Evidence | Nguồn | User/pain nói lên điều gì? | SPEC phải đổi gì? |
|---|---|---|---|
| Phản hồi chung chung "kiểm tra lại" khi khách complaint nhiều lần. | `review.txt` (Dòng 114) | Khách hàng ức chế vì hệ thống CSKH trả lời tự động vô cảm, trì hoãn và không đưa ra giải pháp giải quyết. | Chatbot phải đề xuất giải pháp xử lý cụ thể, rõ ràng hoặc chuyển giao nhân viên thật ngay lập tức cho các sự cố đặc thù. |
| Quy trình đặt voucher và đổi trả phòng phức tạp (quy định đặt trước 10 ngày, gửi hotline/email và chờ đợi lâu). | `review.txt` (Dòng 111, 120-125), `cap` screenshots | Khách bối rối vì các quy định ẩn và mất nhiều thời gian chờ xác nhận đặt chỗ. | Chatbot tích hợp tính năng tự động tra cứu điều kiện voucher và hướng dẫn quy trình đổi trả phòng theo thời gian thực cho khách. |
| Thời gian chờ phản hồi tổng đài CSKH lâu. | `review.txt` (Dòng 76, 116) | Việc gọi hotline hoặc gửi email chờ duyệt gây tắc nghẽn thông tin. | Chatbot cung cấp kênh tự phục vụ (Self-service) 24/7, phản hồi tức thì và tự động hóa các thao tác tra cứu cơ bản. |

## 3. Pain statement

```text
User [khách hàng mua voucher Vinpearl hoặc đang lưu trú] đang gặp khó ở [quy trình đặt phòng bằng voucher, đổi trả phòng và hỏi đáp thông tin tiện ích nội khu],
vì [phải gửi yêu cầu thủ công qua hotline/email rồi chờ đợi phản hồi lâu, các quy định voucher phức tạp không được hiển thị rõ ràng, và khi hỏi thông tin chỉ nhận được phản hồi chung chung "kiểm tra lại" từ bot thông thường],
dẫn tới [sự ức chế về trải nghiệm dịch vụ, cảm giác quy trình quá rườm rà và mất niềm tin vào thương hiệu cao cấp của Vinpearl].
Bằng chứng chính là [nhiều review phàn nàn về sự chậm trễ của tổng đài, việc phản hồi hời hợt, và sự rắc rối khi áp dụng điều kiện voucher trong review.txt cùng các ảnh giao diện chính sách phòng phức tạp trong folder cap/].
```

## 4. Build slice

```text
Cho [khách hàng Vinpearl] đang [sử dụng website Vinpearl để tra cứu voucher, đặt phòng, hoặc quản lý lịch trình lưu trú],
prototype sẽ dùng AI để [tự động trả lời câu hỏi về điều kiện voucher, hỗ trợ đặt lịch phòng, hướng dẫn đổi trả phòng và giải đáp các thắc mắc về tiện ích resort],
tạo ra [thông tin điều kiện voucher rõ ràng, biểu mẫu xác nhận đặt/đổi phòng nhanh, và phản hồi tức thì về tiện ích nội khu],
và xử lý [failure mode: AI trả lời sai quy định voucher hoặc hướng dẫn sai quy trình đổi trả phòng] bằng [thiết lập cơ chế Conditional Automation: tự động hóa hoàn toàn các câu hỏi voucher/tiện ích chuẩn; lập tức chuyển cuộc trò chuyện sang nhân viên CSKH thật (human agent) kèm tóm tắt ngữ cảnh khi gặp thông tin mơ hồ hoặc khiếu nại phức tạp].
```

## 5. Auto/Aug decision

Chọn một:

- [ ] **Augmentation:** AI gợi ý/draft/phân loại, user quyết cuối.
- [x] **Conditional automation:** AI tự làm trong case hẹp; case mơ hồ/rủi ro chuyển người.
- [ ] **Automation:** AI tự quyết và tự hành động.

**Lý do chọn:** Chatbot tương tác trực tiếp với khách hàng cần phản hồi ngay lập tức để giải quyết vấn đề nghẽn cổ chai (Happy Path tự động đặt phòng, hướng dẫn đổi phòng, và hỏi đáp tiện ích). Tuy nhiên, với các ca rủi ro cao (yêu cầu hoàn hủy voucher đặc biệt, lỗi đặt lịch sát ngày, lỗi thanh toán), hệ thống cần chuyển ngay sang nhân viên CSKH thật xử lý để tránh rủi ro tài chính hoặc khủng hoảng truyền thông.  
**Human role:** rescuer (nhân viên CSKH thật sẽ tiếp quản ngay cuộc trò chuyện khi hệ thống chuyển tiếp hoặc khách hàng yêu cầu).

## 6. Four paths

| Path | Prototype phải thể hiện gì? |
|---|---|
| Happy | Khách nhắn: "Tôi muốn đặt phòng từ 15/6-17/6 dùng voucher VNP100". AI kiểm tra thấy voucher hợp lệ (>10 ngày đặt trước), xác nhận điều kiện, và gửi link xác nhận đặt chỗ. Khách bấm "Xác nhận" -> Đặt phòng hoàn tất trong 1 phút. |
| Low-confidence | Khách nhắn mập mờ: "Tôi muốn đổi lịch phòng đã đặt sang tuần sau". AI nhận diện thiếu thông tin (mã đặt phòng cũ, ngày đi mới mong muốn) -> Lịch sự phản hồi: "Dạ, anh/chị vui lòng nhập mã đặt phòng (ví dụ VP-XXXX) và ngày nhận/trả phòng mới cụ thể để em kiểm tra khả năng đổi phòng và hỗ trợ đặt lịch ạ." |
| Failure | AI hướng dẫn sai quy trình hoàn hủy voucher hoặc nhầm lẫn chính sách đổi phòng (ví dụ hứa hẹn đổi phòng miễn phí cho loại voucher không hỗ trợ đổi phòng). |
| Correction | Khách hàng nhắn phản đối: "Tôi muốn gặp nhân viên thật" hoặc "Bot hướng dẫn sai rồi". Hệ thống lập tức kích hoạt nút "Chuyển tiếp cho nhân viên hỗ trợ" (Human Handoff) và chuyển toàn bộ lịch sử trò chuyện đến màn hình làm việc của nhân viên CSKH thật. |

## 7. Failure mode nguy hiểm nhất

```text
Nếu user [yêu cầu hủy đặt phòng sát giờ và đòi hoàn tiền voucher do lý do bất khả kháng (thiên tai/chuyến bay hủy)],
AI có thể [tự ý phê duyệt hoàn tiền voucher trái quy định cứng của Vinpearl],
hậu quả là [gây thất thoát doanh thu trực tiếp hoặc gây ra tranh chấp pháp lý nếu khách hàng vin vào lời hứa của bot].
Prototype sẽ xử lý bằng [nhận diện từ khóa "hủy phòng", "hoàn tiền", "thiên tai" và tự động khóa tính năng tự quyết định, hiện thông báo chuyển tiếp và đẩy ngay cuộc hội thoại cho nhân viên thật có thẩm quyền duyệt ngoại lệ].
Owner kiểm thử path này là [Thành viên phụ trách Test].
```

## 8. Owner plan cho sáng Day 06

| Thành viên | Việc phụ trách | Bằng chứng cần có trong repo |
|---|---|---|
| Lead/Research Owner | Research / evidence | File `evidence-pack.md` hoàn thiện; dữ liệu mẫu về các câu hỏi voucher & khiếu nại của khách. |
| Product Owner | SPEC | File `thin-spec.md` hoàn thiện; sơ đồ kịch bản hội thoại (Flowchart) của Chatbot và giao diện chuyển tiếp nhân viên thật. |
| Tech Lead / Developer | Prototype | Mã nguồn chatbot AI (HTML/JS + LLM API) chạy được tính năng: Đọc tin nhắn -> Phân tích voucher -> Phản hồi hỗ trợ đặt lịch/đổi phòng và chuyển tiếp nhân viên thật. |
| QA / Test Owner | Test / failure path | Kịch bản kiểm thử (Test cases) chứng minh bot xử lý đúng 4 paths và bắt được từ khóa Red Flag để chuyển tiếp thành công. |
| Demo Owner | Demo script / repo | Video quay màn hình demo hoạt động của chatbot; slide thuyết trình mô tả giải pháp giải quyết pain points. |