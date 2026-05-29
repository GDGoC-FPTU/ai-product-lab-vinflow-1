# 01 — Problem Scan & Quick Cards — Nhóm Vinflow

> File này gộp bài **cá nhân** từng thành viên. Phần dưới là bài của **Leader**.

---

##  Vũ Quốc Bảo  — MSSV: 2A202600541

**Vai trò trong lab:** AI Product Engineer @ Vin Smart Future — phối hợp Khối Vận hành **Xanh SM (GSM)** và khảo sát pain point trước khi nhóm vote deep-dive.

---

# 🔍 Phase 1 — SCAN (Cá nhân)

Quét bài toán bằng **4 Lenses** trên các công ty thành viên Vingroup.

| # | Subsidiary | Lens | Mô tả ngắn bài toán |
|---|------------|------|---------------------|
| 1 | **Xanh SM** | Stakeholder Pain | Tài xế phàn nàn app gợi ý **điểm đón** lệch GPS thực tế 50–150m, khách hủy chuyến, tài xế mất ~8 phút/lượt chỉnh lại. |
| 2 | **Xanh SM** | Tốn thời gian | Điều phối viên xử lý thủ công **sự cố pin / hết pin giữa ca** (tra bản đồ, trạm trống, soạn tin) — ước tính **12–18 phút/lượt** giờ cao điểm. |
| 3 | **VinFast** | Lặp lại | Đối soát **hóa đơn sạc điện** giữa hệ thống trạm, đối tác và sổ tài xế đội xe — lặp lại hàng tuần, ~4 giờ/batch 200 xe. |
| 4 | **Vinhomes** | AI-upgrade | Phân loại & route phản hồi trên **App Vinhomes Resident**; CSKH trả lời mẫu, SLA phản hồi trung bình **~10–12 giờ**. |
| 5 | **Vinmec** | Stakeholder Pain | Bác sĩ soạn **tóm tắt xuất viện** thủ công từ hồ sơ điện tử — **20–25 phút/bệnh nhân**, backlog cuối ca. |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân)

Chọn **top 3** từ SCAN: **#2 (Xanh SM — sự cố pin), #4 (Vinhomes — CSKH), #1 (Xanh SM — điểm đón).**

---

## Card #1 — Xanh SM: Sai lệch gợi ý điểm đón

```text
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                       │
│                                                             │
│ Bài toán: Hệ thống gợi ý điểm đón taxi điện lệch so với    │
│ vị trí khách/tài xế thực tế, gây hủy chuyến và mất thời gian.│
│ Công ty thành viên: [x] Xanh SM (GSM)                       │
│                                                             │
│ Ai đang đau? Tài xế (chờ, đổi điểm), Điều phối (can thiệp), │
│              Khách hàng (chờ lâu, hủy cuốc)                 │
│                                                             │
│ Workflow thủ công hiện tại (5 bước):                        │
│   1. App gán điểm đón từ địa chỉ text/GPS cache             │
│   → 2. Tài xế đến nơi, phát hiện lệch vị trí                │
│   → 3. Gọi tổng đài / chat nội bộ xin đổi điểm              │
│   → 4. Điều phối sửa tay trên bản đồ + gửi lại tài xế       │
│   → 5. Tài xế xác nhận và tiếp tục cuốc                     │
│                                                             │
│ Bước nào tốn nhất? Bước 3–4 (⏱ ~8 phút/lượt)                │
│ AI có thể nhảy vào? Bước 1–2: chuẩn hóa địa chỉ + NLP/ghi   │
│ chú tài xế để refine pickup; draft tin nhắn xác nhận khách. │
│                                                             │
│ Metric: Giảm tỉ lệ cuốc cần can thiệp thủ công từ ~22%      │
│         xuống dưới 8%; thời gian chỉnh điểm từ 8 phút → <2 phút.│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x] LLM  [ ] Agent │
│ (Rule cho geo cơ bản; LLM cho mô tả địa điểm mơ hồ)         │
└─────────────────────────────────────────────────────────────┘
```

---

## Card #2 — Xanh SM: Xử lý sự cố sạc pin thực địa

```text
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2                                       │
│                                                             │
│ Bài toán: Tài xế báo pin thấp / hết pin giữa ca, cần hướng  │
│ dẫn trạm sạc hoặc xe sạc di động khẩn cấp.                  │
│ Công ty thành viên: [x] Xanh SM (GSM)                       │
│                                                             │
│ Ai đang đau? Tài xế (nguy cơ dừng xe), Điều phối (quá tải), │
│              Vận hành đội xe (SLA cứu hộ)                   │
│                                                             │
│ Workflow thủ công hiện tại (5 bước):                        │
│   1. Tài xế gọi/chat tổng đài báo % pin + biển số          │
│   → 2. Điều phối tra vị trí xe trên hệ thống                │
│   → 3. Tra thủ công trạm VinFast còn trụ / khoảng cách    │
│   → 4. Soạn tin chỉ đường + gửi app tài xế                  │
│   → 5. Nếu pin cực thấp: gọi xe sạc di động / cứu hộ       │
│                                                             │
│ Bước nào tốn nhất? Bước 2–4 (⏱ 12–15 phút/lượt)             │
│ AI có thể nhảy vào? Bước 2–4: đọc GPS + pin, gợi ý trạm,   │
│ draft JSON hành động; flag pin <5% → ưu tiên mobile charger.│
│                                                             │
│ Metric: Giảm thời gian xử lý sự cố từ 15 phút → dưới 3 phút;│
│         ≥95% draft đúng loại hành động (trạm vs cứu hộ).    │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

---

## Card #3 — Vinhomes: Phân loại phản hồi cư dân

```text
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                       │
│                                                             │
│ Bài toán: Phân loại & chuyển tiếp phản hồi/khiếu nại từ    │
│ App Vinhomes Resident tới bộ phận đúng (kỹ thuật, PCCC, phí).│
│ Công ty thành viên: [x] Vinhomes                            │
│                                                             │
│ Ai đang đau? Cư dân (chờ phản hồi), CSKH (đọc lặp),         │
│              Ban quản lý (SLA khiếu nại)                    │
│                                                             │
│ Workflow thủ công hiện tại (4 bước):                        │
│   1. Cư dân gửi ticket trên app                             │
│   → 2. CSKH đọc và gán nhãn thủ công                        │
│   → 3. Forward email/chat tới team kỹ thuật/pháp chế       │
│   → 4. Team xử lý và CSKH tổng hợp trả lời                 │
│                                                             │
│ Bước nào tốn nhất? Bước 2–3 (⏱ ~25 phút/ticket phức tạp)    │
│ AI có thể nhảy vào? Bước 2: classify intent + urgency;      │
│ draft phản hồi nháp [DRAFT_ONLY] cho CSKH duyệt.           │
│                                                             │
│ Metric: Giảm thời gian phân loại từ 25 phút → dưới 5 phút;   │
│         90% ticket đúng queue ngay lần đầu.                 │
│                                                             │
│ Quick Architecture: [ ] No AI  [x] Rule  [x] LLM  [ ] Agent │
│ (Rule cho từ khóa PCCC/khẩn; LLM cho mô tả dài)            │
└─────────────────────────────────────────────────────────────┘
```

---

## 💡 Gợi ý cho nhóm Vinflow (để vote Phase 3)

| Card | Ưu điểm | Rủi ro / nhược |
|------|---------|----------------|
| **#2 Sự cố pin** | Real-time, metric rõ, khớp starter `prompt_prototype.py` | Cần dữ liệu trạm sạc chính xác |
| **#1 Điểm đón** | Ảnh hưởng trực tiếp hủy chuyến | Phụ thuộc chất lượng GPS/map |
| **#3 Vinhomes** | Khối lượng ticket lớn | Rủi ro pháp lý nếu AI trả lời sai phí/tranh chấp |

> *Các thành viên khác: thêm section riêng bên dưới theo cùng format (SCAN + 3 cards).*

---

## 👤 Lê Đình Sỹ — MSSV: 2A202600770
*(Chưa nộp — thành viên điền Phase 1 & 2)*

## 👤 Nguyễn Hồng Phúc — MSSV: 2A202600843
*(Chưa nộp)*

## 👤 Vũ Văn Huy — MSSV: 2A202600750
*(Chưa nộp)*

## 👤 Nguyễn Đình Bảo Long — MSSV: 2A202600981
*(Chưa nộp)*
