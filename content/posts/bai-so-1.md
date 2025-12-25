+++
title = "Bài 1: Socket Programming trong Java là gì?"
date = "2025-12-25"
draft = false
tags = ["Java", "Network"]
+++

Lập trình Socket là nền tảng của lập trình mạng. Trong Java, chúng ta sử dụng thư viện `java.net`.

**Ví dụ tạo một Server đơn giản:**
```java
ServerSocket server = new ServerSocket(8080);
Socket client = server.accept();
// Xử lý dữ liệu...