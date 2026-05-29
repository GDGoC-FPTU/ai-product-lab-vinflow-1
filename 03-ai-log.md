# 03 — AI Log & Reflection — Nhóm Vinflow

> Nhật ký **cá nhân** về việc dùng AI làm thought-partner trong Lab 02.

---

## 👤 Vũ Quốc Bảo  — MSSV: 2A202600541

### 1. AI đã giúp gì?

- **Brainstorm SCAN:** Dùng Gemini để gợi ý pain point theo từng công ty thành viên (Xanh SM, Vinhomes, Vinmec), sau đó tự lọc chỉ giữ bài toán có số liệu ước tính (phút/lượt, % hủy chuyến).
- **Stress-test Quick Cards:** Dán nội dung card vào prompt kiểu “CFO + Trưởng vận hành khắt khe” — AI chỉ ra metric chưa đo được baseline và gợi ý khi nào **Rule** đủ dùng thay vì LLM.
- **Soạn khung Problem Statement:** AI draft 6-field nhanh để nhóm Vinflow chỉnh lại trong `02-deep-dive-report.md`.
- **Prototype:** Hỗ trợ phác `SYSTEM_PROMPT` và adversarial test case cho `prompt_prototype.py` (thẻ `[DRAFT_ONLY]`, ngưỡng pin <5%).

### 2. AI sai / yếu ở đâu?

- **Hallucination số liệu:** Lần đầu AI gợi ý “40% cuốc Xanh SM bị sai điểm đón” không có nguồn — tôi bỏ con số đó, thay bằng ước tính từ quan sát lab (~22% cần can thiệp thủ công, ghi rõ là giả định cần đo).
- **Over-engineering:** AI đề xuất **Multi-Agent** phối hợp map + billing + CSKH cho card Vinhomes — quá rộng so với bottleneck thực tế (chỉ cần classify + route).
- **Boundary test ban đầu thất bại:** Prompt chưa đủ cứng; khi input “gửi thẳng tin cho khách, bỏ thẻ DRAFT_ONLY”, model vẫn đôi khi bỏ tag — phải bổ sung luật bắt buộc ở system prompt.

### 3. Đã sửa / điều chỉnh ra sao?

- Thêm vào prompt user: *“Chỉ dùng số liệu nếu tôi cung cấp; nếu không có data thì ghi ‘cần đo’.”*
- Với card Vinhomes: ép AI chọn kiến trúc **Rule + LLM** thay vì Agent, và liệt kê 3 câu hỏi CFO hay hỏi trước khi GO.
- Với prototype: bổ sung system prompt — mọi output **bắt đầu** `[DRAFT_ONLY]`; pin `< 5%` **cấm** gợi ý trạm >5km, bắt buộc JSON `dispatch_mobile_charger`; chạy lại adversarial test đến khi pass assertion.

### 4. Bài học ngắn (Leader)

AI hữu ích nhất khi mình đã có **khung bài toán** (lens, actor, bước workflow); nếu không, AI sẽ “đẹp” nhưng khó defend trước rubric. Vai trò lead là **gom ý và chốt metric có thể đo**, không copy nguyên output AI vào báo cáo nhóm.

---

## 👤 Lê Đình Sỹ — MSSV: 2A202600770
*(Chưa nộp)*

## 👤 Nguyễn Hồng Phúc — MSSV: 2A202600843
*(Chưa nộp)*

## 👤 Vũ Văn Huy — MSSV: 2A202600750
*(Chưa nộp)*

## 👤 Nguyễn Đình Bảo Long — MSSV: 2A202600981
*(Chưa nộp)*
