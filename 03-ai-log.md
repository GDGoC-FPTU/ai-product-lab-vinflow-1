# 03-ai-log.md — Nhật ký chiêm nghiệm Phase 6 (AI Log & Reflection)

*   **Họ và tên:** Lê Đình Sỹ
*   **Mã số sinh viên (MSSV):** 2A202600770
*   **Tên nhóm:** Vinflow (Thư mục nhóm: `ai-product-lab-vinagang`)

---

## 🤖 1. AI đã giúp tôi những gì (AI as a Thought-partner)
Trong suốt quá trình thực hiện Lab 02, tôi đã sử dụng AI Gemini như một cộng sự đồng hành đắc lực để:
1.  **Brainstorm 12 bài toán thực tế:** Hỗ trợ quét rộng (scan) các khó khăn chân thực của một sinh viên mới. AI đã giúp tôi phân cấp các nhóm bài toán từ kỹ thuật nghiệp vụ (Git/GitHub, môi trường ảo Python `.venv`), kênh thông tin (Discord, Outlook, V-App) cho đến các kỹ năng mềm thích nghi khác.
2.  **Cấu trúc hóa Problem Cards chuyên nghiệp:** Hỗ trợ định lượng hóa các mục tiêu thành công bằng các con số cụ thể (Success Metrics) và phác thảo các quy trình trước/sau dưới dạng sơ đồ chữ (Text-based Flowchart) trực quan và dễ hiểu.
3.  **Tư duy giải pháp tối ưu:** Giúp tôi challege giữa các phương án Rule-based truyền thống, Workflow có sự tham gia của AI và Agent tự trị để tìm ra giải pháp gọn nhẹ nhất (LLM Feature), tránh bẫy lạm dụng công nghệ.

---

## ⚠️ 2. Điểm sai sót/ảo giác của AI (AI Hallucination & Failures)
Tuy nhiên, tôi cũng đã phát hiện và ghi nhận nhiều điểm hạn chế lớn của AI khi đóng vai trò cố vấn:
1.  **Đề xuất giải pháp cực đoan, thiếu an toàn (Over-engineering):** Khi thiết kế giải pháp gỡ lỗi Git/Terminal cho bài toán Onboarding công cụ số, AI ban đầu đã đề xuất xây dựng một **"Git Agent tự trị"** có quyền tự động truy cập và chạy lệnh `git push`/`git merge` trực tiếp trên máy tính sinh viên khi gặp lỗi. Giải pháp này cực kỳ nguy hiểm vì có thể ghi đè làm mất mã nguồn hoặc gây xung đột code nghiêm trọng.
2.  **Ảo giác thuật ngữ và giao diện:** AI bị ảo giác khi hướng dẫn sửa lỗi Git. Nó đã đề xuất các tham số lệnh Git không tồn tại và chỉ dẫn giao diện VS Code cũ đã bị thay thế ở phiên bản hiện tại.
3.  **Bỏ qua ranh giới con người kiểm duyệt (Bypass HITL):** Trong một số câu trả lời gợi ý tổng hợp deadline, AI đã tự ý đề xuất tự động gửi email nhắc nhở/cảnh báo trực tiếp cho giảng viên khi sinh viên trễ hạn, vi phạm nguyên tắc ứng xử học đường cơ bản.

---

## 🛠️ 3. Tôi đã điều chỉnh ranh giới (Prompt Boundary) ra sao?
Để ép AI hoạt động trong hành lang an toàn và mang lại giá trị thực tế, tôi đã áp dụng các kỹ thuật Prompt Engineering nghiêm ngặt:
1.  **Xác lập ranh giới quyền hạn cứng (Operational Boundary):** Tôi đã bổ sung chỉ thị nghiêm khắc: AI chỉ được phép đóng vai trò **"Cố vấn hướng dẫn" (Step-by-step Guide)**, phân tích thông báo lỗi và đưa ra gợi ý bằng văn bản. **CẤM TUYỆT ĐỐI** AI tự động sinh và thực thi script can thiệp hệ thống máy tính của sinh viên.
2.  **Áp dụng cơ chế Human-in-the-loop (Con người phê duyệt - HITL):** Mọi chỉ dẫn sửa lỗi Git hay tổng hợp deadline đều phải được trình bày rõ ràng dưới dạng bản nháp để sinh viên/trưởng nhóm tự tay duyệt và thực hiện trên Terminal của mình.
3.  **Định hình ngữ cảnh cụ thể (Context-grounding):** Thay vì hỏi chung chung, tôi cung cấp chính xác phiên bản Git, hệ điều hành (Windows/macOS) và loại bài lab để AI không đưa ra các hướng dẫn lỗi thời hoặc sai lệch.

Nhờ việc kiểm soát tốt ranh giới của AI, tôi không chỉ hoàn thành xuất sắc bản báo cáo cá nhân của mình mà còn đóng góp hiệu quả vào tư duy thiết kế ranh giới bảo mật cho dự án chung của nhóm.
