# .kilocode

Thư mục cấu hình và quy tắc cho AI Agent trong dự án PlayTogether.

## 📁 Cấu trúc thư mục

```
.kilocode/
├── mcp.json                 # Cấu hình MCP (Model Context Protocol)
├── README.md               # Tài liệu này
├── rules/                  # Quy tắc phát triển
│   ├── answer-rule.md      # Quy tắc trả lời của AI Agent
│   └── svg-rule.md        # Quy tắc sử dụng SVG trong dự án
└── skills/                 # Kỹ năng chuyên môn
    ├── deploy-to-vercel/   # Kỹ năng triển khai lên Vercel
    ├── vercel-react-best-practices/  # Best practices cho React/Next.js
    └── web-design-guidelines/        # Quy tắc thiết kế UI/UX
```

## 📋 Quy tắc phát triển

### answer-rule.md
Quy định cấu trúc trả lời của AI Agent:
- Tất cả câu trả lời phải bằng tiếng Việt
- Tối đa 3 gạch đầu dòng cho mỗi vấn đề

### svg-rule.md
Quy tắc sử dụng SVG trong dự án:
- Tất cả SVG phải được convert thành React Component (.tsx)
- Đặt tên theo format `Icon{{TênIcon}}` (PascalCase với prefix `Icon`)
- Dùng `React.SVGProps<SVGSVGElement>` cho props
- Sử dụng `currentColor` cho fill/stroke
- Không hardcode màu hoặc kích thước trong component

## 🚀 Kỹ năng chuyên môn

### deploy-to-vercel
Kỹ năng triển khai ứng dụng lên Vercel với các tính năng:
- Tự động tạo deployment
- Quản lý preview deployments
- Cấu hình environment variables
- Tối ưu hóa build process

### vercel-react-best-practices
Best practices từ Vercel Engineering cho React/Next.js:
- Rendering optimization
- Bundle optimization
- Rerender optimization
- Async operations
- Server-side optimization
- JavaScript optimization

### web-design-guidelines
Quy tắc thiết kế UI/UX:
- Tuân thủ Web Interface Guidelines
- Kiểm tra accessibility
- Audit design
- Review UX

## 🔧 Cấu hình

### mcp.json
Cấu hình MCP cho phép AI Agent truy cập và tương tác với các dịch vụ bên ngoài.

## 📝 Sử dụng

Khi AI Agent làm việc với dự án, nó sẽ tự động:
1. Kiểm tra các quy tắc trong thư mục `rules/`
2. Áp dụng các kỹ năng từ `skills/` khi phù hợp
3. Tuân thủ các quy định về ngôn ngữ và cấu trúc trả lời

## 🎯 Mục tiêu

- Đảm bảo code quality nhất quán
- Tối ưu hóa performance
- Tuân thủ best practices
- Giữ code clean và maintainable
- Hỗ trợ AI Agent làm việc hiệu quả
