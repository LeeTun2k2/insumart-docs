# Bảng báo giá vận hành hệ thống

**Trạng thái:** Bản cuối để phê duyệt

**Đối tượng đọc:** CEO, chủ sản phẩm và đội kỹ thuật

**Ngày kiểm tra giá:** 26 tháng 9 năm 2026

## Tóm tắt báo giá

Phương án khuyến nghị là **hai VPS**, gồm một VPS Web và một VPS PostgreSQL.

```mermaid
flowchart LR
    HaTang[Hạ tầng bắt buộc] --> Setup[Setup một lần]
    Setup --> VanHanh{Chọn vận hành}
    VanHanh --> Khong[Không vận hành]
    VanHanh --> Co[Có vận hành]
```

| Lựa chọn theo Phương án 2 | Năm đầu | Từ năm thứ hai |
|---|---:|---:|
| Không dùng gói vận hành | **11,85 triệu VND** | **6,6 triệu VND/năm** |
| Dùng gói vận hành | **44,85 triệu VND** | **39,6 triệu VND/năm** |

Các tổng trên đã gồm VAT 10% cho VPS và gói vận hành. Phí setup 5,25 triệu VND là giá trọn gói và không cộng thêm VAT.

## 1. Chi phí bắt buộc

Chi phí bắt buộc là tiền thuê VPS để hệ thống hoạt động. Có ba lựa chọn:

| Phương án | Cấu hình | Chi phí sau VAT | Ưu điểm | Nhược điểm | Đánh giá |
|---|---|---:|---|---|---|
| 1. Một VPS | Website, ứng dụng và PostgreSQL dùng chung một VPS | **275.000 VND/tháng**; **3,3 triệu VND/năm** | Chi phí thấp nhất. Dễ quản lý. | VPS lỗi thì toàn bộ hệ thống dừng. Website và cơ sở dữ liệu tranh tài nguyên. | Chỉ chọn khi ưu tiên tiết kiệm nhất. |
| 2. Hai VPS | Một VPS Web và một VPS PostgreSQL | **550.000 VND/tháng**; **6,6 triệu VND/năm** | Tách website khỏi cơ sở dữ liệu. Cân bằng tốt giữa chi phí và an toàn. Dễ mở rộng. | Mỗi VPS vẫn là một điểm lỗi. Cần quản lý hai máy chủ. | **Khuyến nghị.** |
| 3. Bốn VPS | Trang khách hàng, trang quản trị, ứng dụng và PostgreSQL dùng bốn VPS riêng | **1,1 triệu VND/tháng**; **13,2 triệu VND/năm** | Lỗi ở một trang có thể ít ảnh hưởng đến trang còn lại. Có thể phát hành từng phần riêng. | Chi phí và công quản lý cao. Ứng dụng và PostgreSQL vẫn là điểm lỗi. Chưa phù hợp với lưu lượng hiện tại. | Chưa cần dùng ở giai đoạn đầu. |

Giá mỗi VPS là 250.000 VND/tháng trước VAT. Mỗi VPS có 2 CPU, 4 GB RAM và 40 GB SSD.

Các mục sau không phát sinh thêm phí nhà cung cấp:

| Hạng mục | Chi phí |
|---|---:|
| Tên miền hiện có | 0 VND |
| Lưu tệp trên VPS Web | Đã gồm trong giá VPS |
| Bản sao lưu hằng tuần của nhà cung cấp | Đã gồm trong giá VPS |
| Công cụ theo dõi tự quản lý | 0 VND |

Giá VPS không tính khuyến mãi. Giá thật có thể thấp hơn nếu nhà cung cấp giảm giá khi trả trước.

## 2. Chi phí setup ban đầu

Phí setup trả một lần. Báo giá này áp dụng cho Phương án 2 được khuyến nghị:

| Phương án | Phí setup trọn gói |
|---|---:|
| 2. Hai VPS | **5,25 triệu VND** |

Chi tiết công việc:

| Công việc | Thời gian dự kiến | Chi phí phân bổ |
|---|---:|---:|
| Tạo hai VPS và cấp quyền truy cập | 1 giờ | 250.000 VND |
| Cài bảo mật hệ điều hành và tường lửa | 4 giờ | 1 triệu VND |
| Cấu hình HTTPS và cổng vào website | 4 giờ | 1 triệu VND |
| Cấu hình PostgreSQL và giới hạn kết nối | 3 giờ | 750.000 VND |
| Cấu hình nơi lưu tệp và quyền truy cập | 2 giờ | 500.000 VND |
| Cấu hình sao lưu và thử khôi phục | 4 giờ | 1 triệu VND |
| Cấu hình theo dõi, nhật ký và cảnh báo | 3 giờ | 750.000 VND |
| **Tổng** | **21 giờ** | **5,25 triệu VND** |

Chi phí được phân bổ theo mức 250.000 VND/giờ để làm rõ từng mục. Đây không phải đơn giá tính thêm. Các công việc trong bảng không phát sinh thêm phí. Yêu cầu ngoài phạm vi phải được báo giá và duyệt trước khi làm.

## 3. Chi phí vận hành

Có hai lựa chọn cho Phương án 2:

| Lựa chọn | Phí cố định | Phạm vi | Khả năng hỗ trợ khi có sự cố |
|---|---:|---|---|
| Không vận hành | **0 VND/tháng** | Không có người phụ trách theo dõi và kiểm tra định kỳ. Khách hàng tự kiểm tra cảnh báo, sao lưu, tài nguyên và bản cập nhật. | Chỉ sửa khi khách hàng báo và người phụ trách có thể nhận việc. **Không bảo đảm có mặt hoặc thời gian phản hồi.** Chi phí được báo theo nhu cầu và phải được khách hàng duyệt trước. |
| Có vận hành | **2,5 triệu VND/tháng trước VAT**; **2,75 triệu VND/tháng sau VAT** | Theo dõi, kiểm tra, bảo trì và báo cáo theo danh sách bên dưới. | Phản hồi trong 30 phút thuộc khung giờ hỗ trợ đã thống nhất. Không trực 24/7. |

### Việc làm khi có gói vận hành

| Tần suất | Công việc |
|---|---|
| Tự động | Kiểm tra website, trang quản trị, API, lỗi mới, tài nguyên VPS, kết nối PostgreSQL, bản sao lưu và truy cập bất thường. |
| Hai lần mỗi tháng | Xem cảnh báo, tốc độ phản hồi, CPU, bộ nhớ, ổ đĩa, mức tăng dữ liệu, truy vấn chậm, bản sao lưu, tường lửa và bản ứng dụng ổn định gần nhất. |
| Hằng tháng | Thử khôi phục PostgreSQL; cài bản cập nhật đã lên lịch; xem lại quyền truy cập, chi phí, dung lượng và hướng dẫn phục hồi; gửi báo cáo ngắn. |
| Hằng quý | Diễn tập phục hồi; xem lại mức mất dữ liệu có thể chấp nhận; kiểm tra phần mềm cũ và đánh giá lại phương án hạ tầng. |

Gói vận hành không gồm sửa lỗi mã nguồn, làm tính năng, nâng cấp lớn, chuyển dữ liệu lớn, trực 24/7 hoặc xử lý sự cố không giới hạn.

### Tổng ngân sách Phương án 2

| Lựa chọn | 1 năm | 2 năm | 3 năm |
|---|---:|---:|---:|
| Không dùng gói vận hành | **11,85 triệu VND** | **18,45 triệu VND** | **25,05 triệu VND** |
| Dùng gói vận hành | **44,85 triệu VND** | **84,45 triệu VND** | **124,05 triệu VND** |

Các tổng trên gồm VPS, phí setup một lần và phí vận hành nếu chọn.

## Điều cần chốt

- Chọn một, hai hay bốn VPS.
- Chọn có hoặc không có gói vận hành.
- Ghi rõ khung giờ hỗ trợ nếu có gói vận hành.
- Xác nhận bản sao lưu hằng tuần có đủ hay cần nơi lưu bên ngoài nhà cung cấp VPS.
- Chỉ định người có quyền duyệt công việc phát sinh.

## Tài liệu tham khảo

- [Các phương án triển khai](../deployments/README.md)
- [Kiến trúc Phương án 1](../deployments/option-1-single-server/architecture.md)
- [Kiến trúc Phương án 2](../deployments/option-2-two-servers/architecture.md)
- [Kiến trúc Phương án 3](../deployments/option-3-separate-services/architecture.md)
- [Công việc và chi phí bảo trì](../maintainances/maintenance-work-and-cost.md)
- [Ứng phó sự cố](../maintainances/incident-response.md)
- [Giảm VAT tại Việt Nam đến hết năm 2026](https://baochinhphu.vn/giam-thue-gia-tri-gia-tang-tu-01-7-2025-den-het-31-12-2026-10225070118590677.htm)
