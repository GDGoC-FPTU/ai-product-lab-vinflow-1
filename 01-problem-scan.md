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
| 1 |Vinhome  |Repetitive | Nhân viên CSKH phải đọc và phân loại hàng trăm yêu cầu cư dân mỗi ngày.|
| 2 |Vinhomes |Time-consuming | Tổng hợp và phản hồi các khiếu nại của cư dân mất nhiều thời gian.|
| 3 | Vinhomes|AI-upgrade | Chatbot hiện tại chỉ trả lời câu hỏi đơn giản, chưa hiểu ngữ cảnh.|
| 4 |Vinmec | Time-consuming| Bác sĩ mất nhiều thời gian tóm tắt hồ sơ bệnh án.|
| 5 | Xanh SM| Stakeholder Pain|Tài xế phàn nàn việc phân bổ cuốc xe chưa tối ưu. |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #__1_                                     │
│                                                             │
│ Bài toán (1 câu): AI tự động phân loại yêu cầu cư dân Vinhomes.  │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ x ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? __Nhân viên CSKH Vinhomes._____________│
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Cư dân gửi yêu cầu  ──> 2. CSKH đọc nội dung ──> 3.Phân loại vấn đề──> 4. Chuyển bộ phận xử lý │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2, 3 ___ (⏱ 3 phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào? | Đọc nội dung và phân loại tự động.│
│                                                             │
│ Đo thành công bằng gì (Metric có số)? |Giảm thời gian phân
 loại từ 3 phút xuống dưới 10 giây.Độ chính xác trên 90%.│
│   VD: "Giảm thời gian soạn phản hồi từ 10 min ──> under 2 min"│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```
```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #__2_                                     │
│                                                             │
│ Bài toán (1 câu): AI tóm tắt nội dung khiếu nại cư dân.  │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ x ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? __Nhân viên CSKH Vinhomes. │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Đọc khiếu nại  ──> 2.Tổng hợp nội dung ──> 3.Viết báo cáo ──> 4. Gửi quản lý │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2, 3 ___ (⏱ 10 phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào? | Tự động tóm tắt và sinh báo cáo..│
│                                                             │
│ Đo thành công bằng gì (Metric có số)? |Giảm thời gian tổng hợp từ 10 phút xuống dưới 1 phút..│
│   VD: "Giảm thời gian soạn phản hồi từ 10 min ──> under 2 min"│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```
```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #__3_                                     │
│                                                             │
│ Bài toán (1 câu): AI chatbot hỗ trợ cư dân 24/7.│
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ x ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Cư dân và CSKH Vinhomes. │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Cư dân đặt câu hỏi  ──> 2.CSKH tiếp nhận ──> 3.Tra cứu thông tin ──> 4. Phản hồi │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước Tra cứu và trả lời (⏱ 5phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào? | Trả lời tự động các câu hỏi phổ biến.│
│                                                             │
│ Đo thành công bằng gì (Metric có số)? |Giảm 50% số ticket cần nhân viên xử lý.│
│   VD: "Giảm thời gian soạn phản hồi từ 10 min ──> under 2 min"│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---
