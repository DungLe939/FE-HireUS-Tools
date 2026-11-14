# HireUS Frontend — hướng dẫn lập trình

## Hiện trạng và nguồn

Đọc [PROJECT_SOURCES.md](PROJECT_SOURCES.md) để tìm yêu cầu tại `../documents/`.
Kiểm tra manifest và code trên nhánh đang làm trước khi dựa vào mô tả baseline:

- Next.js App Router tại `src/app/`, React, TypeScript strict và npm.
- Alias `@/*` trỏ tới `src/*`; CSS toàn cục và CSS Modules.
- Baseline hiện tại chưa cấu hình Tailwind, auth hoặc test framework.

## Giao diện và tích hợp

- Trước khi xây hoặc sửa UI, đọc [UI context](.agents/rules/ui_context.md).
  Dùng tài liệu này cho hình thức và token; hành vi, quyền và ngưỡng đánh giá theo
  nguồn tại `PROJECT_SOURCES.md`. Có mâu thuẫn chưa rõ thì nêu để chốt, không tự bỏ nghiệp vụ.
- Giữ Server Components mặc định; dùng Client Components cho state tương tác,
  event handlers và browser APIs. Đặt code theo route; chỉ tách dùng chung khi có nhu cầu.
- Nối API theo contract backend; quy trình nằm tại
  [contracts/README.md](contracts/README.md). Không tự chọn endpoint, DTO,
  response, error shape hay auth còn thiếu. Thiết kế UI độc lập có thể tiếp tục
  khi contract chưa đủ, nhưng phải phân biệt dữ liệu mẫu với tích hợp thật.
- Giữ khóa dịch vụ và thao tác đặc quyền ở server. Kiểm tra quyền ở UI
  không thay thế kiểm tra quyền của backend.
- Xử lý trạng thái tải, rỗng, lỗi và thành công phù hợp với luồng được yêu cầu.

## Skills và quy trình

Các `SKILL.md` là hướng dẫn dùng chung cho nhiều agent. Nếu công cụ không tự nạp,
đọc file trực tiếp và dùng khả năng tương đương sẵn có; không giả định cú pháp gọi
skill hoặc tên tool giống nhau giữa các agent.

Chỉ đọc skill liên quan tại `.agents/skills/`:

| Công việc | Skill |
| --- | --- |
| Page, form, component, tương tác | [nextjs-feature](.agents/skills/nextjs-feature/SKILL.md) |
| Nối API | [rest-api-consumer](.agents/skills/rest-api-consumer/SKILL.md) |
| Review kỹ thuật | [frontend-quality](.agents/skills/frontend-quality/SKILL.md) |
| Hiệu năng React/Next.js | [vercel-react-best-practices](.agents/skills/vercel-react-best-practices/SKILL.md) |
| Review UI/khả năng truy cập | [web-design-guidelines](.agents/skills/web-design-guidelines/SKILL.md) |

Sửa nhỏ làm trực tiếp từ yêu cầu đủ rõ. Spec Kit tùy chọn cho tính năng lớn:
đọc [.agents/references/spec-kit.md](.agents/references/spec-kit.md) trước khi gọi
`speckit-*`. Project rules ưu tiên hơn ví dụ mặc định trong template;
không tự chọn OAuth/session hay chỉ tiêu hiệu năng chưa có nguồn.

Reviewer tại `.codex/agents/` là adapter riêng cho Codex. Với agent khác, dùng
`frontend-quality` và `rest-api-consumer` trực tiếp cho phần review liên quan.
Chỉ giao reviewer riêng khi tác vụ cho phép và công cụ hỗ trợ; không cần nhiều agent.

## Kiểm tra và bàn giao

Khi bắt đầu việc có sửa, kiểm tra nhánh/upstream và thay đổi local; nếu chưa cập nhật
nguồn cho đầu việc, nhắc pull một lần. Yêu cầu cập nhật/push cho phép fetch remote
liên quan; không pull khi chỉ đọc local. Dùng fast-forward khi sạch và chỉ behind;
không tự stash/reset hoặc force-push. Nếu phân kỳ, xem hai phía và bảo toàn lịch sử.

Trước bàn giao/push, xem cả commit chưa push, diff và file mới liên quan; đối chiếu
README/cách chạy, config mẫu, contract, spec/tasks và tài liệu yêu cầu. Cập nhật
tài liệu kỹ thuật/tổng hợp bị tác động, sửa/gộp/bỏ bản dẫn xuất lỗi thời có căn cứ;
không đổi nghiệp vụ chỉ để khớp code lỗi. Đọc hướng dẫn documents trước khi sửa.
Nếu mở workspace, đọc `../.agents/skills/team-sync/SKILL.md` và skill
`docs-maintenance` trong repo tài liệu; clone riêng vẫn áp dụng các bước trên.
Thiếu checkout tài liệu thì nêu phần chưa đối chiếu, hỏi đường dẫn nếu cần và
tiếp tục phần độc lập; không báo đã sync mọi tài liệu.

Với code thay đổi, chạy kiểm tra phù hợp từ repo này:

```bash
npm run lint
npx tsc --noEmit
npm run build
```

Chưa có lệnh test trong baseline; kiểm tra lại `package.json` nếu nhánh đã thay đổi.
Không thêm test framework cho một sửa không liên quan.

Phần cập nhật tài liệu liên quan trước bàn giao/push thuộc quy trình nhóm ở trên;
sửa repo khác ngoài phần đó cần yêu cầu phối hợp. Đọc hướng dẫn repo kia trước khi sửa.
Giữ nhánh đang làm, bảo vệ thay đổi local. Skills/hướng dẫn là tài nguyên nhóm,
không thêm vào ignore. Chỉ commit/push khi được yêu cầu.
Báo đã làm gì, kiểm tra đã chạy, tài liệu sửa/giữ/xóa và lý do, phần còn thiếu;
giải thích luồng đáng chú ý bằng tiếng Việt. Push bị remote đi trước thì fetch,
tích hợp cùng đích đã xác minh, rà lại tài liệu và kiểm tra phần bị tác động.
Sau push, xác nhận commit/nhánh đích; không coi push FE là đã công bố documents hoặc repo cha.
