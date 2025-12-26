+++
title = "Kỹ thuật viết mã nguồn sạch (Clean Code) cho người mới"
date = "2025-12-26"
draft = false
author = "Võ Tấn Tài"
tags = ["Clean Code", "Lập trình"]
description = "Clean Code không phải là làm cho mã chạy nhanh hơn, mà là làm cho mã dễ đọc và dễ bảo trì hơn."
+++

### Clean Code là gì?

Clean Code không đơn thuần là làm cho mã chạy nhanh hơn, mà trọng tâm là làm cho mã **dễ đọc** và **dễ bảo trì** hơn cho chính bạn và đồng nghiệp trong tương lai.

Dưới đây là một vài nguyên tắc vàng mà mọi lập trình viên nên nằm lòng:

#### 1. Đặt tên có tâm
Tránh đặt tên biến chung chung như `a`, `b`, `c` hay `d`. Tên phải nói lên ý nghĩa và mục đích của nó.
* **Nên tránh:** `int d; // số ngày đã trôi qua`
* **Nên dùng:** `int daysSinceCreation;`

#### 2. Hàm chỉ làm một việc (Single Responsibility)
Một hàm chỉ nên thực hiện một nhiệm vụ duy nhất và hoàn thành nó thật tốt. Nếu hàm của bạn vừa tính toán logic vừa thực hiện gửi email, hãy chia nó làm đôi để dễ kiểm soát và tái sử dụng.

#### 3. Đừng lặp lại chính mình (Nguyên tắc DRY - Don't Repeat Yourself)
Nếu bạn thấy mình đang copy-paste một đoạn code quá 2 lần, đó là dấu hiệu bạn nên tách đoạn mã đó thành một hàm hoặc một lớp dùng chung. Điều này giúp giảm thiểu sai sót khi cần cập nhật logic sau này.

#### 4. Comment đúng chỗ
Code tốt là code có khả năng tự giải thích chính nó thông qua cách đặt tên và cấu trúc. Hãy chỉ sử dụng comment khi bạn cần giải thích **"tại sao"** mình lại làm như vậy (quyết định thiết kế) chứ không phải giải thích code đang làm **"cái gì"**.

---
*Hy vọng những chia sẻ nhỏ này sẽ giúp ích cho quá trình phát triển phần mềm của bạn!*