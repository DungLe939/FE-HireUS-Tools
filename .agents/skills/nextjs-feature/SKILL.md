---
name: nextjs-feature
description: Triển khai hoặc sửa page, component, form và tương tác Next.js trong HireUS; dùng cho công việc frontend có phạm vi rõ.
---

# Làm tính năng frontend

Đọc [AGENTS.md](../../../AGENTS.md) và [PROJECT_SOURCES.md](../../../PROJECT_SOURCES.md).
Xác định màn hình, luồng và tiêu chí nghiệm thu từ nguồn mới nhất; inspect route,
components, styles và manifest trên nhánh đang làm trước khi chọn cấu trúc.

- Dùng Server Components cho phần phù hợp; đặt Client boundary ở thao tác tương tác,
  microphone và browser APIs. Tận dụng CSS/pattern hiện có, không tự thêm UI framework.
- Giữ dữ liệu đầu vào, kết quả đã lưu và thay đổi chưa lưu phân biệt rõ. Chỉ báo lưu
  hoặc áp dụng thành công sau khi thao tác thật hoàn tất.
- Tạo trạng thái tải/rỗng/lỗi/thành công theo luồng; cho thử lại đúng bước thất bại
  và giữ phần dữ liệu đã có.
- Với form nhiều bước, đổi đầu vào phải vô hiệu hóa kết quả phụ thuộc đã cũ.
  Bước xác nhận của người dùng phải là thao tác thật, không chỉ một nhãn UI.
- Microphone cần quyền browser và kiểm tra tín hiệu; cleanup tài nguyên khi rời phiên.
  Dữ liệu demo không chứng minh STT/TTS hoặc lưu dữ liệu đã tích hợp.
- Khi nối API, dùng [rest-api-consumer](../rest-api-consumer/SKILL.md).
  Thiếu contract chỉ chặn phần tích hợp phụ thuộc; vẫn làm được UI đã rõ.

Kiểm tra thao tác chính, keyboard/focus, dữ liệu dài và các trạng thái biên liên quan.
Chạy lint/typecheck/build phù hợp theo `AGENTS.md`; dùng test framework chỉ khi repo
thực sự có và đầu việc cần. Báo hành vi đã làm, nguồn, file và kiểm tra thực tế.
