# Portfolio CV - Nguyễn Ngọc Hải

Trang portfolio/CV cá nhân giới thiệu Nguyễn Ngọc Hải, các kỹ năng Frontend, một số dự án đã thực hiện và thông tin liên hệ. Giao diện được xây dựng theo hướng responsive, ưu tiên trải nghiệm trên điện thoại và mở rộng bố cục cho máy tính bảng, máy tính để bàn.

> README này nằm trong thư mục `assets/`. Các lệnh chạy bên dưới cần được thực hiện tại thư mục gốc dự án — thư mục chứa `index.html` — không phải trong `assets/`.

## Chức năng

- Giới thiệu cá nhân và định hướng Frontend Developer.
- Hiển thị các kỹ năng và công nghệ.
- Trình bày các dự án tiêu biểu dưới dạng thẻ có hình ảnh và mô tả.
- Cung cấp thông tin liên hệ.
- Điều hướng đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Hỗ trợ bố cục responsive, cuộn mượt và trạng thái focus cho điều hướng bằng bàn phím.

## Công nghệ sử dụng

- **HTML5**: cấu trúc nội dung và các vùng ngữ nghĩa.
- **CSS3**: giao diện, biến CSS, Flexbox, CSS Grid, media queries và responsive design.
- **JavaScript**: hiện chưa được sử dụng để vận hành trang; JavaScript (ES6+) chỉ được liệt kê trong phần kỹ năng trên CV.
- **Docker/Nginx**: tùy chọn để phục vụ trang tĩnh trong container.

## Cấu trúc dự án

```text
.
├── index.html
└── assets/
    ├── README.MD
    ├── css/
    │   └── styles.css
    └── img/
        └── các hình ảnh được sử dụng trên trang
```

## Yêu cầu môi trường

### Chạy trực tiếp hoặc bằng máy chủ cục bộ

- Windows, macOS hoặc Linux.
- Trình duyệt hiện đại như Chrome, Edge, Firefox hoặc Safari.
- Không cần cài Node.js, npm, cơ sở dữ liệu hay công cụ build.
- Có thể mở `index.html` trực tiếp; khuyến nghị dùng máy chủ HTTP cục bộ để kiểm tra các đường dẫn tài nguyên.
- Để chạy máy chủ cục bộ, cần Python 3 (hoặc dùng một máy chủ HTTP tĩnh tương đương).

### Chạy bằng Docker

- Docker Engine và Docker CLI.
- Trên Windows/macOS, cần Docker Desktop đang hoạt động.
- Máy cần trống cổng `8080`, hoặc đổi cổng phía máy chủ trong lệnh chạy.

## Cài đặt

1. Tải mã nguồn hoặc clone repository về máy.

   ```bash
   git clone https://github.com/nguyenvanhuynh15091977-a11y/CV.git
   ```

2. Đi vào thư mục gốc vừa tải/clone, nơi có file `index.html`.

   ```bash
   cd CV
   ```

3. Không cần cài thêm thư viện hay chạy lệnh build. Nếu mở trực tiếp, hãy mở file `index.html` bằng trình duyệt.

## Cấu hình

Dự án hiện là website tĩnh và không cần file cấu hình môi trường, API key hay thông tin bí mật.

- **Nội dung trang**: chỉnh sửa `index.html`.
- **Màu sắc, kiểu chữ và bố cục**: chỉnh sửa `assets/css/styles.css`.
- **Ảnh**: đặt ảnh trong `assets/img/` và cập nhật đường dẫn `src` tương ứng trong `index.html`.
- **Thông tin liên hệ**: cập nhật email, số điện thoại và địa chỉ hồ sơ trong phần Liên hệ của `index.html`. Trước khi xuất bản, nên kiểm tra các thuộc tính `href` của GitHub và LinkedIn để chúng trỏ đến hồ sơ thật.
- **Cổng máy chủ cục bộ**: có thể đổi `8000` trong lệnh chạy bên dưới.
- **Cổng Docker**: đổi số `8080` ở phía trái của `-p` nếu cổng này đang được sử dụng.

## Chạy thử

### Windows

Mở PowerShell tại thư mục gốc dự án và chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có trên máy, thử:

```powershell
python -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000) trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### macOS

Mở Terminal tại thư mục gốc dự án:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000) trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### Linux

Mở Terminal tại thư mục gốc dự án:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000) trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### Mở trực tiếp

Trên cả Windows, macOS và Linux, có thể mở file `index.html` bằng trình duyệt. Cách này không cần cài Python, nhưng máy chủ HTTP cục bộ thường thuận tiện hơn khi kiểm tra website.

## Chạy bằng Docker

Không cần tạo Dockerfile: image `nginx:alpine` sẽ phục vụ các file tĩnh từ thư mục dự án.

### Windows (PowerShell)

Mở PowerShell tại thư mục gốc dự án. Đảm bảo Docker Desktop đang chạy, sau đó thực hiện:

```powershell
docker run --rm --name portfolio-cv -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

### macOS và Linux

Mở Terminal tại thư mục gốc dự án và chạy:

```bash
docker run --rm --name portfolio-cv -p 8080:80 -v "$(pwd):/usr/share/nginx/html:ro" nginx:alpine
```

Sau khi container khởi động, mở [http://localhost:8080](http://localhost:8080). Dừng container bằng `Ctrl+C`; tùy chọn `--rm` sẽ tự xóa container sau khi dừng.

Nếu cổng `8080` đang được sử dụng, thay `8080` ở phía trái của `-p` bằng một cổng khác, ví dụ `8081:80`, rồi truy cập cổng tương ứng. Nếu Docker không truy cập được thư mục trên Windows/macOS, hãy kiểm tra quyền chia sẻ thư mục trong Docker Desktop.

## Thông tin liên hệ

Thông tin đang được hiển thị trong trang:

- **Tác giả**: Nguyễn Ngọc Hải
- **Email**: [ngokhai15022008@gmail.com](mailto:ngokhai15022008@gmail.com)
- **GitHub**: `nguyenngochai1502`
- **LinkedIn**: `linkedin.com/in/nguyenngochai1502`
- **Điện thoại**: `0385206623`

Các thông tin này có thể được cập nhật trực tiếp trong phần Liên hệ của `index.html`.