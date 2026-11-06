# Quyền riêng tư và dữ liệu cục bộ

[Trang chủ](../../README.vi.md) · [Cài đặt](installation.md) · [Tính năng](features.md) · [Câu hỏi thường gặp](faq.md)

## Hoạt động cục bộ

AntiBotPCExplorer thu thập và phân tích dữ liệu trên chính máy tính đang chạy ứng dụng. Giao diện được nhúng trong tệp thực thi. Quá trình quét, so sánh, kiểm tra chữ ký và xuất báo cáo không gửi yêu cầu mạng. Giao diện WebView2 nhúng chặn điều hướng tới các trang khác; các chức năng kết nối mạng nền và tải báo cáo sự cố lên mạng được tắt. Hai nút website sản phẩm mở [anti.bot](https://anti.bot) hoặc [detect.expert](https://detect.expert) trong trình duyệt mặc định.

Quá trình quét chạy ở chế độ người dùng, không có trình điều khiển nhân hệ điều hành. Việc thu thập thông thường đọc dữ liệu hiện có. Các thao tác khóa TPM tùy chọn, tệp báo cáo xuất ra và dữ liệu cục bộ của ứng dụng được mô tả bên dưới.

## Giá trị trên màn hình

Giao diện ẩn các trường được đánh dấu nhạy cảm cho đến khi bạn chọn và xác nhận **Show identifiers**. Những trường này gồm số sê-ri, UUID phần cứng, địa chỉ MAC, dấu vân tay khóa cùng một số thông tin cá nhân hoặc mạng. Trang Raw JSON tuân theo cùng cài đặt này.

Bối cảnh hệ thống, tên model, trạng thái bảo mật, kết quả chẩn đoán và các trường không được đánh dấu nhạy cảm vẫn hiển thị. Hiện giá trị trên màn hình không làm thay đổi chế độ xuất.

## Định dạng báo cáo

| Kiểu xuất | Nội dung |
| --- | --- |
| Báo cáo bảo vệ quyền riêng tư | Các trường nhạy cảm được thay bằng thẻ HMAC-SHA256; bỏ qua các bảng không thuộc phạm vi xuất an toàn |
| Báo cáo chẩn đoán thô | Giá trị gốc đã thu thập, bao gồm mã định danh nhạy cảm |

Định dạng bảo vệ quyền riêng tư giữ lại bối cảnh chẩn đoán hữu ích và cho phép so sánh thông qua các thẻ nhất quán. Định dạng này chứa thông tin hệ thống và mã định danh không được đánh dấu nhạy cảm. Báo cáo chỉ được lưu khi bạn chọn thao tác xuất hoặc cung cấp đường dẫn đầu ra qua dòng lệnh.

Khóa HMAC được tạo cục bộ. Hai báo cáo dùng cùng khóa có thể so sánh các giá trị được bảo vệ. Khi báo cáo dùng các khóa khác nhau, công cụ so sánh đánh dấu những giá trị này là không thể so sánh.

## Các tệp được lưu

Thư mục dữ liệu cục bộ mặc định là:

```text
%LOCALAPPDATA%\AntiBotPCExplorer
```

Nếu thư mục đó không khả dụng, ứng dụng sử dụng `%TEMP%\AntiBotPCExplorer`.

| Tệp hoặc thư mục | Mục đích |
| --- | --- |
| `hmac.key` | Khóa cục bộ dùng để tạo thẻ ổn định cho các giá trị nhạy cảm trong báo cáo |
| `language.txt` | Ngôn ngữ giao diện đã lưu |
| `WebView2\` | Hồ sơ trình duyệt của giao diện nhúng |

Báo cáo JSON được ghi vào đường dẫn bạn chọn trong hộp thoại Save hoặc cung cấp qua dòng lệnh. Các tệp này nằm riêng với thư mục lưu thiết lập.

Để đặt lại dữ liệu cục bộ của ứng dụng, hãy đóng chương trình và xóa thư mục dữ liệu. Thao tác này đặt lại ngôn ngữ và khóa HMAC. Các giá trị được bảo vệ trong báo cáo xuất trước và sau khi đặt lại sẽ không còn đối chiếu được qua thẻ. Nếu không đọc được tệp khóa hiện có, ứng dụng giữ nguyên tệp đó và dùng khóa tạm thời cho phiên hiện tại.

## Khóa TPM tùy chọn

Trang TPM chỉ tạo khóa minh họa không thể xuất `AntiBotPCExplorer-DeviceKey` khi bạn chọn thao tác tạo. **Delete key** xóa khóa này. Xóa tệp thực thi hoặc thư mục dữ liệu cục bộ không xóa khóa TPM đó.

Lệnh `--selftest` dùng một khóa tạm thời riêng, ký và xác minh một thử thách, rồi xóa khóa thử nghiệm khi hoàn tất.

## Dữ liệu không được thu thập

Công cụ không đọc khóa sản phẩm Windows, dữ liệu BitLocker, vùng chứa khóa Windows Hello, thông tin ủy quyền chủ sở hữu TPM hoặc mã định danh thuê bao di động như IMSI và ICCID. Thông tin giấy phép Windows chỉ gồm trạng thái mô tả và mã định danh, không có khóa sản phẩm. Phần kiểm tra OneDrive đọc các mã định danh thiết bị liên quan thay vì nội dung tài khoản.

## Phản hồi và báo cáo bảo mật

Đối với lỗi ứng dụng có thể tái hiện, làm theo [CONTRIBUTING.vi.md](../../CONTRIBUTING.vi.md). Để báo cáo lỗ hổng, làm theo [SECURITY.vi.md](../../SECURITY.vi.md).
