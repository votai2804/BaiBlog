+++
title = "Hướng dẫn Fetch API: Cách lấy dữ liệu từ Server chuẩn hiện đại"
date = "2025-12-26T14:00:00+07:00"
draft = false
author = "Võ Tấn Tài"
tags = ["JavaScript", "API", "Network"]
description = "Quên AJAX đi, Fetch API mới là tiêu chuẩn để thực hiện HTTP Request trong trình duyệt hiện nay."
+++

### Fetch API là gì?

`fetch()` là một hàm có sẵn trong mọi trình duyệt hiện đại, dùng để gửi các yêu cầu HTTP (GET, POST, PUT...) đến máy chủ mà không cần thư viện ngoài như Axios hay jQuery.

### 1. Gửi yêu cầu GET (Lấy dữ liệu)
```javascript
fetch('[https://jsonplaceholder.typicode.com/posts/1](https://jsonplaceholder.typicode.com/posts/1)')
  .then(response => response.json())
  .then(json => console.log(json));
```
### 2. Gửi yêu cầu POST (Tạo dữ liệu mới)
```javascript
fetch('[https://jsonplaceholder.typicode.com/posts](https://jsonplaceholder.typicode.com/posts)', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    title: 'Bài viết mới',
    body: 'Nội dung bài viết...',
    userId: 1,
  }),
})
  .then(res => res.json())
  .then(data => console.log("Thành công:", data));
```
Làm chủ Fetch API là kỹ năng bắt buộc của mọi Frontend Developer!