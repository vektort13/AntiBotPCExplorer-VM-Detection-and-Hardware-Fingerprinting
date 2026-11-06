# Nhật ký thay đổi

Tệp thực thi mới nhất có trên [GitHub Releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest).

## 1.4.0 — 2026-11-05

### Bổ sung

- Trang **VM Detection** với các nhóm kiểm tra, năm trạng thái kết quả, trọng số dữ liệu, mức đóng góp vào điểm số và phần giải thích chi tiết.
- **Physical PC Confidence**, điểm chẩn đoán thứ tư trên trang Overview.
- Mở rộng chẩn đoán ảo hóa, bao gồm CPU và cấu trúc liên kết, firmware, thiết bị PCI/PnP, thiết bị lưu trữ, bộ điều hợp mạng, đồ họa, màn hình và các thành phần tích hợp máy ảo khách.
- Danh mục tham khảo gồm 100 phương pháp và 10 dấu hiệu suy đoán bổ sung, kèm trạng thái triển khai và liên kết tới các phép kiểm tra có sẵn.
- Các kiểm tra bối cảnh thụ động về trình gỡ lỗi, lớp tương thích sandbox, Wine và phiên làm việc từ xa, được tách riêng khỏi điểm VM.
- Kết quả chẩn đoán mới trong báo cáo xuất ra và cả chín ngôn ngữ giao diện.

### Cải tiến

- Việc nhóm dữ liệu tính đến các tín hiệu liên quan, nguồn không khả dụng, bộ điều hợp trên máy vật lý và cấu hình máy chủ vật lý trên đám mây.
- Phân biệt Hyper-V và VBS trên máy vật lý với dữ liệu về máy ảo khách.
- Cải thiện việc đọc TPM và phân tích nhật ký khởi động, bao gồm phân loại lỗi rõ ràng hơn.
- Đóng gói bản dịch nhúng trong giới hạn kích thước trang WebView2.

### Sửa lỗi

- Nhãn điều hướng dài, cuộn thanh bên và khả năng truy cập các mục điều hướng phía dưới.
- Kích thước ban đầu và tối thiểu của cửa sổ trên màn hình DPI cao; ngắt dòng thanh công cụ và vị trí menu thả xuống trong cửa sổ hẹp.
- Che mã định danh máy ảo Hyper-V, tên máy ảo và mã định danh thế hệ trong báo cáo bảo vệ quyền riêng tư.
- Chuỗi giao diện tiếng Trung bị lỗi mã hóa.

Đây là phiên bản đầu tiên được phân phối qua kho lưu trữ sản phẩm công khai này.
