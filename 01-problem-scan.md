# Lab 02 — Worksheet: AI Product Scoping (Vin Smart Future)

# 🔍 Phase 1 — SCAN (Cá nhân, 20 min)

Hãy sử dụng **4 Lenses** dưới đây để quét qua hoạt động vận hành của các công ty thành viên Vingroup. Ghi lại **ít nhất 5 bài toán/bottleneck** thực tế.

### 4 Lenses tìm bài toán AI cho Vingroup:
1. **Lặp lại (Repetitive):** Tác vụ lặp đi lặp lại nhiều lần hằng ngày. (Ví dụ: So khớp hóa đơn sạc điện tại VinFast, route lại chuyến taxi tại Xanh SM).
2. **Tốn thời gian (Time-consuming):** Tác vụ ngốn thời gian xử lý thủ công của nhân viên. (Ví dụ: Soạn thảo phản hồi đánh giá 1-star của cư dân Vinhomes).
3. **AI có thể tốt hơn (AI-upgrade):** Dịch vụ khách hàng hiện tại còn chậm hoặc phản hồi rập khuôn. (Ví dụ: Chatbot CSKH Vinpearl hỗ trợ đặt vé vui chơi).
4. **Pain từ người khác (Stakeholder Pain):** Bottleneck khiến khách hàng hoặc nhân viên thực địa phàn nàn. (Ví dụ: Tài xế Xanh SM phàn nàn về việc hệ thống gợi ý điểm đón khách không chính xác).

> [!TIP]
> **🤖 AI Prompts — Partner brainstorm:**
> Hãy sử dụng prompt sau để brainstorm các bài toán thực tế nếu bạn chưa có ý tưởng:
> *"Tôi là AI Engineer tại Vin Smart Future (Vingroup). Tôi đang tìm kiếm các pain point vận hành cụ thể có thể tối ưu bằng AI cho mảng [Chọn một: VinFast / Xanh SM / Vinhomes / Vinmec]. Hãy gợi ý cho tôi 5 quy trình nghiệp vụ thủ công, tốn nhiều thời gian và gây rò rỉ hiệu suất kèm con số thống kê ước tính về tổn thất."*

### 📝 List bài toán của tôi:
| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 |Xanh SM |Tốn thời gian |Tối ưu điều phối tài xế theo khu vực có nhu cầu cao. AI có thể dự báo nhu cầu theo thời gian, vị trí, thời tiết để gợi ý tài xế di chuyển đến điểm nóng, giúp giảm thời gian chờ và tăng số chuyến hoàn thành. |
| 2 |Xanh SM |Lặp lại |Tự động phân loại khiếu nại khách hàng sau chuyến đi. Các phản ánh như tài xế đến muộn, sai cước,... lặp nhiều hàng ngày và cần nhân viên đọc thủ công. AI có thể tự động tóm tắt, phân loại mức độ nghiêm trọng và chuyển đến đúng bộ phận để xử lý. |
| 3 |Xanh SM|Stakeholder Pain |Giảm thời gian chờ và tỷ lệ hủy chuyến của khách hàng. Khách hàng dễ khó chịu khi phải chờ xe lâu, đặc biệt vào giờ cao điểm hoặc khi trời mưa. AI có thể dự đoán khả năng khách hủy chuyến, ưu tiên ghép xe gần nhất và thông báo thời gian đón chính xác hơn. |
| 4 |Vinmec |Stakeholder Pain |Giảm thời gian chờ khám và hỗ trợ đặt lịch đúng chuyên khoa, AI có thể hỏi qua các triệu chứng ban đầu, gợi ý chuyên khoa và tối ưu lịch đặt của bác sĩ. |
| 5 |Vinmec |AI-upgrade |Tự động tóm tắt hồ sơ bệnh án và kết quả khám. AI có thể hỗ trợ chuyển giọng nói thành văn bản, tóm tắt bệnh án và gợi ý cấu trúc ghi chép, giúp giảm thời gian hành chính cho nhân viên y tế. |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #_1__                                    │
│                                                             │
│ Bài toán (1 câu): Tự động phân loại, tóm tắt và chuyển xử lý
                    khiếu nại khách hàng sau chuyến đi        │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? _Nhân viên chăm sóc khách hàng, khách 
                     hàng khiếu nại, bộ phận vận hành tài xế. │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Khách hàng gửi phản ánh sau chuyến đi
  ──> 2. Nhân viên CSKH đọc nội dung khiếu nại 
  ──> 3. Nhân viên phân loại lỗi: sai cước, tài xế đến muộn, 
    thái độ phục vụ, hủy chuyến, thất lạc đồ...
  ──> 4. Nhân viên chuyển ticket đến bộ phận liên quan
  ──> 5. Bộ phận xử lý phản hồi lại khách hàng                │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2-3 (⏱ 5-10 phút/lượt)│
│ AI có thể nhảy vào hỗ trợ ở bước nào? AI hỗ trợ ở bước 2, 3 
  và 4: tự động đọc nội dung phản ánh, tóm tắt ý chính, phân
  loại mức độ nghiêm trọng, gắn nhãn loại lỗi và chuyển đến 
 đúng bộ phận xử lý.                                          │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian phân 
               loại ticket từ 7 phút xuống dưới 2 phút/ticket.│
│                                                             │
│ Quick Architecture: [ ] No AI  [x] Rule  [ ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #_2__                                    │
│                                                             │
│ Bài toán (1 câu): Giảm thời gian chờ và tỷ lệ hủy chuyến của 
khách hàng Xanh SM bằng dự đoán nguy cơ hủy chuyến và tối ưu ghép tài xế.│ 
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │ 
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │ 
│                                                             │ 
│ Ai đang đau (Actor)? Nhân viên chăm sóc khách hàng, khách 
                     hàng khiếu nại, bộ phận vận hành tài xế. │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Khách hàng đặt xe trên ứng dụng
  ──>2. Hệ thống hiển thị thời gian tài xế đến đón
  ──>3. Nếu thời gian chờ lâu, khách có thể hủy chuyến
  ──>4. Tài xế mất chuyến, hệ thống phải tìm lại khách khác
  ──>5. Đội vận hành chỉ phát hiện vấn đề sau khi tỷ lệ hủy tăng│
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 3 (⏱ 5-12 phút/lượt) │
│ AI có thể nhảy vào hỗ trợ ở bước nào? AI hỗ trợ ở bước 2 và 
  3 bằng cách dự đoán khả năng khách hủy chuyến dựa trên thời 
  gian chờ, khoảng cách tài xế, thời tiết, lịch sử hủy của 
  khu vực và tình trạng giao thông. Hệ thống có thể ưu tiên 
 tài xế gần hơn hoặc gửi thông báo chính xác hơn cho khách.   │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? 
  Giảm tỷ lệ hủy chuyến do chờ lâu từ khoảng 12% xuống dưới 7%.
  Tăng tỷ lệ khách hoàn tất chuyến sau khi đặt xe lên trên 90%.│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #_3__                                    │
│                                                             │
│ Bài toán (1 câu): Tối ưu điều phối tài xế Xanh SM đến các 
  khu vực có nhu cầu cao để giảm thời gian chờ và tăng số 
  chuyến hoàn thành.                                          │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Khách hàng đặt xe, tài xế Xanh SM, 
                       đội vận hành điều phối.                │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Khách hàng đặt xe trên ứng dụng
    ──> 2. Hệ thống tìm tài xế gần nhất
    ──> 3. Tài xế nhận chuyến hoặc từ chối
    ──> 4. Nếu khu vực thiếu xe, khách phải chờ lâu hoặc hủy chuyến
    ──> 5. Đội vận hành xem dữ liệu sau đó mới điều chỉnh phân bổ xe│
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 4 (⏱ 8-15 phút/lượt) │
│ AI có thể nhảy vào hỗ trợ ở bước nào? AI hỗ trợ trước bước 2
  bằng cách dự báo nhu cầu người dùng, Sau đó hệ thống gợi ý 
  tài xế di chuyển đến điểm có nhu cầu cao.                   │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? 
  1. Giảm thời gian chờ trung bình của khách từ khoảng 10 phút 
  xuống dưới 5 phút ở các khung giờ cao điểm.
  2.Tăng tỷ lệ hoàn thành chuyến thêm 10–15%                  │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---
