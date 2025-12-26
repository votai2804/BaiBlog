
+++
title = "WebSocket là gì? Tại sao Chat App lại cần nó?"
date = "2025-12-26T15:00:00+07:00"
draft = false
author = "Võ Tấn Tài"
tags = ["JavaScript", "WebSocket", "Real-time"]
description = "Phân biệt HTTP và WebSocket. Cách tạo kết nối thời gian thực đơn giản với JavaScript."
+++

### HTTP vs WebSocket

* **HTTP:** Mỗi lần muốn lấy dữ liệu mới, Client phải "hỏi" Server (Request) rồi Server mới trả lời (Response). Giống như bạn nhắn tin hỏi người yêu: *"Em ăn cơm chưa?"* rồi chờ trả lời.
* **WebSocket:** Tạo một đường ống kết nối 2 chiều liên tục. Server có thể tự động đẩy tin nhắn về Client bất cứ lúc nào mà không cần hỏi. Giống như đang gọi điện thoại nói chuyện trực tiếp.

### Code Demo WebSocket Client

```javascript
// 1. Tạo kết nối đến Server
const socket = new WebSocket('wss://echo.websocket.org');

// 2. Lắng nghe khi kết nối thành công
socket.onopen = function(event) {
  console.log("Đã kết nối!");
  socket.send("Xin chào Server!"); // Gửi tin nhắn
};

// 3. Nhận tin nhắn từ Server gửi về
socket.onmessage = function(event) {
  console.log("Tin nhắn từ Server:", event.data);
};
```