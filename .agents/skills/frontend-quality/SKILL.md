---
name: frontend-quality
description: Review code frontend HireUS về lỗi hành vi, dữ liệu, Next.js, accessibility và tích hợp API; mặc định chỉ đọc.
---

# Review frontend

Đọc [AGENTS.md](../../../AGENTS.md), diff và callers/routes trực tiếp liên quan.
Với hành vi sản phẩm, dùng [PROJECT_SOURCES.md](../../../PROJECT_SOURCES.md)
để đối chiếu bản yêu cầu mới nhất; kế hoạch chưa triển khai không tự là bug.

Ưu tiên lỗi có tác động quan sát được:
- Dữ liệu cũ còn được tính/xác nhận sau khi input đổi; áp gợi ý khi chưa duyệt;
  báo thành công khi lưu lỗi hoặc làm mất dữ liệu khi bước sau thất bại.
- Sai quyền/session, lộ secrets, response không khớp contract hoặc request lặp.
- Sai Server/Client boundary, hydration, effect cleanup và tài nguyên âm thanh.
- Form errors, keyboard/focus, nhãn trạng thái và thông tin chỉ thể hiện bằng màu.
- Hiệu năng có đường gây chậm cụ thể; chỉ đọc quy tắc Vercel liên quan,
  không yêu cầu refactor cả app để khớp mọi ví dụ.

Kiểm tra test/checks thực tế đã có; không tự cài framework hoặc sửa code trong review.
Mỗi finding ghi mức độ, file/dòng, trigger, tác động và căn cứ. Tách lỗi xác nhận
khỏi điểm cần hỏi. Nếu không có finding, nêu phạm vi đã xem và giới hạn kiểm tra.
Agent hiện tại tự review được; reviewer/subagent riêng là tùy khả năng và yêu cầu.
