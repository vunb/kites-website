## ApiDoc Template
{: #kites-apidoc-template}

**ApiDoc** hay tài liệu hướng dẫn sử dụng API là một nội dung kỹ thuật có thể phân phối hoặc dùng để tham chiếu, bao gồm những hướng dẫn sử dụng và tích hợp API một cách hiệu quả.

### Tại sao tài liệu API lại quan trọng?

Một vài gạch đầu dòng cho biết `ApiDoc` rất quan trọng:

* **Cải thiện trải nghiệm người dùng**: Nếu bạn có tài liệu hướng dẫn tốt, nhiều người sẽ dễ dàng tìm thấy giá trị trong các dịch vụ của bạn, dẫn tới sự hợp tác và tăng trưởng.
* **Giúp nhiều người biết đến API của bạn**: Kites cũng muốn được mọi người biết đến nhiều hơn và bạn đang đọc tài liệu về `kites` :smile:
* **Tiết kiệm thời gian hỗ trợ và chi phí**: Tài liệu tốt giúp giảm thời gian hỗ trợ người dùng mới, thành viên mới của team hoặc của đối tác
* **Dễ bảo trì**: Apidoc giúp team của bạn biết cụ thể và chi tiết tài nguyên, phương thức, api, .. giúp bạn biết làm thế nào để cải tiến và năng hiệu suất cho hệ thống và sản phẩm.


Tài liệu hướng dẫn sử dụng API thường được khởi tạo ([1](#kites-init-apidoc-1)) và bảo trì ([2](#kites-init-apidoc-2)) bằng cách soạn thảo văn bản thông thường hoặc theo chuẩn mở [OpenAPI/Swagger Sepecification](https://swagger.io/specification/), sau đó bạn hoàn toàn có thể đưa lên Web Online ([3](#kites-init-apidoc-3)). Trong phạm vi của kites framework thì kites sẽ hỗ trợ bạn tạo ra một trang tài liệu tĩnh được dùng để mô tả và hướng dẫn lập trình tích hợp với API của bạn hiệu quả như trang [demo này](https://kites.nodejs.vn/docs).

* Truy cập demo: [https://kites.nodejs.vn/docs](https://kites.nodejs.vn/docs)
* Một trang khác: [https://docs.yeu.ai/](https://docs.yeu.ai/)
* Trang của bạn sẽ sử dụng **kites** chứ ?


### Cách tạo ApiDoc với kites như thế nào?
{: #kites-init-apidoc}

<section markdown="1">

#### #1. Khởi tạo dự án của bạn
{: #kites-init-apidoc-1 .code}

Sau khi cài đặt [@kites/cli](https://www.npmjs.com/package/@kites/cli) thì bạn có thể khởi tạo dự án của mình bằng các lệnh sau:

```bash
# khởi tạo dự án
kites init my-project --template apidoc

# di chuyển vào thư mục dự án
cd my-project

# cài đặt các phụ thuộc và công cụ build
npm install

# build trang tài liệu mà bạn đã viết bằng markdown
npm run build

# chạy lệnh sau đây để xem thành quả tại http://localhost:3000
npm start
```

#### #2. Phát triển và bảo trì dự án ApiDoc
{: #kites-init-apidoc-2 .code}

Rõ ràng tài liệu của bạn sẽ thay đổi khi có cập nhật và nâng cấp. Theo đó, thì bạn cũng cần cập nhật nội dung tài liệu ApiDoc của mình trong thư mục `source/includes`. Để nhìn thấy kết quả luôn trong quá trình sửa đổi tài liệu, chạy lệnh:

```bash
# chạy ở chế độ phát triển tài liệu
npm run dev
```

Chú ý: Nếu cần thiết thay đổi thứ tự xuất hiện của tài liệu, hãy sửa đổi nội dung file `index.yml`, mục `includes` như hình sau đây.

![apidoc](/images/kites/templates/apidoc.png)

</section>

#### #3. Đưa tài liệu lên Web Online
{: #kites-init-apidoc-3 .code}

Sau khi tài liệu đã được build bạn hoàn toàn có thể đưa trang tài liệu của mình lên Web Online, bằng 1 trong 3 phương án sau đây.

**Phương án 1**: Bạn có vps hoặc máy chủ riêng, bạn chỉ cần up code và chạy lệnh

```bash
# tại thư mục của dự án
npm start
```

**Phương án 2**: Đưa lên heroku

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

**Phương án 3**: Đưa lên Github Pages

Bạn hãy dùng `git` để đưa trang tài liệu của mình lên Github, ý tưởng là bạn có thể lưu trang tài liệu của trên nhánh `gh-pages` hoặc sử dụng thư mục `docs` trên nhánh master.

Để cho đơn giản mình chọn thư mục `docs` trên nhánh master, các bạn có thể thao tác với `git` bằng các lệnh sau đây.

```bash
# tại thư mục của dự án
git init
git remote add origin git@github.com:your-user-name/your-kites-apidoc.git

# build lại dự án trước khi publish
npm run build

# add toàn bộ source code
git add .
git commit -m "init api document"

# add tài liệu đã được build ra
git add -f docs/*
git commit -m "update document"

git push origin master
```

* Thêm: Bạn có thể cấu hình domain cho trang tài liệu của mình bằng hướng dẫn [Using a custom domain with GitHub Pages](https://help.github.com/articles/using-a-custom-domain-with-github-pages/)

