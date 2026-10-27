# Báo cáo đánh giá chất lượng dự án

**Dự án:** Portfolio CV - Nguyễn Ngọc Hải  
**Ngày đánh giá:** 27/10/2026  
**Phạm vi:** Đánh giá phiên bản mã nguồn hiện có, tập trung vào sáu tiêu chí theo yêu cầu. Đây là website tĩnh gồm `index.html`, CSS và ảnh; không có backend hay bộ kiểm thử tự động trong repository.

## Tóm tắt kết quả

| Tiêu chí | Đánh giá | Kết luận |
|---|---|---|
| Tính đúng đắn | Đạt một phần | Các phần chính hiển thị, ảnh tải thành công, điều hướng neo hoạt động; còn liên kết giữ chỗ và sai khác thông tin. |
| UI/UX | Đạt một phần | Có bố cục responsive và không tràn ngang trong các kích thước đã kiểm tra; một số chi tiết tiếp cận và liên hệ cần hoàn thiện. |
| Khả năng vận hành - xử lý lỗi | Đạt một phần | Có thể mở trực tiếp bằng trình duyệt; chưa có cơ chế xử lý lỗi hoặc kiểm thử tự động. |
| Bảo mật | Chưa đủ cơ sở xác nhận | Website tĩnh, không xử lý dữ liệu đầu vào; chưa kiểm tra cấu hình bảo mật khi triển khai lên máy chủ. |
| Chất lượng mã nguồn | Đạt một phần | Có tách HTML/CSS và dùng cấu trúc ngữ nghĩa; còn markup liên hệ không hợp lệ và chưa có lint/validator. |
| Khả năng triển khai | Đạt một phần | Có hướng dẫn chạy cục bộ và Docker trong README; chưa chạy thử container hoặc cấu hình pipeline/hosting. |

## 1. Tính đúng đắn

**Kết quả: Đạt một phần**

- Trang mở được trong trình duyệt, có tiêu đề và hiển thị bốn phần chính: Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Trong lần kiểm tra trên trình duyệt, cả 5 ảnh được tham chiếu trong trang đều tải thành công.
- Thử chọn mục điều hướng “Dự án” đưa địa chỉ trang tới `#projects`.
- Phát hiện các liên kết “Xem chi tiết” và một số liên kết thông tin liên hệ vẫn dùng `href="#"`, nên chưa dẫn tới đích thực tế.
- Thông tin mô tả trong thẻ meta (`Nguyễn Văn An`) không khớp tên hiển thị trên trang (`Nguyễn Ngọc Hải`).

**Minh chứng:** [Ảnh giao diện desktop](docs/screenshots/portfolio-desktop.png), [ảnh giao diện mobile](docs/screenshots/portfolio-mobile.png); các mục và liên kết tương ứng nằm trong `index.html`.

## 2. UI/UX

**Kết quả: Đạt một phần**

- CSS áp dụng cách tiếp cận mobile-first, Flexbox và CSS Grid; lưới dự án có một cột ở màn hình hẹp và ba cột ở màn hình rộng đã kiểm tra.
- Không phát hiện cuộn ngang tại hai kích thước kiểm tra trên trình duyệt.
- Có thanh điều hướng cố định, trạng thái focus nhìn thấy được và hỗ trợ giảm chuyển động qua `prefers-reduced-motion`.
- Một số ảnh có nội dung `alt` mô tả chung, chưa phản ánh chính xác dự án.
- Cấu trúc phần liên hệ bị ảnh hưởng bởi markup không hợp lệ ở dòng GitHub, có thể làm nhãn/liên kết hiển thị hoặc được đọc không như mong muốn bằng công nghệ hỗ trợ.
- Chưa thực hiện đánh giá khả năng tiếp cận đầy đủ, kiểm tra tương phản tự động hoặc thử nghiệm người dùng.

**Minh chứng:** Hai ảnh chụp desktop/mobile ở thư mục `docs/screenshots/`; quy tắc responsive và focus nằm trong `assets/css/styles.css`.

## 3. Khả năng vận hành - xử lý lỗi

**Kết quả: Đạt một phần**

- Trang có thể mở trực tiếp bằng trình duyệt. Trong lần chạy kiểm tra, các hình ảnh được tải và điều hướng neo trong trang hoạt động.
- Theo cấu trúc mã nguồn hiện tại, đây là trang tĩnh, không có JavaScript nghiệp vụ, gửi biểu mẫu, API hay cơ sở dữ liệu để kiểm tra xử lý lỗi phía ứng dụng.
- Không có kiểm thử tự động hoặc kiểm tra lỗi khi tài nguyên bị thiếu; chưa xác minh hành vi trên nhiều trình duyệt/hệ điều hành.
- Các liên kết giữ chỗ `#` là hạn chế vận hành cần giải quyết trước khi dùng như CV/portfolio công khai.

**Minh chứng:** Kết quả kiểm tra trực tiếp bằng trình duyệt và ảnh giao diện trong `docs/screenshots/`; hướng dẫn chạy thử nằm trong `README.MD`.

## 4. Bảo mật

**Kết quả: Chưa đủ cơ sở xác nhận**

- Phạm vi mã nguồn đang xem là website tĩnh; không thấy biểu mẫu nhận dữ liệu, xử lý đăng nhập, API hoặc thư viện JavaScript bên thứ ba. Vì vậy, bề mặt rủi ro phía ứng dụng nhỏ hơn một website có backend.
- Không thể kết luận website an toàn chỉ từ việc không có backend. Chưa thực hiện quét bảo mật, rà soát cấu hình máy chủ, kiểm tra header bảo mật, HTTPS/TLS hoặc chính sách lưu trữ/triển khai.
- Khi đưa lên máy chủ, cần dùng HTTPS và cấu hình các header phù hợp (ví dụ CSP, `X-Content-Type-Options` và chính sách `Referrer-Policy`) ở nền tảng phục vụ nội dung.
- Không đưa thông tin bí mật hoặc dữ liệu cá nhân không cần thiết vào mã nguồn công khai.

**Minh chứng:** Rà soát mã nguồn `index.html` và `assets/css/styles.css`. Đây là rà soát phạm vi hẹp, không thay thế kiểm thử bảo mật chuyên sâu.

## 5. Chất lượng mã nguồn

**Kết quả: Đạt một phần**

- HTML và CSS được tách thành các file riêng; trang dùng các vùng HTML ngữ nghĩa, CSS custom properties, Flexbox, Grid và media queries.
- Có khai báo ngôn ngữ trang, viewport, mô tả meta, nhãn điều hướng và văn bản thay thế cho ảnh.
- Dòng GitHub trong phần liên hệ tại `index.html` có markup chưa đóng/không hợp lệ (`<a>` lồng với phần tử `<github>`), cần sửa để cấu trúc tài liệu và cây trợ năng nhất quán.
- Chưa chạy HTML validator, CSS linter hoặc bộ kiểm thử; do đó báo cáo không xác nhận mã nguồn đạt chuẩn kiểm tra tự động.

**Minh chứng:** `index.html`, `assets/css/styles.css`; ghi nhận markup liên hệ tại dòng GitHub trong `index.html`.

## 6. Khả năng triển khai

**Kết quả: Đạt một phần**

- Do là trang tĩnh, không cần cài dependencies hoặc chạy bước build để phục vụ nội dung.
- `README.MD` có hướng dẫn chạy cục bộ trên Windows, macOS, Linux và dùng Docker với Nginx.
- Đã kiểm tra trang mở trực tiếp trong trình duyệt; chưa chạy xác minh các lệnh máy chủ Python/Docker trên từng hệ điều hành hoặc thực sự build/chạy container.
- Repository chưa có Dockerfile, cấu hình hosting, tên miền/HTTPS hay pipeline CI/CD. Hướng dẫn Docker hiện dùng image Nginx trực tiếp để phục vụ thư mục dự án.

**Minh chứng:** Hướng dẫn triển khai trong `README.MD`; ảnh chụp được lưu tại `docs/screenshots/`.

## Ảnh minh chứng

- [Giao diện desktop](docs/screenshots/portfolio-desktop.png)
- [Giao diện mobile](docs/screenshots/portfolio-mobile.png)

Ảnh được chụp trực tiếp từ trang đang mở bằng trình duyệt và lưu trong repository. Kết quả trên phản ánh lần kiểm tra ngày 27/10/2026, không phải chứng nhận kiểm thử toàn diện.

## Đề xuất ưu tiên

1. Sửa markup phần GitHub trong `index.html` và cập nhật các liên kết `href="#"` thành URL thật hoặc nội dung phù hợp.
2. Đồng bộ tên trong metadata, văn bản thay thế ảnh và nội dung hiển thị.
3. Chạy HTML validator và kiểm tra điều hướng, bố cục responsive trên các trình duyệt/kích thước màn hình mục tiêu.
4. Trước khi phát hành công khai, kiểm tra Docker/hosting thực tế, HTTPS và header bảo mật của máy chủ.