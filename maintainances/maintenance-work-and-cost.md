# Công việc và chi phí bảo trì

**Trạng thái:** Đề xuất

**Đối tượng đọc:** CEO, chủ sản phẩm và đội kỹ thuật

## Mục đích

Tài liệu này nêu rõ việc cần làm để hệ thống hoạt động ổn định. Tài liệu cũng cho biết phí bảo trì của từng phương án.

Phí bảo trì không gồm làm tính năng mới, sửa lỗi mã nguồn, phát hành lớn, chuyển dữ liệu lớn hoặc nâng cấp lớn.

## Cách bảo trì

```mermaid
flowchart LR
    TuDong[Kiểm tra tự động] --> XemXet[Xem hai lần mỗi tháng]
    XemXet --> BaoTri[Bảo trì hằng tháng]
    BaoTri --> BaoCao[Báo cáo ngắn]
```

Hệ thống tự động phát hiện vấn đề thường gặp. Người phụ trách xem lại cảnh báo, sửa vấn đề cần thiết và báo cáo cho khách hàng.

## Việc được kiểm tra tự động

| Công việc | Kết quả cần có |
|---|---|
| Kiểm tra website, trang quản trị và API | Các dịch vụ chính trả lời bình thường |
| Theo dõi cảnh báo và lỗi mới | Vấn đề quan trọng được phát hiện |
| Theo dõi CPU, bộ nhớ, ổ đĩa và kết nối cơ sở dữ liệu | Máy chủ chưa gần hết tài nguyên |
| Kiểm tra bản sao lưu PostgreSQL mới nhất | Tác vụ đã chạy và có tệp sao lưu |
| Theo dõi đăng nhập sai và lưu lượng lạ | Vấn đề bảo mật được báo lại |

Cảnh báo được gửi tự động. Không có người ngồi theo dõi liên tục.

## Việc làm hai lần mỗi tháng

| Công việc | Kết quả cần có |
|---|---|
| Xem thời gian hoạt động, lỗi và tốc độ phản hồi | Phát hiện vấn đề lặp lại |
| Xem CPU, bộ nhớ, ổ đĩa và mức tăng dữ liệu | Phát hiện sớm nguy cơ thiếu tài nguyên |
| Xem truy vấn PostgreSQL chậm và số kết nối | Có hướng xử lý vấn đề cơ sở dữ liệu |
| Kiểm tra bản sao lưu | Có bản sao hằng ngày và bản sao Vietnix hằng tuần |
| Xem bản cập nhật hệ điều hành và bảo mật | Lên lịch hoặc cài bản cập nhật an toàn |
| Xem Cloudflare, tường lửa và quyền vào trang quản trị | Truy cập công khai vẫn được giới hạn |
| Kiểm tra bản ứng dụng ổn định gần nhất | Có thể quay lại bản cũ khi cần |
| Gửi báo cáo ngắn | Khách hàng biết tình trạng, rủi ro và việc đã làm |

Việc cần dừng hệ thống phải được khách hàng đồng ý trước.

## Việc làm hằng tháng

- Khôi phục thử PostgreSQL trong khu vực riêng và kiểm tra dữ liệu.
- Cài các bản cập nhật đã lên lịch.
- Xem lại quyền truy cập và xóa quyền không còn dùng.
- Kiểm tra chi phí và dung lượng còn lại.
- Sửa hướng dẫn phục hồi nếu có thông tin sai.

## Việc làm hằng quý

- Diễn tập phục hồi theo phương án đang dùng.
- Xem lại mức mất dữ liệu mà doanh nghiệp có thể chấp nhận.
- Kiểm tra phần mềm cũ và lên kế hoạch nâng cấp riêng.
- Đánh giá phương án hiện tại còn phù hợp hay không.

## Công sức dự kiến

Các số dưới đây dùng để ước lượng khối lượng việc. Phí bảo trì là phí trọn gói, không lấy số giờ nhân với đơn giá.

| Phương án | Xem định kỳ | Việc hằng tháng | Phần việc hằng quý tính trung bình | Tổng dự kiến |
|---|---:|---:|---:|---:|
| Phương án 1: Một máy chủ | 1,5 giờ/tháng | 2 giờ/tháng | 1,5 giờ/tháng | **5 giờ/tháng** |
| Phương án 2: Hai máy chủ | 2 giờ/tháng | 2 giờ/tháng | 2 giờ/tháng | **6 giờ/tháng** |
| Phương án 3: Tách riêng dịch vụ | 4 giờ/tháng | 3 giờ/tháng | 3 giờ/tháng | **10 giờ/tháng** |

Thời gian thật có thể thay đổi. Phí trọn gói còn trả cho việc theo dõi cảnh báo, giữ kiến thức về hệ thống và sẵn sàng hỗ trợ trong khung giờ đã thống nhất.

## Phí bảo trì

| Phương án | Trước VAT mỗi tháng | Sau VAT mỗi tháng | Sau VAT mỗi năm |
|---|---:|---:|---:|
| Phương án 1: Một máy chủ | 2 triệu VND | 2,2 triệu VND | **26,4 triệu VND** |
| Phương án 2: Hai máy chủ | 2,5 triệu VND | 2,75 triệu VND | **33 triệu VND** |
| Phương án 3: Tách riêng dịch vụ | 4 triệu VND | 4,4 triệu VND | **52,8 triệu VND** |

Phương án 2 là lựa chọn đề xuất. Phương án này có hai máy chủ cần kiểm tra riêng nhưng vẫn dễ quản lý.

## Công việc ngoài gói

Mọi công việc ngoài gói có đơn giá chung là **300.000 VND/giờ**.

- Áp dụng cùng một giá vào ban ngày, buổi tối, cuối tuần và ngày lễ.
- Tính theo mỗi 30 phút.
- Chỉ làm sau khi khách hàng đồng ý.
- Không cam kết người phụ trách luôn sẵn sàng ngoài giờ.
- Phí của nhà cung cấp khác được tính riêng.

Các việc thường nằm ngoài gói:

- Sửa lỗi mã nguồn hoặc làm tính năng.
- Chuyển dữ liệu lớn.
- Thay đổi kiến trúc.
- Nâng cấp phiên bản lớn.
- Xử lý nhiều sự cố bất thường trong cùng tháng.

## Thời gian phản hồi

- Gói thường: phản hồi trong vòng 8 giờ làm việc đã thống nhất.
- Không có trực 24/7.
- Không cam kết phản hồi trong 15 phút.
- Trường hợp khẩn cấp ngoài giờ chỉ được xử lý khi người phụ trách có thể nhận việc.

Nếu doanh nghiệp cần trực 24/7, nên thuê thêm đơn vị chuyên trực hệ thống.

## Khi nào cần đổi giá

Hai bên cần xem lại phí khi:

- Thêm máy chủ, cơ sở dữ liệu hoặc môi trường.
- Cần công cụ theo dõi hoặc bảo mật có phí.
- Yêu cầu phản hồi nhanh hơn.
- Tăng số lần sao lưu hoặc thời gian giữ bản sao.
- Lưu lượng, dữ liệu hoặc số sự cố tăng nhiều.
- Phạm vi công việc thực tế thường xuyên vượt gói.

Mức giá này là giá ưu đãi cho năm đầu. Hai bên nên xem lại khi gia hạn.

## Điều cần xác nhận

- Phương án 2 có phí bảo trì 2,5 triệu VND/tháng trước VAT.
- Công việc ngoài gói có giá 300.000 VND/giờ.
- Khung giờ hỗ trợ cần được ghi rõ trong hợp đồng.
- Khách hàng cần chỉ định người có quyền duyệt việc phát sinh.
- Việc cài hệ thống theo dõi, sao lưu và phát hành ban đầu nằm trong phí cài đặt 8 triệu VND.

## Tài liệu tham khảo

- [Các phương án triển khai](../deployments/README.md)
- [Kiến trúc Phương án 1](../deployments/option-1-single-server/architecture.md)
- [Kiến trúc Phương án 2](../deployments/option-2-two-servers/architecture.md)
- [Kiến trúc Phương án 3](../deployments/option-3-separate-services/architecture.md)
- [Phương án 4: Giám sát tối thiểu (rút gọn chi phí vận hành)](./goi-giam-sat-toi-thieu.md)
