# 01 — Individual Problem Scan (Báo cáo cá nhân)

> **Khóa học:** Day 02 — AI Product Labs  
> **Mục tiêu:** Quét rộng (scan) 10 bài toán thực tế, chọn lựa và xây dựng Top 3 Problem Cards, phác thảo luồng vận hành trước/sau để đánh giá khả năng áp dụng AI.
> **Tên nhóm:** vinagang

---

## 🔍 1. Quét rộng tìm kiếm cơ hội (Scan 12 Problems)

Dưới đây là danh sách 12 bài toán thực tế được đúc kết từ trải nghiệm thực tế của một sinh viên mới trong những ngày đầu làm quen với môi trường học tập số và các công cụ AI:

| # | Thấu kính (Lens) | Bài toán quan sát được | Actor chịu ảnh hưởng | Dấu hiệu thực tế & Đo lường |
| :---: | :--- | :--- | :--- | :--- |
| **1** | Lặp lại / Công cụ | **Chưa thành thạo Git/GitHub:** Gặp khó khăn với các lệnh cơ bản (clone, commit, push, resolve conflicts) khiến tiến trình nhận và nộp bài lab bị chậm trễ. | Sinh viên mới | Loay hoay mất 15-25 phút mỗi lần thao tác trên Terminal, liên tục phải nhờ bạn bè hoặc Trợ giảng (TA) gỡ lỗi. |
| **2** | Lặp lại / Công cụ | **Xung đột môi trường ảo Python (`.venv` & Thư viện):** Thao tác tạo môi trường ảo, cài đặt SDK (`pip install`) và đồng bộ phiên bản thư viện hay bị lỗi do hệ điều hành. | Sinh viên mới bắt đầu code Python/AI | Tốn từ 30–60 phút loay hoay cài đi cài lại thư viện trước mỗi buổi lab, dễ gặp lỗi khó hiểu như `ModuleNotFoundError`. |
| **3** | Tìm kiếm thông tin | **Tài liệu học tập phân tán:** Slide bài giảng, code mẫu, hướng dẫn làm lab và link nộp bài nằm rải rác trên nhiều nền tảng khác nhau. | Sinh viên mới | Tốn 10-20 phút mỗi ngày chỉ để đi tìm và tập hợp đầy đủ tài liệu chuẩn bị làm bài lab. |
| **4** | Lặp lại / Công cụ | **Trôi thảo luận trên Discord:** Các cuộc hội thoại trao đổi nhanh trôi đi quá nhanh, không có hệ thống lưu trữ tri thức lớp học tập trung. | Sinh viên mới | Mất hàng chục phút cuộn màn hình để tìm lại câu trả lời cho lỗi hệ thống mà các sinh viên trước đó đã hỏi và xử lý xong. |
| **5** | Lặp lại / Công cụ | **Quá tải hòm thư Outlook:** Khó khăn khi lọc và quản lý email thông báo bài tập, hạn nộp tự động từ hệ thống LMS/Classroom. | Sinh viên mới | Hòm thư ngập tràn các email tự động thông báo hoạt động, mất nhiều thời gian để xác định email thực sự quan trọng. |
| **6** | Lặp lại / Công cụ | **V-App và Cổng thông tin nội bộ lỗi/khó dùng:** Giao diện tra cứu điểm số, lịch trình và thủ tục hành chính phức tạp, có lúc bị lỗi truy cập. | Sinh viên mới | Hoang mang không rõ thông tin chính thức nằm ở cổng thông tin nào, dễ gây nhầm lẫn quy trình hành chính. |
| **7** | Tốn thời gian / Kiến thức | **Thuật ngữ AI/Product mới mẻ:** Khối lượng từ khóa chuyên ngành lớn (Workflow, Agent, Bottleneck, ROI, Boundary, HITL) khó nhớ và khó hiểu sâu. | Sinh viên mới học AI | Bị ngắt mạch tư duy giữa buổi học lý thuyết do phải vừa nghe giảng vừa tự tra cứu nghĩa thuật ngữ. |
| **8** | Tốn thời gian / Kiến thức | **Đọc hiểu Slides bài giảng chuyên ngành dài và khó:** Các file slides bài giảng Tiếng Anh dài chứa nhiều thuật ngữ kỹ thuật chuyên sâu gây quá tải khi tự học trước giờ lên lớp. | Sinh viên mới học AI/Product | Mất từ 1–2 tiếng mỗi tối chỉ để dịch và đọc lướt qua slide bài giảng mà vẫn khó chắt lọc được ý chính. |
| **9** | Lặp lại / Tốn thời gian | **Không kịp ghi chép kiến thức cốt lõi:** Nhịp độ bài giảng nhanh, sinh viên vừa phải tập trung nghe hiểu vừa phải ghi chú lại các lưu ý dẫn đến việc ghi chép bị đứt quãng. | Sinh viên mới | Phải ghi âm lại buổi học và mất thêm 30–40 phút buổi tối để nghe lại và hoàn thiện ghi chú cá nhân. |
| **10** | Làm việc nhóm | **Áp lực làm việc nhóm cường độ cao:** Chưa quen nhịp độ cộng tác nhanh, kỹ năng phản biện (challenge) và thuyết trình (pitching) ý tưởng còn lúng túng. | Sinh viên mới | Các buổi họp nhóm bị kéo dài lan man, tranh luận không chốt được giải pháp tối ưu cuối cùng dưới áp lực thời gian. |
| **11** | Pain từ stakeholder / Tìm kiếm thông tin | **Khó khăn khi ghép nhóm làm Project/Lab:** Chưa quen biết rộng rãi các thành viên trong lớp mới, khó tìm kiếm người có cùng lịch trình hoạt động phù hợp. | Sinh viên mới | Mất nhiều ngày nhắn tin rời rạc trên các kênh chung, có trường hợp sát giờ làm bài nhóm vẫn chưa ghép được nhóm hiệu quả. |
| **12** | Môi trường mới | **Bỡ ngỡ với không gian học tập mới:** Chưa quen sơ đồ phòng học, đường đi và các tiện ích sinh hoạt quanh giảng đường mới. | Sinh viên mới | Đi nhầm phòng học trong tuần đầu tiên, mất thời gian định vị thủ công bằng bản đồ cá nhân. |


### 💡 Nhận xét tổng quan sau khi Scan:
Trong 12 vấn đề trên, nhóm bài toán liên quan đến **học tập số, công cụ cộng tác, và thuật ngữ AI chuyên ngành** là phù hợp nhất để đưa vào scoping. Các quy trình này có các bước thao tác rõ ràng, dễ đo lường bằng thời gian thực tế và rất thích hợp để so sánh giữa các phương án xử lý (Rule-based vs Workflow vs Agent).

---

## 🎯 2. Đánh giá lựa chọn Top 3 Problems

| Hạng | Bài toán tiềm năng | Lý do lựa chọn tiêu biểu | Điểm cần làm rõ thêm |
| :---: | :--- | :--- | :--- |
| **Rank 1** | Sinh viên mới chưa thành thạo các công cụ học tập số (GitHub, Teams, Discord, Outlook, V-App) | Quy trình thao tác cực kỳ rõ ràng, lặp lại liên tục, ảnh hưởng trực tiếp đến hiệu suất làm bài lab và có thể đo lường chính xác bằng thời gian hoàn thành tác vụ. | Cần khảo sát xem công cụ nào thực sự gây ra nút thắt cổ chai lớn nhất cho các bạn. |
| **Rank 2** | Sinh viên gặp khó khăn với lượng thuật ngữ AI mới và khó hiểu | Ảnh hưởng trực tiếp đến khả năng tiếp thu bài giảng lý thuyết và hiệu quả thảo luận nhóm trong các buổi lab tiếp theo. | Metric đánh giá "mức độ hiểu bài" khó định lượng bằng số hơn là thời gian. |
| **Rank 3** | Khó khăn trong việc theo dõi, tổng hợp thông báo và deadline phân tán trên nhiều kênh | Tần suất lặp lại hàng ngày, dễ đo lường bằng số lần kiểm tra thông báo thủ công và số lượng deadline bị bỏ lỡ. | Khả năng kết nối, gom dữ liệu (API) từ nhiều nền tảng đóng như Teams hay Outlook về một mối. |

---

# 🃏 3. Chi tiết 3 Thẻ bài toán (Quick Problem Cards)

---

## 🎴 QUICK PROBLEM CARD #1: Onboarding công cụ học tập số

```text
┌───────────────────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1: ONBOARDING CÔNG CỤ HỌC TẬP SỐ                      │
│                                                                           │
│ Bài toán: Sinh viên mới mất quá nhiều thời gian làm quen và thực hiện các │
│ thao tác cơ bản trên GitHub, Teams, Outlook, Discord và V-App.            │
│ Công ty thành viên/Đơn vị: [x] Đào tạo / Học viên mới                     │
│                                                                           │
│ Ai đang đau? Sinh viên mới (hoang mang, chậm tiến độ),                     │
│             Trợ giảng TA (quá tải vì trả lời các câu hỏi lặp lại).        │
│                                                                           │
│ Workflow thủ công hiện tại (8 bước):                                      │
│   1. Nhận link bài lab ──> 2. Mở Teams/Discord tìm thông tin liên quan     │
│   ──> 3. Mở GitHub (chưa quen clone) ──> 4. Google/YouTube tìm hướng dẫn  │
│   ──> 5. Thao tác thử trên VS Code ──> 6. Gặp lỗi Terminal/Git            │
│   ──> 7. Hỏi bạn bè/Trợ giảng ──> 8. Chờ đợi, sửa lại và nộp bài.         │
│                                                                           │
│ Bước nào tốn nhất? Bước 3 đến 6 (⏱ Trung bình 20 - 30 phút/lab)           │
│ AI có thể tham gia hỗ trợ ở bước nào? Bước 4, 6 & 7                       │
│ (AI tự động bắt lỗi Terminal, hướng dẫn clone/push Git theo ngữ cảnh).    │
│                                                                           │
│ Đo thành công bằng gì (Metric có số)?                                     │
│ - Giảm thời gian thực hiện thao tác Git/công cụ từ 35 phút ──> dưới 12 phút│
│ - Giảm số lần phải hỏi trợ giảng từ 3 lần ──> 0 hoặc 1 lần mỗi buổi.      │
│                                                                           │
│ Quick Architecture: [x] LLM Feature (Tích hợp AI hướng dẫn theo ngữ cảnh) │
└───────────────────────────────────────────────────────────────────────────┘
```

### 🔄 Quy trình vận hành của Card #1:

```text
Quy trình hiện tại (Thủ công & Tắc nghẽn):
[Nhận bài lab] ──> [Mở Git (lúng túng)] ──> [Tra Google/YouTube 🔴] ──> [Gặp lỗi Git 🔴] ──> [Hỏi TA & Chờ 🔴] ──> [Nộp bài]

Quy trình tương lai (Có AI hỗ trợ):
[Nhận bài lab] ──> [Gặp lỗi Git/Terminal] ──> [🔵 AI hướng dẫn sửa theo lỗi thực tế] ──> [Tự sửa thành công] ──> [Nộp bài]
                                                  │
                                                  └──> (Nếu vẫn lỗi) ──> [🟢 TA hỗ trợ nhanh]
```

---

## 🎴 QUICK PROBLEM CARD #2: Keyword AI mới lạ, khó hiểu

```text
┌───────────────────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2: KEYWORD AI MỚI LẠ, KHÓ HIỂU                       │
│                                                                           │
│ Bài toán: Sinh viên mới gặp nhiều thuật ngữ AI/Product mới liên tục,      │
│ gây gián đoạn mạch nghe giảng và khó hiểu sâu nội dung bài lab.          │
│ Công ty thành viên/Đơn vị: [x] Đào tạo / Lớp học AI                       │
│                                                                           │
│ Ai đang đau? Sinh viên mới học AI/Product Thinking.                       │
│                                                                           │
│ Workflow thủ công hiện tại (7 bước):                                      │
│   1. Nghe giảng/đọc slide ──> 2. Gặp thuật ngữ tiếng Anh mới              │
│   ──> 3. Bị khựng lại vì chưa hiểu nghĩa ──> 4. Tra cứu Google/Từ điển     │
│   ──> 5. Bị mất mạch giảng bài của giảng viên ──> 6. Hỏi lại bạn bên cạnh │
│   ──> 7. Ghi chú nhanh khái niệm thu thập được.                           │
│                                                                           │
│ Bước nào tốn nhất? Bước 3, 4 & 5 (⏱ Làm mất 5 - 10 phút tập trung nghe)   │
│ AI có thể tham gia hỗ trợ ở bước nào? Bước 4 & 7                          │
│ (AI đóng vai trò từ điển thông minh, giải thích ngắn gọn kèm ví dụ lab).  │
│                                                                           │
│ Đo thành công bằng gì (Metric có số)?                                     │
│ - Giảm số lượng từ khóa chưa hiểu sau buổi học từ 15-20 từ ──> còn ≤ 5 từ. │
│ - Đảm bảo sinh viên nắm vững sự khác biệt giữa Rule, Workflow và Agent.   │
│                                                                           │
│ Quick Architecture: [x] LLM Feature (Trợ lý từ điển thông minh)           │
└───────────────────────────────────────────────────────────────────────────┘
```

### 🔄 Quy trình vận hành của Card #2:

```text
Quy trình hiện tại (Thủ công & Tắc nghẽn):
[Gặp từ khóa mới] ──> [Tra Google/Từ điển dài dòng 🔴] ──> [Mất tập trung mạch giảng của thầy 🔴] ──> [Ghi chép sót]

Quy trình tương lai (Có AI hỗ trợ):
[Gặp từ khóa mới] ──> [🔵 AI giải thích ngắn gọn + ví dụ trực quan] ──> [Nắm bài ngay lập tức] ──> [Tiếp tục nghe giảng]
```

---

## 🎴 QUICK PROBLEM CARD #3: Thông báo và deadline phân tán

```text
┌───────────────────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3: THÔNG BÁO VÀ DEADLINE PHÂN TÁN                     │
│                                                                           │
│ Bài toán: Sinh viên dễ bỏ sót deadline và thông báo quan trọng do thông    │
│ tin bị rải rác trên nhiều nền tảng: Outlook, Teams, Discord, GitHub.      │
│ Công ty thành viên/Đơn vị: [x] Đào tạo / Quản lý lớp học                  │
│                                                                           │
│ Ai đang đau? Sinh viên mới (bị lỡ deadline), Trưởng nhóm (quản lý mệt mỏi).│
│                                                                           │
│ Workflow thủ công hiện tại (7 bước):                                      │
│   1. Mở Outlook kiểm tra email ──> 2. Mở Teams xem thông báo chính thức   │
│   ──> 3. Mở Discord check tin nhắn thảo luận ──> 4. Mở GitHub xem lab mới │
│   ──> 5. Lọc và tổng hợp thủ công ──> 6. Tự ghi chú deadline ra giấy/Lịch │
│   ──> 7. Bắt đầu làm bài hoặc nhắc nhở các thành viên trong nhóm.         │
│                                                                           │
│ Bước nào tốn nhất? Bước 1 đến 6 (⏱ Tốn 15 - 25 phút kiểm tra mỗi ngày)    │
│ AI có thể tham gia hỗ trợ ở bước nào? Bước 5 & 6                          │
│ (AI tự động quét, tóm tắt và phân loại độ ưu tiên của các thông báo).     │
│                                                                           │
│ Đo thành công bằng gì (Metric có số)?                                     │
│ - Giảm thời gian tổng hợp thông báo từ 25 phút/ngày ──> dưới 7 phút/ngày. │
│ - Đưa tỉ lệ bỏ lỡ deadline/thông báo khẩn cấp về 0%.                      │
│                                                                           │
│ Quick Architecture: [x] LLM Feature (Gom và tóm tắt thông báo thông minh) │
└───────────────────────────────────────────────────────────────────────────┘
```

### 🔄 Quy trình vận hành của Card #3:

```text
Quy trình hiện tại (Thủ công & Tắc nghẽn):
[Mở email] ──> [Mở Teams] ──> [Mở Discord] ──> [Mở GitHub] ──> [Tổng hợp & chép deadline tay 🔴] ──> [Dễ bỏ sót 🔴]

Quy trình tương lai (Có AI hỗ trợ):
[🔵 AI quét & tổng hợp tự động các kênh] ──> [Draft danh sách tóm tắt theo thứ tự ưu tiên] ──> [🟢 Sinh viên duyệt & theo dõi]
```

---

## 📊 4. So sánh & Đánh giá Top 3 Problems

Để đưa ra quyết định lựa chọn bài toán tối ưu nhất mang đi Pitching cùng cả nhóm, dưới đây là bảng đối chiếu chi tiết:

| Tiêu chí so sánh | Card #1: Onboarding công cụ số | Card #2: Thuật ngữ AI mới | Card #3: Deadline phân tán |
| :--- | :--- | :--- | :--- |
| **Actor chính** | Sinh viên mới chưa thạo Git/công cụ | Sinh viên mới học AI | Sinh viên mới học tập theo nhóm |
| **Nút thắt cổ chai** | Không biết thao tác Git/Terminal, mất thời gian tự mò lỗi | Khựng lại khi gặp từ khóa, mất mạch nghe giảng bài | Phải mở nhiều app để tổng hợp thủ công, dễ bỏ sót |
| **Metric thành công** | **Thời gian thao tác:** 35 min ──> 12 min | **Số từ chưa hiểu:** 15 từ ──> ≤ 5 từ | **Thời gian tổng hợp:** 25 min ──> 7 min |
| **Kiến trúc AI đề xuất** | **LLM Feature** (hướng dẫn theo ngữ cảnh) | **LLM Feature** (giải thích ngắn + ví dụ) | **LLM Feature** (tổng hợp & phân loại) |
| **Lý do chưa chọn làm #1** | **(ĐƯỢC CHỌN LÀM #1)** | Định lượng "mức độ hiểu bài" khó đo lường chính xác bằng số hơn. | Cần tích hợp API sâu vào nhiều app bên thứ ba có bảo mật cao. |

---

## 🏁 5. Tự đánh giá phần cá nhân

### 🎯 Điểm mạnh của bản Scan cá nhân này:
*   Có quy trình scan rộng rõ ràng (12 bài toán thực tế) trước khi chắt lọc ra Top 3.
*   Ý tưởng xuất phát trực tiếp từ các "điểm đau" (pain points) có thật mà bất kỳ sinh viên mới nào cũng gặp phải trong tuần đầu học tập.
*   Cấu trúc Problem Card hoàn thiện, định lượng hóa rõ ràng bằng các con số (Success Metrics).
*   Không lạm quyền công nghệ: Đưa ra các phương án thay thế phi AI (Non-AI alternatives) để đối chiếu trực quan và lựa chọn giải pháp AI gọn nhẹ nhất (LLM Feature), tránh bẫy "Multi-Agent" tự trị phức tạp.

### 📢 Ý tưởng muốn mang đi Pitching với nhóm nhất:
**Problem Card #1 — Trợ lý hướng dẫn và gỡ lỗi công cụ học tập số (Onboarding Git/Terminal).**

*   **Vì sao?** Đây là bài toán cấp thiết, lặp lại hàng ngày, ảnh hưởng trực tiếp đến kết quả nộp bài của sinh viên và rất dễ phát triển thành một bản mẫu kỹ thuật (prompt prototype) hoạt động hiệu quả.
*   **Câu hỏi thảo luận dành cho nhóm:**
    *   Các bạn trong nhóm có gặp khó khăn với Git/Terminal trong tuần đầu giống mình không?
    *   Liệu một cẩm nang PDF/Video hướng dẫn tĩnh có đủ giải quyết vấn đề, hay bắt buộc phải cần đến sự trợ giúp tương tác trực tiếp của AI?
    *   Làm thế nào để huấn luyện AI đưa ra hướng dẫn chuẩn xác với từng hệ điều hành (Windows/macOS) và từng phiên bản phần mềm cụ thể?
