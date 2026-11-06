# Cài đặt và chạy lần đầu

[Trang chủ](../../README.vi.md) · [Tính năng](features.md) · [Câu hỏi thường gặp](faq.md) · [Quyền riêng tư và dữ liệu cục bộ](privacy.md)

## Yêu cầu

| Thành phần | Yêu cầu |
| --- | --- |
| Hệ điều hành | Windows 10 hoặc Windows 11, x64 64 bit |
| Ứng dụng | Một tệp thực thi chạy trực tiếp; không cần trình cài đặt hay .NET |
| Giao diện đồ họa | Microsoft Edge WebView2 Runtime |
| Quyền truy cập | Tài khoản người dùng thông thường để kiểm tra cơ bản; có thể nâng quyền để đọc thêm nguồn dữ liệu |

Giao diện và cả chín bản dịch giao diện đều được nhúng trong tệp thực thi. WebView2 Runtime có sẵn trên Windows 11. Nếu giao diện thông báo không thể khởi động WebView2, hãy cài Evergreen Runtime x64 từ [trang tải WebView2 của Microsoft](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) rồi mở lại ứng dụng.

## Tải xuống và chạy

1. Mở [bản phát hành mới nhất](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest).
2. Tải `AntiBotPCExplorer-1.4.0-x64.exe` trong mục **Assets** và lưu vào thư mục bạn chọn.
3. Nhấp đúp vào tệp thực thi. Quá trình thu thập bắt đầu tự động và trang Overview xuất hiện khi quét xong.
4. Dùng thanh bên để khám phá phần cứng, mã định danh hệ thống, bảo mật nền tảng, trình điều khiển và khả năng phát hiện máy ảo.

[Tải tệp thực thi](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest/download/AntiBotPCExplorer-1.4.0-x64.exe) · [Tất cả bản phát hành](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases)

Ứng dụng thu thập dữ liệu ngay trên máy. Bạn không cần tài khoản sản phẩm hoặc kết nối Internet để quét.

## Xác minh tệp tải xuống

Tải tệp tổng kiểm SHA-256 của bản phát hành cùng với tệp thực thi. Trong PowerShell, tính giá trị băm của tệp đã tải:

```powershell
Get-FileHash .\AntiBotPCExplorer-1.4.0-x64.exe -Algorithm SHA256
```

So sánh kết quả với dòng ghi cho cùng tệp đó trong tệp tổng kiểm.

Tệp thực thi được ký số bởi **Vektor T13 Technologies B.V.** Để kiểm tra chữ ký bằng PowerShell:

```powershell
Get-AuthenticodeSignature .\AntiBotPCExplorer-1.4.0-x64.exe | Format-List Status,SignerCertificate
```

Windows cần hiển thị trạng thái `Valid`. Bạn cũng có thể mở thẻ **Properties → Digital Signatures** của tệp.

## Sử dụng giao diện

| Thao tác | Cách thực hiện |
| --- | --- |
| Đổi ngôn ngữ giao diện | Nút lá cờ trên thanh công cụ phía trên hoặc trang About |
| Tìm kiếm trong trang hiện tại | `Ctrl+F`; tìm theo nhãn tiếng Anh và bản dịch của nhãn |
| Thu thập ảnh chụp trạng thái mới | `F5` |
| Hiện mã định danh nhạy cảm | **Show identifiers**, sau đó xác nhận |
| Lưu báo cáo | **Export** → **Privacy-safe report** hoặc **Raw diagnostic report** |
| Đọc thêm nguồn dữ liệu được bảo vệ | **Restart as administrator** trong ứng dụng |

Menu ngôn ngữ có tiếng Anh, Nga, Việt, Trung giản thể, Trung phồn thể, Tây Ban Nha, Bồ Đào Nha (Brazil), Pháp và Đức. Lần khởi chạy đầu tiên sử dụng cài đặt ngôn ngữ của Windows; những lần sau ghi nhớ lựa chọn của bạn.

Nâng quyền cho phép truy cập các nguồn như biến UEFI Secure Boot, cấu hình khởi động, ATA Identify, giá trị băm phần cứng Autopilot và lịch sử mạng đã biết. Những phần khác vẫn hoạt động khi không đọc được một nguồn được bảo vệ; dòng tương ứng sẽ hiển thị lý do.

## Xuất báo cáo mà không mở cửa sổ

Các lệnh này sử dụng bộ thu thập gốc và không cần WebView2. Do tệp thực thi là ứng dụng GUI, `Start-Process -Wait` giúp PowerShell đợi cho đến khi báo cáo được ghi xong.

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export','report.json' -Wait -NoNewWindow
```

Để xuất báo cáo thô chứa các giá trị mã định danh gốc:

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export-raw','raw.json' -Wait -NoNewWindow
```

Đường dẫn đầu ra được tính tương đối từ thư mục làm việc của tiến trình, trừ khi bạn cung cấp đường dẫn tuyệt đối. Hãy chọn vị trí có quyền ghi. Nếu đường dẫn có dấu cách, đặt đường dẫn trong dấu ngoặc kép bên trong chuỗi đối số:

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export "C:\Reports Folder\report.json"' -Wait -NoNewWindow
```

Mở giao diện bằng ngôn ngữ đã chọn:

```powershell
.\AntiBotPCExplorer-1.4.0-x64.exe --lang zh-Hant
```

Các mã ngôn ngữ được hỗ trợ: `en`, `ru`, `vi`, `zh-Hans`, `zh-Hant`, `es`, `pt`, `fr`, `de`.

## Cập nhật hoặc gỡ bỏ

Để cập nhật, đóng ứng dụng và tải tệp thực thi mới từ Releases. Cài đặt cục bộ được lưu riêng với tệp thực thi, nên việc thay chương trình vẫn giữ nguyên ngôn ngữ đã chọn và khóa dùng để so sánh các mã định danh được bảo vệ.

Để gỡ chương trình, xóa tệp thực thi. Nếu muốn xóa cả cài đặt cục bộ và hồ sơ WebView2, hãy đóng chương trình rồi xóa `%LOCALAPPDATA%\AntiBotPCExplorer`. Thao tác này cũng đặt lại khóa so sánh báo cáo. Các báo cáo được xuất trước và sau khi đặt lại sẽ không thể đối chiếu các mã định danh được bảo vệ bằng HMAC. Xem [Quyền riêng tư và dữ liệu cục bộ](privacy.md) để biết danh sách đầy đủ các tệp được lưu cùng thông tin về khóa TPM minh họa tùy chọn.
