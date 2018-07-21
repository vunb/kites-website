## MVC Template
{: #kites-mvc-template}

**Kites MVC** là template dựng sẵn tuân thủ theo mẫu kiến trúc phần mềm **[Model - View - Controller (MVC)](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)**. Điều này có nghĩa là việc sử dụng Kites MVC sẽ giúp bạn có thể tạo ra được các ứng dụng trở nên đơn giản hơn đối với các dự án có nhiều nghiệp vụ phức tạp.

### Kiến trúc mô hình MVC

![mvc model](/images/kites/templates/mvc3.jpg)

**MVC** là một kiến trúc phần mềm hay mô hình thiết kế được sử dụng trong kỹ thuật phần mềm. Thực chất, mô hình này sẽ phân bố source code thành 3 phần, mỗi thành phần có một nhiệm vụ riêng biệt và độc lập với các thành phần khác (như hình).

* **Controller** - Có nhiệm vụ điều hướng các yêu cầu từ người dùng tới các phương thức xử lý phù hợp.
* **Model** - Đây là thành phần chứa tất cả các nghiệp vụ logic, phương thức (hàm) xử lý, truy xuất database, mô tả đối tượng dữ liệu, ... 
* **View** - Đảm nhận việc hiển thị thông tin, tương tác với người dùng, nơi chứa tất cả các đối tượng GUI như textbox, images, ...

Khi có một yêu cầu từ phía client gửi đến server, bộ phận `controller` có nhiệm vụ nhận yêu cầu, xử lý yêu cầu đó. Và nếu cần, nó sẽ gọi đến phần `model`, vốn là bộ phần làm việc với Database. Sau khi xử lý xong, toàn bộ kết quả được đẩy về phần `View`. Tại `View`, sẽ biên dịch ra mã Html tạo nên giao diện, và trả toàn bộ html về trình duyệt để hiển thị.

#### Kites Service

Kites bổ sung thêm tầng **Service** nằm bên dưới kiến trúc MVC, nhằm mục đích tạo ra các nghiệp vụ logic nhiều bước quy trình, thực hiện các tác vụ của ứng dụng, nơi trung chuyển dữ liệu dữ các hệ thống và (hoặc) truy xuất tới các đối tượng dữ liệu từ nhiều nguồn khác nhau, như: Database, File, Web service, Network, Sub system ... 

Từ trên xuống dưới thì kiến trúc của Kites-MVC được thể hiện theo thứ tự như sau:

1. MVC Layer
2. Service Layer (*)
3. Data Access Objects Layer - Truy xuất tới cơ sở dữ liệu hoặc tới các hệ thống khác như LDAP, Web Service, ...

### Xây dựng một ứng dụng Kites MVC?
{: #kites-init-mvc}

<section markdown="1">

#### #1. Khởi tạo dự án của bạn
{: #kites-init-mvc-1 .code}

Sau khi cài đặt [@kites/cli](https://www.npmjs.com/package/@kites/cli) thì bạn có thể khởi tạo dự án của mình bằng các lệnh sau:

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

#### #2. Phát triển và bảo trì dự án MVC
{: #kites-init-mvc-2 .code}

```bash
# chạy ở chế độ phát triển
npm run dev
```

Bố cục của dự án được tổ chức như hình sau đây.

![kites mvc](/images/kites/templates/mvc2.PNG)

</section>

#### #3. Thiết lập cấu hình
{: #kites-init-mvc-2 .code}

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

