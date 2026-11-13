---
name: rest-api-consumer
description: Tích hợp hoặc rà soát frontend HireUS với contract API backend; dùng khi nối dữ liệu, session hoặc xử lý lỗi HTTP.
---

# Tiêu thụ API từ frontend

Đọc [PROJECT_SOURCES.md](../../../PROJECT_SOURCES.md) và
[ranh giới contract](../../../contracts/README.md).
Tìm contract backend trong checkout được cung cấp; ghi đường dẫn và revision.
Nếu chỉ được review, báo findings và không sửa.

Trước khi nối một operation, xác định method/path, input/output, status/error,
quyền truy cập và cách truyền session từ contract. Không tự bịa token storage,
refresh flow hoặc payload còn thiếu. Đầu việc thiết kế contract được chuyển về
vai trò backend; không yêu cầu contract có sẵn để bắt đầu chính việc thiết kế nó.

- Dùng consumer types/adapters theo contract, không tạo bản contract nguồn thứ hai.
- Chọn server hoặc client fetching theo tương tác thực tế; secrets giữ ở server.
- Phân biệt lỗi mạng, timeout, HTTP lỗi, dữ liệu sai và trạng thái đang xử lý
  nếu contract có phân biệt. Không ép lỗi phân tích thành điểm 0 hay danh sách trống.
- Chỉ retry operation có semantics cho phép; tránh tạo trùng phiên, phân tích,
  thông báo hoặc lần lưu khi người dùng bấm lại.
- Giữ kết quả đã có khi bước gợi ý/báo cáo lỗi; quyền truy cập vẫn do backend kiểm tra.
- Khi contract đổi, rà callers và trạng thái UI bị ảnh hưởng. Đánh dấu mock,
  không báo đã nối dịch vụ thật chỉ vì response mẫu đúng kiểu.

Kiểm tra mapping và lỗi bằng công cụ hiện có trong repo; chạy checks liên quan
tại `AGENTS.md`. Báo operation/revision, hành vi đã kiểm tra và phần chưa nối được.
