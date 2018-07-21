---
title : Getting Started
---

# Guide

## Hướng dẫn khởi tạo 1 dự án Kites

Sau đây là hướng dẫn khởi tạo một dự án kites với bộ mẫu dựng sẵn: `mvc`

### #1. Cài đặt Kites cli

Trước hết bạn cần cài đặt kites cli để có được công cụ gõ trên cửa sổ dòng lệnh:

```bash
npm install -g @kites/cli
```

### #2. Khởi tạo dự án

Sau đó, bạn có thể khởi tạo dự án của mình bằng các lệnh sau:

```bash
# khởi tạo dự án
kites init my-project --template mvc

# di chuyển vào thư mục dự án
cd my-project

# cài đặt các phụ thuộc và công cụ build
npm install

# chạy lệnh sau đây để xem thành quả tại http://localhost:3000
npm start
```

### #3. Phát triển dự án

```bash
# chạy ở chế độ phát triển
npm run dev
```

Bố cục của dự án được tổ chức như hình sau đây.

![kites mvc](/images/kites/templates/mvc2.PNG)

### #4. Thiết lập cấu hình

Lưu ý: Thiết lập cấu hình kết nối cho kites trong file `kites.config.json`

Dưới đây là nội dung các cấu hình được thiết lập mặc định, bạn hoàn toàn có thể thay đổi nó cho dự án của mình.

```json
{
    "extensionsLocationCache": true,
    "logger": {
        "console": {
            "transport": "console",
            "level": "info"
        }
    },
    "extensions": null,
    "kites-api": {
        "connection": "memory",
        "dataSource": [{
            "name": "memory",
            "driver": "memory",
            "active": true
        }, {
            "name": "mysql",
            "driver": "mysql",
            "host": "localhost",
            "port": "3306",
            "username": "root",
            "password": "",
            "database": "test",
            "active": false,
            "pool": true
        }]
    },
    "express": {
        "static": "./public",
        "httpPort": 3000,
        "poweredBy": "Kites",
        "views": {
            "engine": "ejs",
            "path": "content/views"
        }
    }
}
```

## Các bản mẫu dựng sẵn

Xem chi tiết hướng dẫn cài đặt sử dụng các bản mẫu khác, [tại đây](/documentation/kites/templates).

