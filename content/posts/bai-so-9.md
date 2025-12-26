+++
title = "JSON và những sai lầm thường gặp khi gọi API"
date = "2025-12-26T16:00:00+07:00"
draft = false
author = "Võ Tấn Tài"
tags = ["JavaScript", "JSON", "Debug"]
description = "Cách xử lý chuỗi JSON và bắt lỗi HTTP 404, 500 đúng cách trong JavaScript."
+++

### JSON là gì?
JSON (JavaScript Object Notation) là định dạng dữ liệu phổ biến nhất để giao tiếp giữa Client và Server.
* `JSON.stringify(obj)`: Biến Object JS thành chuỗi JSON (để gửi đi).
* `JSON.parse(str)`: Biến chuỗi JSON thành Object JS (để sử dụng).

### Sai lầm khi dùng Fetch: Không check lỗi HTTP!

Rất nhiều bạn mới học nghĩ rằng dùng `catch()` là đủ. Nhưng thực tế, `fetch()` **không chạy vào catch** khi Server trả về lỗi 404 (Not Found) hay 500 (Server Error). Nó chỉ tính là lỗi khi mất mạng.

**Cách xử lý đúng:**

```javascript
const response = await fetch('/api/user/9999');

// Phải kiểm tra thuộc tính .ok
if (!response.ok) {
    console.error(`Lỗi HTTP: ${response.status}`);
    return;
}

const data = await response.json();
console.log(data);