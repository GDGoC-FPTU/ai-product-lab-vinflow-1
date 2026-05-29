# 02 — Deep-Dive Report — Nhóm Vinflow

## Thông tin nhóm

| | |
|---|---|
| **Tên nhóm** | Vinflow |
| **Bài toán chọn** | Card #2 — Xanh SM: Xử lý sự cố sạc pin thực địa |
| **Nguồn card** | Vũ Quốc Bảo (Leader) — `01-problem-scan.md` |

### Thành viên

| Họ và tên | MSSV |
|-----------|------|
| Vũ Quốc Bảo | 2A202600541 |
| Lê Đình Sỹ | 2A202600770 |
| Nguyễn Hồng Phúc | 2A202600843 |
| Vũ Văn Huy | 2A202600750 |
| Nguyễn Đình Bảo Long | 2A202600981 |

---

# 🗳️ Quyết định lựa chọn của nhóm

Nhóm **Vinflow** thống nhất chọn **Card #2 — Xanh SM: Xử lý sự cố sạc pin thực địa** (đề xuất Leader) để Deep-Dive, prototype prompt và đánh giá GO/NOT YET/NO-GO.

## Lý do lựa chọn

- **Real-time:** Ảnh hưởng trực tiếp tài xế đang chạy ca,người dùng đang di chuyển làm mất doanh thu cuốc xe cũng như là thời gian người dùng.
- **Metric rõ:** Thời gian xử lý/lượt, tỉ lệ hướng dẫn đúng trạm — đo được sau pilot.
- **AI Fit vừa đủ:** Quy trình có cấu trúc, dùng **LLM Feature** + rule (pin <5%) thay vì multi-agent.
- **Khớp starter code:** Ranh giới `[DRAFT_ONLY]` và `dispatch_mobile_charger` đã có trong `prompt_prototype.py`.

## Loại bỏ các card khác (từ SCAN Leader)

| Card | Lý do không chọn |
|------|------------------|
| **#1 — Sai lệch điểm đón** | Phụ thuộc chất lượng GPS/map; cần baseline A/B map trước khi cam kết metric. |
| **#3 — Vinhomes CSKH** | Rủi ro pháp lý/phí quản lý nếu AI trả lời sai; nên rule-router trước, LLM sau. |

---

# 🏗️ Phase 3 — DEEP-DIVE

## 3.1. Current-State Workflow

Quy trình xử lý sự cố pin thực địa tại Trung tâm Điều vận Xanh SM (tham chiếu vẽ tay → `04-workflow-diagram.png`):

```text
┌──────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│ Bước 1       │     │ Bước 2       │     │ Bước 3       │     │ Bước 4       │
│ Nhận báo     │     │ Tra GPS xe   │     │ Tra trạm     │     │ Soạn tin     │
│ sự cố pin    │ ──→ │ trên bản đồ  │ ──→ │ VinFast trống│ ──→ │ chỉ dẫn      │
│ (gọi/chat)   │     │ nội bộ       │     │ + loại cổng  │     │ gửi app      │
│ Ai: Dispatch │     │ Ai: Dispatch │     │ Ai: Dispatch │     │ Ai: Dispatch │
│ ⏱ ~2 phút    │     │ ⏱ ~2 phút    │     │ ⏱ ~6 phút 🔴 │     │ ⏱ ~5 phút 🔴 │
│ In: Biển số, │     │ In: Log sự   │     │ In: Toạ độ,  │     │ In: Địa chỉ  │
│ % pin        │     │ cố           │     │ model xe     │     │ trạm         │
│ Out: Ticket  │     │ Out: GPS     │     │ Out: Trạm    │     │ Out: SMS nháp│
└──────────────┘     └──────────────┘     └──────────────┘     └──────────────┘
                                                                      │
                                                                      ▼
                                                               ┌──────────────┐
                                                               │ Bước 5       │
                                                               │ Gọi xe sạc   │
                                                               │ di động nếu  │
                                                               │ pin cực thấp │
                                                               │ ⏱ ~2 phút    │
                                                               └──────────────┘

🔄 Handoff: Tài xế → Tổng đài/Chat → Điều phối → App tài xế (và đội cứu hộ nếu cần)
🔴 Bottleneck: Bước 3–4 (tra trạm thủ công + soạn tin)
⏱ Tổng: ~15–17 phút/lượt (giờ cao điểm)
```

---

## 3.2. Problem Statement (6-field)

| Field | Nội dung |
|-------|----------|
| **1. Actor / Operator** | Điều phối viên (Dispatcher) — Trung tâm Điều vận Xanh SM (GSM). |
| **2. Current Workflow** | Tài xế/Người dùng báo % pin qua tổng đài/chat → điều phối tra GPS, mở dashboard trạm VinFast tìm trụ trống phù hợp dòng xe (VF5/VFe34/VF8), soạn tin chỉ đường gửi app, gọi xe sạc di động nếu pin nguy hiểm. 5 bước thủ công. |
| **3. Bottleneck** | Bước 3–4 (~11 phút): tra trụ trống + soạn tin tiếng Việt; dễ sai khi quá tải giờ cao điểm. |
| **4. Business Impact** | Giả định ~60–80 sự cố pin/ngày tại Hà Nội × 15 phút ≈ **15–20 giờ-lao động điều vận/ngày**. Tài xế chờ lâu → mất cuốc, stress, rò rỉ doanh thu (cần đo baseline thực tế). |
| **5. Success Metric** | (1) Giảm thời gian xử lý **15 phút → dưới 3 phút**. (2) ≥**95%** draft đúng loại hành động (trạm gần vs `dispatch_mobile_charger`). (3) **98%** hướng dẫn đúng loại trụ/cổng sạc (sau HITL). |
| **6. Operational Boundary** | AI được: đọc GPS + % pin (API), gợi ý trạm/trụ, soạn **nháp** tin chỉ dẫn. **Cấm:** tự gửi tin (bắt buộc `[DRAFT_ONLY]` + dispatcher duyệt); pin **<5%** thì **cấm** gợi ý trạm **>5km** — phải `dispatch_mobile_charger`; không đổi giá/cước; không cam kết thời gian đến cứu hộ nếu chưa có SLA API. |

---

## 3.3. Future-State Flow & AI Fit

### AI-Fit Matrix

| Phương án | Đánh giá |
|-----------|----------|
| **No AI** | Không đạt metric 3 phút khi volume cao. |
| **Rule only** | Đủ cho pin <5% + khoảng cách; không đủ soạn tin tự nhiên, đa ngữ cảnh. |
| **LLM Feature** ✅ | Draft tin + JSON hành động; rule cứng cho ngưỡng pin. |
| **Agentic Loop** | Không chọn — rủi ro hành động sai trên đường, chi phí vận hành cao. |

### Future-State Flow

```text
┌──────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│ Bước 1       │     │ Bước 2       │     │ Bước 3       │     │ Bước 4       │
│ Nhận báo     │     │ 🔵 Rule+API  │     │ 🔵 LLM draft │     │ 🟢 HITL gửi  │
│ sự cố        │ ──→ │ GPS + trạm   │ ──→ │ [DRAFT_ONLY] │ ──→ │ dispatcher   │
│              │     │ trống        │     │ SMS/JSON     │     │ click Send   │
└──────────────┘     └──────────────┘     └──────────────┘     └──────────────┘
                                                                      │
                    ↩️ Fallback: LLM lỗi / confidence thấp / JSON invalid
                    → Dispatcher xử lý thủ công như current-state (Bước 3–4 cũ)
```

- **🔵 AI Step:** Gom dữ liệu trạm + soạn draft / JSON `recommend_station` hoặc `dispatch_mobile_charger`.
- **🟢 Human Step (HITL):** Điều phối đọc, sửa, bấm gửi app tài xế.
- **↩️ Fallback:** Không auto-send; log lỗi; queue thủ công.

---

# 💻 Phase 4 — Prompt Prototype & Boundary Test

File: [`extras/prompt_prototype.py`](extras/prompt_prototype.py)

### Ranh giới (Operational Boundary)

| # | Quy tắc |
|---|---------|
| 1 | Mọi output **bắt đầu** `[DRAFT_ONLY]` — không auto-send cho tài xế. |
| 2 | Pin **< 5%**: **không** gợi ý trạm **> 5km**; bắt buộc JSON `{"action": "dispatch_mobile_charger", "reason": "..."}`. |

### Adversarial tests (tóm tắt)

1. Pin 2% + yêu cầu trạm 8km + bỏ nháp → phải cứu hộ mobile, giữ `[DRAFT_ONLY]`.
2. Pin đủ, user ép bỏ tag `[DRAFT_ONLY]` → vẫn giữ tag.
3. User giả mạo “đã duyệt, gửi thẳng” → vẫn draft-only.

Chạy local:

```powershell
$env:GEMINI_API_KEY="your-key"
python extras/prompt_prototype.py
```

---

# 🏁 Phase 5 — EVALUATE

### AI Readiness Checklist

| # | Câu hỏi | Trả lời nhóm Vinflow |
|---|---------|----------------------|
| 1 | Có dữ liệu mẫu/logs sạch để test? | **Một phần** — có log sự cố pin (ẩn danh) từ điều vận; cần thêm 2 tuần baseline thời gian xử lý. |
| 2 | Rủi ro AI sai có kiểm soát? | **Có** — HITL + fallback thủ công; rule pin <5%; không auto-send. |
| 3 | Stakeholder sẵn sàng đổi quy trình? | **Có** — Khối vận hành GSM ưu tiên giảm TTR sự cố pin; cần training 1 buổi cho dispatcher. |

### Quyết định: **GO** ✅

**Lý giải kỹ thuật & chi phí:**

- **Scope pilot hẹp:** 1 trung tâm điều vận (HN), chỉ luồng “pin thấp + cần trạm/cứu hộ”, không mở rộng billing/CSKH.
- **Chi phí ước tính (3 tháng pilot):**
  - LLM API (Gemini Flash): ~**$200–400/tháng** (giả định 2.000 lượt/tháng × ~2k token/lượt).
  - Tích hợp API trạm + GPS: **2 engineer × 3 tuần** (nội bộ Vin Smart Future).
  - Không triển khai Agent/autonomous dispatch trong pilot.
- **ROI định hướng:** Giảm 12 phút/lượt × 70 lượt/ngày ≈ **14 giờ dispatcher/ngày** — đủ bù chi phí API nếu baseline xác nhận.

**NOT YET** nếu sau 2 tuần không đo được baseline thời gian xử lý. **NO-GO** nếu pháp chế cấm LLM đọc vị trí tài xế real-time — hiện chưa có rào cản này trong phạm vi pilot nội bộ.

---

## Kết luận

Dự án **Vinflow — Co-pilot sự cố pin Xanh SM** đạt **GO**: bài toán cụ thể, metric đo được, kiến trúc LLM + rule, ranh giới đã prototype trong `extras/prompt_prototype.py`. Bước tiếp theo: pilot 2 tuần + đo TTR và % draft accepted sau HITL.