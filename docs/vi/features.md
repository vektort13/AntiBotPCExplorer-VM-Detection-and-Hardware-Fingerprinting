# Tính năng

[Trang chủ](../../README.vi.md) · [Cài đặt](installation.md) · [Câu hỏi thường gặp](faq.md) · [Quyền riêng tư và dữ liệu cục bộ](privacy.md)

AntiBotPCExplorer tập hợp danh tính thiết bị, thông tin phần cứng và bảo mật nền tảng Windows trong một công cụ kiểm tra cục bộ. Ứng dụng chạy ở chế độ người dùng, sử dụng các giao diện Windows sẵn có và không cần trình điều khiển nhân hệ điều hành.

## Bốn điểm số có thể giải thích

Trang Overview hiển thị điểm từ 0 đến 100 cho mỗi lĩnh vực, kèm các yếu tố đóng góp bên dưới.

| Điểm số | Nội dung được mô tả |
| --- | --- |
| Device identity | Các yếu tố nhận diện phần cứng và bản cài đặt hiện có, bao gồm mã định danh TPM, firmware, thiết bị lưu trữ và mạng |
| Platform integrity | Dữ liệu về cơ chế bảo vệ khởi động và nhân hệ điều hành: TPM, Secure Boot, VBS, HVCI, IOMMU cùng các cài đặt liên quan |
| Driver trust | Các loại chữ ký của trình điều khiển nhân đang chạy và cài đặt tính toàn vẹn mã của hệ thống |
| Physical PC Confidence | Dữ liệu ảo hóa, mức độ khả dụng của các nguồn và các nhóm dữ liệu độc lập tạo nên kết quả |

Điểm số được tính bằng các quy tắc có trọng số; mỗi trang cho biết những quan sát và phép kiểm tra làm cơ sở.

## VM Detection

Trang VM Detection riêng sắp xếp dữ liệu về máy ảo khách và hạ tầng đám mây theo từng nhóm. Mỗi phép kiểm tra đã thực hiện đều có trạng thái, trọng số, mức đóng góp vào điểm số và chi tiết kỹ thuật. Trang này còn có danh mục 100 phương pháp và mười dấu hiệu suy đoán yếu, kèm trạng thái triển khai cùng liên kết tới các phép kiểm tra đã thực hiện có liên quan.

Mô hình nhóm các quan sát liên quan để những tín hiệu firmware hoặc thiết bị có tương quan không bị tính lặp cùng một dữ liệu. Hyper-V hoặc VBS trên máy vật lý được diễn giải theo bối cảnh máy chủ của nó. Phiên làm việc từ xa và các kiểm tra thụ động về trình gỡ lỗi, Sandboxie, Comodo, Wine được hiển thị như thông tin bối cảnh, với trọng số điểm VM bằng không.

## Thông tin phần cứng và hệ thống

| Trang | Nội dung nổi bật |
| --- | --- |
| Identifiers | Các mã định danh tìm được, phạm vi tính duy nhất, trọng số, nhóm danh tính và nguồn |
| CPU & FPU | Tính năng CPU, cấu trúc liên kết bộ xử lý logic, bộ nhớ đệm và hồ sơ tính toán dấu phẩy động có kết quả xác định |
| Firmware | SMBIOS, ACPI, thông tin cập nhật firmware, chứng chỉ Secure Boot và cấu hình khởi động |
| Storage | Mã định danh ổ đĩa và bộ điều khiển, nhiều phương thức truy vấn lưu trữ, phân vùng và ổ logic |
| Network | Địa chỉ MAC hiện tại và cố định, mã định danh giao diện, mạng đã biết, thiết bị Bluetooth và thông tin modem di động |
| Display & power | Bộ điều hợp đồ họa, màn hình kết nối, EDID, chế độ hiển thị và pin |
| PnP devices | Mã định danh thiết bị, trình điều khiển, thông tin liên kết PCIe, đầu cuối âm thanh, cảm biến sinh trắc học, đầu đọc thẻ thông minh và máy in |
| TPM | Thuộc tính TPM, khóa và chứng chỉ xác nhận, PCR, nhật ký Measured Boot và bản ghi cấp phát của Windows |
| Platform security | Secure Boot, VBS/HVCI, tính toàn vẹn mã, IOMMU và trạng thái sản phẩm trong Security Center |
| Microsoft & cloud | Trạng thái giấy phép Windows, mã định danh dịch vụ Microsoft, trạng thái tham gia Entra, MDM/Intune và thông tin Autopilot |
| Kernel drivers | Trình điều khiển nhân đang chạy, phân loại chữ ký và tổng hợp nhà phát hành |
| Windows | Mã định danh bản cài đặt, thông tin hệ điều hành, lịch sử nâng cấp, siêu dữ liệu hồ sơ người dùng và chứng chỉ máy |
| Raw JSON | Ảnh chụp trạng thái cục bộ hiện tại; các giá trị nhạy cảm tuân theo cài đặt hiện mã định danh của giao diện |

Mức độ chi tiết phụ thuộc vào phần cứng, cấu hình Windows và quyền truy cập. Giao diện hiển thị thông báo trạng thái rõ ràng cho các nguồn không khả dụng.

## Đối chiếu từ các nguồn độc lập

Ứng dụng so sánh các quan sát thu được từ những nguồn khác nhau. Ví dụ: thông tin CPU với firmware, bộ điều hợp đồ họa với danh sách thiết bị, địa chỉ mạng hiện tại với địa chỉ cố định, số sê-ri lưu trữ giữa các phương thức truy vấn, và thông tin TPM với bản ghi firmware, Windows. Các sự kiện Measured Boot có thể được phát lại để đối chiếu với giá trị PCR hiện tại. Những điểm không khớp được hiển thị bên cạnh các quan sát.

## Compare snapshots

Tải hai báo cáo JSON đã lưu hoặc dùng lần quét hiện tại cho một trong hai ô. Ứng dụng so sánh các nhóm danh tính như TPM, bo mạch chủ, thiết bị lưu trữ, mạng, đồ họa, firmware, CPU, bản cài đặt Windows và bộ nhớ.

Kết quả gồm điểm tương đồng và phân tích theo từng nhóm. Các kịch bản mô phỏng tích hợp giúp bạn khám phá ảnh hưởng của việc cài lại Windows, nâng cấp linh kiện hoặc thay phần cứng đến kết quả so sánh. Một nút cho phép mở cùng cặp báo cáo đó trong Report diff.

## Report diff

So sánh hai báo cáo theo từng trường: siêu dữ liệu báo cáo, điểm số và các yếu tố đóng góp, phép đối chiếu, mã định danh và bảng dữ liệu. Màu đỏ đánh dấu trường bị thay đổi và những dòng chỉ xuất hiện trong một báo cáo. Bộ lọc có thể chỉ hiển thị khác biệt và bỏ qua các trường thường xuyên thay đổi như thời điểm quét hoặc thời gian hoạt động. Liên kết từng phần đưa bạn thẳng đến bảng so sánh tương ứng.

Bạn có thể tải báo cáo bằng hộp chọn tệp hoặc kéo tệp JSON vào một ô. Giá trị nhạy cảm vẫn được ẩn cho đến khi bạn chọn **Show identifiers**. Các báo cáo sử dụng cùng khóa cục bộ có thể so sánh mã định danh được bảo vệ; giá trị được bảo vệ bằng các khóa khác nhau được đánh dấu là không thể so sánh.

## Báo cáo và ngôn ngữ

Xuất báo cáo JSON bảo vệ quyền riêng tư, trong đó các trường nhạy cảm được thay bằng thẻ HMAC, hoặc báo cáo JSON thô chứa giá trị gốc đã thu thập. Cả hai định dạng đều có thể được tải lại vào các công cụ so sánh. Việc thu thập và xuất cũng hoạt động qua [dòng lệnh](installation.md).

Tệp thực thi chứa toàn bộ giao diện và chín ngôn ngữ: tiếng Anh, Nga, Việt, Trung giản thể, Trung phồn thể, Tây Ban Nha, Bồ Đào Nha (Brazil), Pháp và Đức.

## Minh họa khóa TPM tùy chọn

Trang TPM có thể tạo khóa minh họa ECDSA P-256 không thể xuất, ký và xác minh một thử thách mới, rồi xóa khóa. Các thao tác này chỉ chạy khi được yêu cầu. Lệnh `--selftest` thực hiện riêng một chu trình kiểm tra với khóa tạm thời và xóa khóa thử nghiệm khi hoàn tất.

## Phiên bản 1.4.0

Bản phát hành này giới thiệu Physical PC Confidence và trang VM Detection riêng, mở rộng chẩn đoán ảo hóa cùng các bản dịch tương ứng, cải thiện kích thước cửa sổ và điều hướng trên màn hình DPI cao, đồng thời cập nhật cơ chế che thông tin Hyper-V để bảo vệ quyền riêng tư. Xem [nhật ký thay đổi](../../CHANGELOG.vi.md) và [ghi chú phát hành](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/tag/v1.4.0).
