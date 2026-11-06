# Bảo mật

## Bản phát hành được hỗ trợ

Chúng tôi tiếp nhận báo cáo bảo mật cho bản phát hành mới nhất đã công bố, hiện là **1.4.0**. Tải xuống từ [GitHub Releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest).

## Báo cáo lỗ hổng

Dùng [biểu mẫu báo cáo lỗ hổng riêng tư của GitHub](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/security/advisories/new) để gửi báo cáo cho nhóm duy trì.

Cung cấp phiên bản ứng dụng, phiên bản Windows, các bước tái hiện, tác động quan sát được và ví dụ tối giản nếu có thể. Chỉ đính kèm dữ liệu cần thiết để minh họa vấn đề. Sử dụng báo cáo riêng tư cho chi tiết lỗ hổng và tệp đính kèm nhạy cảm.

Đối với lỗi thông thường và câu hỏi sử dụng, dùng [Issues](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/issues).

## Xác minh tệp tải xuống

Các tệp thực thi phát hành chính thức được ký số bởi **Vektor T13 Technologies B.V.** Bản phát hành có kèm `SHA256SUMS.txt`; [hướng dẫn cài đặt](docs/vi/installation.md) giải thích cách so sánh giá trị băm SHA-256 và kiểm tra chữ ký Windows.

## Dữ liệu chẩn đoán

Ứng dụng thu thập dữ liệu chẩn đoán cục bộ. Mã định danh được ẩn trong giao diện theo mặc định và báo cáo JSON tiêu chuẩn sử dụng thẻ HMAC. Báo cáo thô chứa giá trị gốc. Xem [Quyền riêng tư và báo cáo](docs/vi/privacy.md) để biết về lưu trữ cục bộ, tùy chọn xuất và việc chia sẻ báo cáo.
