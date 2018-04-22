---
title   : Overview
anchors : true
---

# Overview

**Kites** là một dự án mã nguồn mở đầy tham vọng với mục tiêu là tạo ra các ứng dụng Web một cách nhanh chóng, rất phù hợp cho doanh nghiệp vừa và nhỏ.

Bạn có thể khởi tạo nhanh chóng một ứng dụng kites bằng lệnh sau đây:

```bash
kites init my-project --template restful
```

Kết thúc lệnh trên là bạn đã tạo ra một dự án RESTful API, rất đơn giản và nhanh chóng.

## Mục tiêu của dự án Kites

* Là 1 framework tạo ra các ứng dụng web đầy tham vọng
* Là 1 công cụ dòng lệnh, hỗ trợ khởi tạo nhanh dự án
* Mô-đun hóa các thành phần, tiện ích tái sử dụng thành các phần mở rộng (extensions)
* Phân tách tầng ứng dụng: device access layer, database access layer, cron jobs, ...
* Đóng gói các dự án cơ sở thành khuôn mẫu (templates)
* Mỗi một khuôn mẫu đều có `Dockerfile` và `docker-compose`
* Tích hợp với các dự án, module khác mà không gây ra xung đột


## Server side

Với mục tiêu là dễ dàng tạo ra một máy chủ phục vụ một ứng dụng Web, ta có thể khởi chạy ngay mà không phải cấu hình thêm bất cứ gì bằng một trong hai cách sau:

(1) hoặc:

```bash
# tại thư mục của dự án
kites fly
```

(2) hoặc:

```bash
# tại thư mục của dự án
docker-compose build
docker-compose up
```

## Templates - Các khuôn mẫu dự án


* [x] **`basic`**: Template for building from scratch (**default**, current)
* [x] **`apidoc`**: Template for API Documentation, [nodevn/kites-apidoc](https://github.com/nodevn/kites-apidoc)
* [x] `express`: Template for Express Application
* [ ] `restful`: Template for generating a RESTful API Server
* [ ] `framework`: Assembling all into complete ship (default, next stage), [document](https://kites.nodejs.vn/documentation)
* [ ] `spa`: Template for generating a Single Page Application (SPA)
* [ ] `cms`: Template for generating a Content Management System (CMS)
* [ ] `chat`: Template for generating a Chat application
* [x] `chatbot`: Template for generating an AI Chatbot application, [vntk/chatbot](https://github.com/vntk/chatbot), [document](https://github.com/vntk/chatbot)
* [ ] `videocall`: Template for generating a Video Call application

