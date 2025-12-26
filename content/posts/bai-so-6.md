+++
title = "Hiểu về Async/Await trong JavaScript: Tạm biệt Callback Hell"
date = "2025-12-26T13:00:00+07:00"
draft = false
author = "Võ Tấn Tài"
tags = ["JavaScript", "Async", "Frontend"]
description = "Hướng dẫn sử dụng Async/Await để viết code bất đồng bộ gọn gàng và dễ đọc hơn."
+++

### Vấn đề của JavaScript cũ

JavaScript là ngôn ngữ đơn luồng (single-threaded). Trước đây, để xử lý các tác vụ tốn thời gian như gọi API hay đọc file, chúng ta phải dùng **Callback**, dẫn đến tình trạng "Callback Hell" (code lồng nhau quá nhiều).

### Async/Await là gì?

Từ ES2017, `async/await` ra đời giúp viết code bất đồng bộ trông giống như đồng bộ (tuần tự), cực kỳ dễ đọc.

### Ví dụ minh họa

Cách viết cũ dùng Promise:
```javascript
function getData() {
    fetch('[https://api.example.com/user](https://api.example.com/user)')
        .then(res => res.json())
        .then(data => console.log(data))
        .catch(err => console.error(err));
}
```
Cách viết mới dùng Async/Await:
```javascript
async function getData() {
    try {
        const res = await fetch('[https://api.example.com/user](https://api.example.com/user)');
        const data = await res.json();
        console.log(data);
    } catch (error) {
        console.error("Lỗi rồi:", error);
    }
}
```
Rõ ràng là code mới nhìn "sạch" và logic hơn hẳn phải không?