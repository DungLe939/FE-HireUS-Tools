---
name: web-design-guidelines
description: Rà soát UI HireUS về khả năng sử dụng, accessibility và tính nhất quán; dùng khi người dùng yêu cầu review giao diện hoặc UX.
metadata:
  author: vercel
  version: "1.0.0"
  maintainer: HireUS Tools
---

# Review UI và UX

Đọc [AGENTS.md](../../../AGENTS.md), màn hình/luồng được yêu cầu và yêu cầu sản phẩm
tại [PROJECT_SOURCES.md](../../../PROJECT_SOURCES.md). Review chỉ đọc trừ khi có yêu cầu sửa.

Nếu cần áp dụng Web Interface Guidelines của Vercel, lấy bản hiện tại qua công cụ
web có sẵn từ https://raw.githubusercontent.com/vercel-labs/web-interface-guidelines/main/command.md.
Không truy cập được thì báo giới hạn; vẫn có thể review UI trong phạm vi nguồn local,
nhưng không gọi đó là audit guideline mới nhất.

Kiểm tra theo tình huống người dùng:
- Form có label, lỗi tại trường, thứ tự focus và thao tác keyboard.
- Loading/rỗng/lỗi/thử lại có ý nghĩa; thao tác xóa cần xác nhận theo yêu cầu.
- Điểm, thời hạn tin và trạng thái xử lý có nhãn chữ, không chỉ màu.
- Nội dung dài, tiếng Việt và kích thước màn hình thuộc phạm vi hỗ trợ.
- Trình chỉnh sửa CV không mất dữ liệu; AI chưa duyệt không được áp dụng.
- Màn hình prototype có thể cũ hơn đặc tả. Dùng quy tắc nguồn để chọn hành vi,
  không khôi phục tính năng đã bị loại chỉ vì nút vẫn xuất hiện trong ảnh.

Báo findings theo file/vị trí hoặc màn hình, trigger và tác động.
Chỉ mô tả những gì đã nhìn thấy/chạy thử; ảnh tĩnh không chứng minh tương tác hoạt động.
