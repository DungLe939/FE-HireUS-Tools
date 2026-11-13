---
name: vercel-react-best-practices
description: Áp dụng các quy tắc hiệu năng React và Next.js của Vercel cho code HireUS khi viết hoặc review rendering, fetching, bundle và tương tác.
license: MIT
metadata:
  author: vercel
  version: "1.0.0"
  maintainer: HireUS Tools
---

# Hiệu năng React/Next.js cho HireUS

Đọc [AGENTS.md](../../../AGENTS.md) để giữ đúng kiến trúc và phạm vi.
Bộ quy tắc Vercel được lưu trong `rules/`; chỉ mở các rule liên quan đến code
đang làm. Đây là hướng dẫn dùng cho HireUS, phần tài liệu upstream vẫn được giữ.

## Chọn nhóm quy tắc

| Dấu hiệu cần xem | Bắt đầu từ |
| --- | --- |
| Fetch độc lập bị chờ tuần tự | [async-parallel](rules/async-parallel.md) |
| Chờ dữ liệu trước khi biết có cần dùng | [async-defer-await](rules/async-defer-await.md) |
| Bundle lớn do import tập trung | [bundle-barrel-imports](rules/bundle-barrel-imports.md) |
| Component nặng chỉ dùng khi tương tác | [bundle-dynamic-imports](rules/bundle-dynamic-imports.md) |
| Lặp dữ liệu server theo request | [server-cache-react](rules/server-cache-react.md) |
| Effect đồng bộ state có thể tính trực tiếp | [rerender-derived-state-no-effect](rules/rerender-derived-state-no-effect.md) |
| Memo hóa biểu thức đơn giản | [rerender-simple-expression-in-memo](rules/rerender-simple-expression-in-memo.md) |

Dùng [tài liệu tổng hợp](AGENTS.md) khi cần tra cứu nhiều nhóm; không tải toàn bộ
72 rule files cho một sửa nhỏ. Các ví dụ SWR/cache/library không cho phép tự cài
dependency hoặc đổi kiến trúc.

## Áp dụng có căn cứ

Xác định đường gây chậm, ảnh hưởng người dùng và cơ sở so sánh trước khi tối ưu.
Không dùng cache toàn cục cho CV, transcript hoặc dữ liệu theo tài khoản nếu chưa
xác định isolation/invalidation. Không đánh đổi correctness, quyền hoặc khả năng
hiểu code chỉ để theo một pattern hiệu năng.

Khi review, nêu trigger và tác động cụ thể; không đưa mọi khuyến nghị thành lỗi.
Khi sửa, chạy checks phù hợp theo `AGENTS.md`; nếu chưa đo, mô tả đây là cải thiện
cấu trúc dự kiến, không khẳng định số phần trăm hoặc độ trễ đã giảm.
