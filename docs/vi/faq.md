# Câu hỏi thường gặp

[Trang chủ](../../README.vi.md) · [Cài đặt](installation.md) · [Tính năng](features.md) · [Quyền riêng tư và dữ liệu cục bộ](privacy.md)

## AntiBotPCExplorer làm được gì?

Ứng dụng kiểm tra mã định danh phần cứng và hệ thống của máy tính Windows, hiển thị thông tin bảo mật nền tảng và chữ ký trình điều khiển, phân tích dữ liệu ảo hóa và so sánh ảnh chụp trạng thái thiết bị. Xem [hướng dẫn tính năng](features.md) để tìm hiểu đầy đủ các phần trong giao diện.

## Những phiên bản Windows nào có thể chạy ứng dụng?

Windows 10 và Windows 11 trên hệ thống x64. Giao diện đồ họa sử dụng Microsoft Edge WebView2 Runtime. Tệp thực thi chạy trực tiếp và chứa sẵn giao diện cùng các bản dịch; không cần cài .NET.

## Tôi tải ứng dụng ở đâu?

Tải tệp thực thi từ [GitHub Releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest). Cùng bản phát hành đó có ghi chú phát hành và tổng kiểm SHA-256. Xem [Cài đặt](installation.md) để biết cách chạy lần đầu và xác minh tệp.

## Vì sao giao diện thông báo không thể khởi động WebView2?

Cài Evergreen Runtime x64 từ [trang WebView2 của Microsoft](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) rồi khởi chạy lại ứng dụng. Bạn cũng có thể thu thập báo cáo JSON mà không dùng giao diện đồ họa bằng `--export report.json`; chế độ này không sử dụng WebView2.

## Tôi có cần quyền quản trị viên không?

Việc kiểm tra thông thường chạy bằng tài khoản người dùng tiêu chuẩn. Một số nguồn yêu cầu nâng quyền, bao gồm biến UEFI, cấu hình khởi động, ATA Identify, giá trị băm phần cứng Autopilot và lịch sử mạng đã biết. Giao diện chỉ rõ các nguồn không khả dụng; thao tác **Restart as administrator** cho phép khởi động lại công cụ với quyền cao hơn.

## Ứng dụng có thay đổi mã định danh hoặc cài đặt bảo mật của máy tính không?

Quá trình quét đọc dữ liệu hiện có. Ứng dụng không sửa đổi mã định danh phần cứng, firmware, cài đặt khởi động hoặc chính sách bảo mật Windows, và không cài trình điều khiển nhân hệ điều hành. Chức năng minh họa khóa TPM tùy chọn tạo hoặc xóa khóa riêng của nó khi bạn yêu cầu. Ứng dụng cũng lưu khóa so sánh cục bộ, ngôn ngữ đã chọn, hồ sơ WebView2 và ghi báo cáo xuất ra vào vị trí bạn chọn.

## Ứng dụng có tải kết quả quét lên mạng hoặc dùng dịch vụ đám mây không?

Việc thu thập, phân tích, so sánh báo cáo và xuất dữ liệu đều diễn ra cục bộ. Ứng dụng không gửi yêu cầu mạng. Các nút **anti.bot** và **detect.expert** mở những website này trong trình duyệt mặc định. Xem [Quyền riêng tư và dữ liệu cục bộ](privacy.md).

## Vì sao một số giá trị bị ẩn?

Số sê-ri, UUID, địa chỉ MAC, dấu vân tay khóa và các trường khác được đánh dấu nhạy cảm đều được che theo mặc định. Nhấp **Show identifiers** rồi xác nhận để hiện chúng. Trang Raw JSON tuân theo cùng cài đặt này.

## Hai định dạng xuất khác nhau thế nào?

Báo cáo bảo vệ quyền riêng tư thay các trường nhạy cảm bằng thẻ HMAC có khóa và bỏ qua các bảng không thuộc phạm vi xuất an toàn. Báo cáo chẩn đoán thô chứa giá trị gốc đã thu thập. Cả hai đều giữ cấu trúc chẩn đoán của báo cáo. Thay đổi cài đặt hiện giá trị trên màn hình không làm thay đổi định dạng xuất đã chọn.

## Báo cáo bảo vệ quyền riêng tư có thể so sánh được không?

Có. Các báo cáo được xuất bằng cùng khóa HMAC cục bộ có thể đối chiếu mã định danh được bảo vệ mà không hiện giá trị gốc. Khi khóa khác nhau, công cụ so sánh các giá trị đọc được và đánh dấu trường được bảo vệ là không thể so sánh. Xóa thư mục dữ liệu cục bộ của ứng dụng sẽ đặt lại khóa này.

## Compare snapshots khác Report diff như thế nào?

**Compare snapshots** tính mức độ tương đồng có trọng số giữa các nhóm danh tính thiết bị và cung cấp mô phỏng thay đổi phần cứng. **Report diff** hiển thị riêng từng trường, điểm số, phép kiểm tra và dòng bảng bị thay đổi. Trang so sánh có thể chuyển trực tiếp hai báo cáo sang Report diff.

## Bật Hyper-V hoặc VBS có tự động khiến máy tính bị coi là máy ảo khách không?

Mô hình VM đánh giá các quan sát theo bối cảnh và nhóm dữ liệu liên quan. Hyper-V hoặc VBS trên máy Windows vật lý không được coi là bằng chứng độc lập cho thấy máy đó là máy ảo khách. Trang VM Detection hiển thị các phép kiểm tra và mức đóng góp tạo nên Physical PC Confidence.

## Tôi đổi ngôn ngữ như thế nào?

Dùng nút lá cờ trên thanh công cụ hoặc các lựa chọn ngôn ngữ trên trang About. Bạn cũng có thể khởi chạy bằng `--lang en`, `--lang ru`, `--lang vi` hoặc `--lang zh-Hant`. Các mã khác gồm `zh-Hans`, `es`, `pt`, `fr` và `de`.

## Cài đặt được lưu ở đâu và xóa bằng cách nào?

Thư mục mặc định là `%LOCALAPPDATA%\AntiBotPCExplorer`; thư mục dự phòng là `%TEMP%\AntiBotPCExplorer`. Thư mục này chứa khóa HMAC, ngôn ngữ đã chọn và hồ sơ WebView2. Hãy đóng ứng dụng trước khi xóa thư mục. Khóa TPM minh họa tùy chọn được xóa riêng bằng **Delete key** trên trang TPM.

## Tôi báo lỗi hoặc đề xuất tính năng bằng cách nào?

Dùng [GitHub Issues](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/issues). Cung cấp phiên bản ứng dụng, phiên bản Windows, trang bị ảnh hưởng, các bước tái hiện và kết quả bạn mong đợi. [Hướng dẫn đóng góp](../../CONTRIBUTING.vi.md) mô tả quy trình phản hồi; [chính sách bảo mật](../../SECURITY.vi.md) mô tả cách báo cáo lỗ hổng. Website sản phẩm: [detect.expert](https://detect.expert), [anti.bot](https://anti.bot) và [antidetect.com](https://antidetect.com).
