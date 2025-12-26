+++
title = "Design Patterns - Những 'mẫu thiết kế' cứu cánh cho lập trình viên"
date = "2025-12-26T11:00:00+07:00"
draft = false
author = "Võ Tấn Tài"
tags = ["Design Patterns", "Java", "Architecture"]
description = "Giới thiệu 3 mẫu Design Patterns kinh điển (Singleton, Observer, Factory) giúp giải quyết các vấn đề phổ biến trong thiết kế phần mềm."
+++

### Design Patterns là gì?

Bạn có bao giờ cảm thấy mình đang "phát minh lại cái bánh xe" khi giải quyết một vấn đề code không? **Design Patterns** chính là tập hợp những giải pháp tối ưu đã được các chuyên gia đúc kết và kiểm chứng qua hàng thập kỷ cho những vấn đề lặp đi lặp lại đó.

Dưới đây là 3 mẫu (patterns) nhập môn mà bất kỳ lập trình viên nào cũng nên biết:

### 1. Singleton Pattern
**Mục đích:** Đảm bảo một Class chỉ có duy nhất **1 thực thể (instance)** tồn tại trong suốt vòng đời ứng dụng.
* **Ứng dụng:** Kết nối Database, quản lý cấu hình (Config Manager), Logging.
* **Ví dụ (Java):**
```java
public class Database {
    private static Database instance;
    
    private Database() {} // Constructor private để chặn tạo mới từ bên ngoài

    public static Database getInstance() {
        if (instance == null) {
            instance = new Database();
        }
        return instance;
    }
}