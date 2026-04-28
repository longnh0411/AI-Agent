# svg-rule.md

## 1. Nguyên tắc chung

* Tất cả SVG **KHÔNG dùng dạng file `.svg` trực tiếp**
* SVG sẽ được convert thành **React Component (.tsx)**

👉 Mục tiêu:

* Dễ control
* Dễ style
* Dễ reuse
* Scale tốt trong project lớn

---

## 2. Cấu trúc thư mục

```bash
src/
 └── assets/
      └── icons/
           ├── IconUser.tsx
           ├── IconArrowLeft.tsx
           └── IconSearch.tsx
```

---

## 3. Quy tắc đặt tên

* Format:

  ```
  Icon{{TênIcon}}
  ```

### Ví dụ:

* `user.svg` → `IconUser.tsx`
* `arrow-left.svg` → `IconArrowLeft.tsx`
* `search.svg` → `IconSearch.tsx`

👉 Rule:

* PascalCase
* Prefix bắt buộc: `Icon`

---

## 4. Format component chuẩn

```tsx id="2f1m8a"
import React from "react";

type Props = React.SVGProps<SVGSVGElement>;

const IconUser = (props: Props) => {
  return (
    <svg
      viewBox="0 0 24 24"
      fill="none"
      stroke="currentColor"
      {...props}
    >
      <path
        strokeLinecap="round"
        strokeLinejoin="round"
        strokeWidth={2}
        d="..."
      />
    </svg>
  );
};

export default IconUser;
```

---

## 5. Quy tắc coding

### ✔️ Bắt buộc

* Dùng `React.SVGProps<SVGSVGElement>` cho props
* Spread `{...props}` vào `<svg>`
* Luôn có `viewBox`
* Dùng `currentColor` cho `fill` hoặc `stroke`

---

### ❌ Không được làm

* Hardcode màu:

```tsx id="0l5qrm"
stroke="black"
fill="red"
```

* Set width/height cứng trong component

---

## 6. Sử dụng trong code

```tsx id="z0sqe3"
import IconUser from "@/assets/icons/IconUser";

<IconUser className="w-6 h-6 text-blue-500" />
```

---

## 7. Styling

* Dùng `className` để control:

  * size
  * color
  * animation

### Ví dụ:

```tsx id="k0o2l7"
<IconUser className="w-5 h-5 text-gray-400 hover:text-blue-500" />
```

---

## 8. Tối ưu

* Trước khi convert:

  * Xóa attribute dư (`id`, `clipPath`, `defs`)
* Gộp path nếu có thể
* Dùng tool:

  * SVGO

---

## 9. Best Practices

* Mỗi icon = 1 file
* Không export nhiều icon trong 1 file
* Có thể tạo `index.ts` để export:

```ts id="rfj3vn"
export { default as IconUser } from "./IconUser";
export { default as IconSearch } from "./IconSearch";
```

---

## 10. Anti-pattern

❌ Dùng `<img src="icon.svg" />`
❌ Hardcode màu
❌ Không dùng `currentColor`
❌ Không support props
❌ Không có `viewBox`

---

## 11. Kết luận

👉 SVG = React Component = best practice
👉 Clean + scalable + reusable

Nếu làm đúng rule này:

* UI consistent
* Dev đỡ cực
* Design system xài cực mượt 😏
