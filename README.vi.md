<p align="center">
  <a href="README.md">🇬🇧 English</a> · <a href="README.ru.md">🇷🇺 Русский</a> · <a href="README.vi.md">🇻🇳 Tiếng Việt</a> · <a href="README.zh-Hant.md">🇹🇼 繁體中文</a>
</p>

<p align="center">
  <img src="assets/logo/app-icon.png" width="104" height="104" alt="Logo AntiBotPCExplorer">
</p>
<h1 align="center">AntiBotPCExplorer - VM Detection and Hardware Fingerprinting</h1>
<p align="center"><strong>Hiểu rõ phần cứng. Nắm rõ danh tính thiết bị.</strong><br>Kiểm tra dấu vân tay thiết bị, bảo mật nền tảng và môi trường ảo hóa trên Windows.<br>do <strong>Vektor T13</strong> phát triển</p>
<p align="center"><a href="https://detect.expert">detect.expert</a> · <a href="https://anti.bot">anti.bot</a> · <a href="https://antidetect.com">antidetect.com</a></p>

<p align="center">
  <a href="https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest"><img alt="Bản phát hành mới nhất" src="https://img.shields.io/github/v/release/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting?style=flat-square&amp;color=528cff"></a>
  <a href="https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases"><img alt="Lượt tải bản phát hành" src="https://img.shields.io/github/downloads/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/total?style=flat-square&amp;color=22bfa4"></a>
  <img alt="Windows 10 và 11 x64" src="https://img.shields.io/badge/Windows-10%20%7C%2011%20%C2%B7%20x64-528cff?style=flat-square">
  <a href="LICENSE"><img alt="Giấy phép độc quyền" src="https://img.shields.io/badge/license-proprietary-6d7890?style=flat-square"></a>
  <img alt="Ứng dụng chạy trực tiếp" src="https://img.shields.io/badge/distribution-portable-22bfa4?style=flat-square">
</p>

<p align="center">
  <a href="https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest/download/AntiBotPCExplorer-1.4.0-x64.exe"><img alt="Tải xuống cho Windows x64" src="https://img.shields.io/badge/Download-Windows%20x64-528cff?style=for-the-badge&amp;logo=github&amp;logoColor=white"></a>
</p>
<p align="center">
  <a href="https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest">Bản phát hành mới nhất</a> · <a href="docs/vi/installation.md">Cài đặt</a> · <a href="docs/vi/features.md">Tính năng</a> · <a href="docs/vi/faq.md">Câu hỏi thường gặp</a> · <a href="https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/issues">Hỗ trợ</a>
</p>

---

AntiBotPCExplorer tập hợp mã định danh phần cứng, thông tin firmware, dữ liệu TPM, danh tính Windows và bảo mật nền tảng trong một ứng dụng kiểm tra trên máy tính. Khám phá các tín hiệu dùng để nhận diện máy tính, xem xét dấu hiệu ảo hóa và so sánh báo cáo trước và sau khi thay đổi hệ thống.

**Một tệp thực thi chạy trực tiếp. Chẩn đoán ngay trên máy. Mã định danh được ẩn theo mặc định.** Ứng dụng được ký số bởi **Vektor T13 Technologies B.V.**

<p align="center">
  <img src="assets/screenshots/overview.png" alt="Trang tổng quan AntiBotPCExplorer 1.4.0 với bốn điểm chẩn đoán và mã định danh được ẩn" width="1200">
</p>

## Bạn có thể làm gì

| Khả năng | Thông tin bạn nhận được |
|---|---|
| <img src="assets/icons/hardware.svg" width="36" height="36" alt=""> **Khám phá danh tính thiết bị** | Hồ sơ CPU và FPU, firmware, thiết bị lưu trữ, bộ điều hợp mạng, màn hình, thiết bị PnP và mã định danh Windows tại cùng một nơi. |
| <img src="assets/icons/platform.svg" width="36" height="36" alt=""> **Kiểm tra độ tin cậy của nền tảng** | Thuộc tính TPM, Secure Boot, VBS/HVCI, dữ liệu khởi động và thông tin chữ ký trình điều khiển nhân hệ điều hành. |
| <img src="assets/icons/compare.svg" width="36" height="36" alt=""> **So sánh ảnh chụp trạng thái hệ thống** | So sánh theo nhóm danh tính, mô phỏng các tình huống thay đổi và xem khác biệt giữa báo cáo theo từng trường, có bộ lọc bỏ qua các trường thường xuyên thay đổi. |
| <img src="assets/icons/offline.svg" width="36" height="36" alt=""> **Giữ hoạt động chẩn đoán trên máy** | Thu thập ngoại tuyến, che mã định danh và xuất báo cáo JSON bảo vệ quyền riêng tư bằng thẻ HMAC. |

### Nhìn nhanh về môi trường ảo hóa

Phiên bản **1.4.0** bổ sung trang **VM Detection** riêng và điểm **Physical PC Confidence**. Xem dữ liệu được nhóm theo nguồn, trạng thái kiểm tra, mức đóng góp vào điểm số và chi tiết kỹ thuật từ CPU, firmware, thiết bị, đồ họa đến các thành phần tích hợp máy ảo khách.

Việc đánh giá tính đến dữ liệu có tương quan và những nguồn không khả dụng. Hyper-V hoặc VBS chạy trên máy Windows vật lý được xử lý riêng với dữ liệu cho thấy hệ thống là máy ảo khách.

<details>
<summary><strong>Xem VM Detection và danh mục mã định danh</strong></summary>

### VM Detection

<img src="assets/screenshots/vm-detection.png" alt="Trang VM Detection trong AntiBotPCExplorer 1.4.0 hiển thị các nhóm kiểm tra và dữ liệu chẩn đoán" width="1200">

### Mã định danh

<img src="assets/screenshots/identifiers.png" alt="Danh mục mã định danh trong AntiBotPCExplorer 1.4.0 với các giá trị nhạy cảm được ẩn" width="1200">

</details>

## Bắt đầu trong một phút

1. [Tải AntiBotPCExplorer 1.4.0 cho Windows x64](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest/download/AntiBotPCExplorer-1.4.0-x64.exe).
2. Lưu tệp `.exe` vào thư mục bạn chọn rồi nhấp đúp để chạy. Không cần trình cài đặt.
3. Nếu cửa sổ thông báo thiếu môi trường chạy, hãy cài [Microsoft Edge WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) rồi khởi chạy lại ứng dụng.
4. Khám phá **Overview**, mở trang chi tiết hoặc xuất báo cáo. Chọn ngôn ngữ giao diện trong menu có biểu tượng lá cờ.

Dùng tài khoản Windows thông thường cho việc kiểm tra hằng ngày. **Run as administrator** cho phép đọc thêm thông tin firmware và hệ thống được bảo vệ.

| Yêu cầu | Cấu hình được hỗ trợ |
|---|---|
| Hệ điều hành | Windows 10 hoặc Windows 11 |
| Kiến trúc | x64 (Intel / AMD 64 bit) |
| Giao diện máy tính | Microsoft Edge WebView2 Runtime |
| Cài đặt | Tệp `.exe` chạy trực tiếp; không cần cài .NET |
| Kết nối Internet | Không cần khi chẩn đoán |

Xem [hướng dẫn cài đặt](docs/vi/installation.md) để biết cách cài môi trường chạy, xác minh SHA-256, cập nhật và sử dụng dòng lệnh.

## Báo cáo phù hợp với quy trình làm việc của bạn

Xuất báo cáo JSON bảo vệ quyền riêng tư mà không mở giao diện máy tính:

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export','report.json' -Wait
```

Mở giao diện bằng một ngôn ngữ cụ thể:

```powershell
.\AntiBotPCExplorer-1.4.0-x64.exe --lang en
```

Giao diện máy tính có **Compare snapshots** và **Report diff**. Các báo cáo được tạo bằng cùng một khóa HMAC cục bộ có thể được so sánh trong khi mã định danh vẫn được che. [Tìm hiểu về báo cáo và dữ liệu cục bộ](docs/vi/privacy.md).

## Công nghệ sử dụng

<p>
  <img alt="C++" src="https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&amp;logo=cplusplus&amp;logoColor=white">
  <img alt="Win32 API" src="https://img.shields.io/badge/Win32-API-528cff?style=flat-square">
  <img alt="Microsoft Edge WebView2" src="https://img.shields.io/badge/Microsoft%20Edge-WebView2-22bfa4?style=flat-square">
  <img alt="HTML5" src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&amp;logo=html5&amp;logoColor=white">
  <img alt="CSS" src="https://img.shields.io/badge/CSS-663399?style=flat-square&amp;logo=css&amp;logoColor=white">
  <img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&amp;logo=javascript&amp;logoColor=black">
</p>

Ứng dụng C++ gốc sử dụng các API Windows và giao diện HTML, CSS, JavaScript nhúng, được hiển thị bằng Microsoft Edge WebView2. Giao diện và các bản dịch đều nằm trong tệp thực thi.

## Ngôn ngữ

**Giao diện ứng dụng — 9 ngôn ngữ:** English, Русский, Tiếng Việt, 简体中文, 繁體中文, Español, Português (Brasil), Français và Deutsch.

**Tài liệu sản phẩm — 4 ngôn ngữ:** [English](README.md), [Русский](README.ru.md), [Tiếng Việt](README.vi.md) và [繁體中文](README.zh-Hant.md). Mỗi bản đều có hướng dẫn cài đặt, tính năng, câu hỏi thường gặp và tài liệu về quyền riêng tư.

## Tài liệu và hỗ trợ

| Nội dung | Liên kết |
|---|---|
| Cài đặt, chạy, cập nhật và xác minh tệp tải xuống | [Cài đặt](docs/vi/installation.md) |
| Khám phá công cụ kiểm tra và xử lý báo cáo | [Hướng dẫn tính năng](docs/vi/features.md) |
| Các câu hỏi thường gặp | [Câu hỏi thường gặp](docs/vi/faq.md) |
| Xuất báo cáo, che mã định danh và dữ liệu cục bộ | [Quyền riêng tư và báo cáo](docs/vi/privacy.md) |
| Lịch sử phiên bản | [Nhật ký thay đổi](CHANGELOG.vi.md) |
| Tệp tải xuống và ghi chú phát hành | [GitHub Releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases) |
| Báo lỗi, câu hỏi và đề xuất tính năng | [GitHub Issues](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/issues) · [Hướng dẫn phản hồi](CONTRIBUTING.vi.md) |
| Báo cáo bảo mật | [Chính sách bảo mật](SECURITY.vi.md) |
| Website sản phẩm | [detect.expert](https://detect.expert) · [anti.bot](https://anti.bot) · [antidetect.com](https://antidetect.com) |

## Phân phối

AntiBotPCExplorer là **sản phẩm độc quyền, mã nguồn đóng**. Kho lưu trữ này cung cấp tài liệu chính thức, hình ảnh sản phẩm và các bản phát hành nhị phân. Mã nguồn ứng dụng được giữ riêng tư. Xem [LICENSE](LICENSE) và [thông báo về thành phần bên thứ ba](THIRD_PARTY_NOTICES.md).
