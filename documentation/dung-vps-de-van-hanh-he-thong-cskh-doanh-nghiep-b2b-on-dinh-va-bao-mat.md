---
description: "Hướng dẫn từng bước dùng VPS để vận hành hệ thống CSKH tổ chức ổn định, bảo mật và sẵn sàng cho mùa cao điểm."
---

# Dùng VPS để vận hành hệ thống CSKH doanh nghiệp B2B ổn định và bảo mật

## Mở đầu: Vì sao đội CSKH cần hạ tầng riêng

Nhiều đội CSKH doanh nghiệp B2B tại Hà Nội và TP.HCM đang vận hành hệ thống ticket, CRM và email thông báo trên hạ tầng dùng chung hoặc dịch vụ giá rẻ. Khi bước vào cuối quý hoặc mùa báo cáo, lưu lượng yêu cầu từ khách hàng doanh nghiệp tăng đột biến, hệ thống dễ bị nghẽn. Khách chờ phản hồi lâu, lịch sử trao đổi bị gián đoạn, việc đối soát hợp đồng trở nên khó khăn.

Với đội CSKH từ 5 đến 20 người, hạ tầng riêng mang lại ba lợi ích rõ rệt. Thứ nhất, doanh nghiệp kiểm soát toàn bộ dữ liệu khách hàng thay vì phụ thuộc vào bên thứ ba. Thứ hai, đội kỹ thuật có thể chủ động nâng cấu hình khi cần. Thứ ba, môi trường thử nghiệm và môi trường vận hành được tách bạch, giảm rủi ro khi thay đổi cấu hình.

## VPS phù hợp với khối công việc CSKH nào

[VPS](https://vps.com.vn/) không phải là giải pháp cho mọi nhu cầu, nhưng rất phù hợp để chạy các khối công việc chính của đội CSKH. Hệ thống ticket nội bộ và CRM lưu lịch sử trao đổi phục vụ đối soát hợp đồng là ứng dụng đầu tiên nên đặt lên VPS. Máy chủ email gửi thông báo cho khách doanh nghiệp, ví dụ cảnh báo SLA hoặc nhắc gia hạn hợp đồng, cũng cần một môi trường riêng để kiểm soát danh tiếng tên miền.

Tổng đài VoIP và công cụ chat đa kênh tích hợp với ticket là khối công việc thứ ba. Kho lưu trữ tệp đính kèm và biên bản trao đổi theo hợp đồng là khối thứ tư. Lưu ý quan trọng: không đặt mọi thứ lên một VPS duy nhất. Nên tách vai trò ngay từ đầu, ví dụ một VPS cho ticket và CRM, một VPS cho email, để khi một dịch vụ gặp sự cố không kéo theo toàn bộ hệ thống.

## Chuẩn bị trước khi triển khai

Trước khi cài đặt, đội CSKH cần kiểm kê dữ liệu khách hàng: loại dữ liệu đang lưu, nơi lưu trữ, thời hạn lưu theo hợp đồng. Việc này giúp xác định dung lượng cần thiết và chính sách lưu trữ phù hợp.

Phân quyền theo vai trò là bước chuẩn bị thứ hai. Quản lý cần quyền xem toàn bộ, trưởng nhóm xem dữ liệu của nhóm phụ trách, nhân viên chỉ xem dữ liệu khách hàng mình phục vụ. Kiểm toán nội bộ nếu có chỉ cần quyền đọc. Quy định sao lưu cần được thống nhất: tần suất sao lưu, nơi lưu bản sao, người chịu trách nhiệm khôi phục.

Khi chọn nhà cung cấp VPS, ưu tiên datacenter tại Việt Nam hoặc gần khu vực khách hàng chính để giảm độ trễ. Cam kết uptime và hỗ trợ kỹ thuật bằng tiếng Việt là hai tiêu chí cần xác nhận trước. Cuối cùng, thống nhất đầu mối kỹ thuật và đầu mối CSKH để tránh trách nhiệm chồng chéo trong quá trình triển khai.

## Các bước triển khai

1. Chọn cấu hình VPS theo tải thực tế. Với đội 5–20 người, cần ước lượng CPU và RAM cho ticket và CRM, dung lượng đĩa cho lịch sử trao đổi, băng thông cho email. Nên bắt đầu ở mức vừa phải và nâng cấp khi cần.

2. Cài hệ điều hành, cập nhật bản vá, tạo tài khoản quản trị riêng và tắt đăng nhập mặc định. Đây là bước nền tảng cho bảo mật.

3. Cài hệ thống ticket/CRM, cấu hình tên miền phụ và chứng chỉ HTTPS. Tên miền phụ nên dễ nhớ, ví dụ ticket.tenmien.vn cho hệ thống ticket.

4. Cấu hình email gửi thông báo với bản ghi SPF, DKIM và DMARC. Ba bản ghi này giúp email đến hộp thư khách hàng doanh nghiệp không bị rơi vào spam.

5. Kết nối tổng đài VoIP và kênh chat vào ticket. Kiểm tra việc ghi nhận lịch sử hội thoại vào đúng hồ sơ khách hàng.

6. Thiết lập sao lưu định kỳ tự động. Ngay sau lần sao lưu đầu tiên, thực hiện thử khôi phục trên môi trường test để xác nhận bản sao lưu dùng được.

7. Ghi lại toàn bộ cấu hình vào tài liệu bàn giao nội bộ. Tài liệu này cần bao gồm tài khoản quản trị, sơ đồ dịch vụ và lịch sao lưu.

## Kiểm thử và bàn giao cho đội CSKH

Checklist nghiệm thu nên dựa trên tình huống thực tế. Kiểm tra khách gửi ticket ngoài giờ có được ghi nhận đúng thời gian hay không. Kiểm tra ticket quá hạn SLA có kích hoạt cảnh báo hay không. Kiểm tra khách phản hồi qua email có được gắn vào đúng ticket gốc hay không.

Phân quyền cần được kiểm tra kỹ: nhân viên không xem được dữ liệu ngoài phạm vi phụ trách. Kiểm tra tải bằng cách mô phỏng lượng ticket và email của một ngày cao điểm cuối quý. Kiểm tra khôi phục bằng cách xóa thử dữ liệu trên môi trường test và phục hồi từ bản sao lưu.

Bàn giao kèm hướng dẫn một trang cho nhân viên: cách đăng nhập, cách tạo ticket, cách tra cứu lịch sử khách hàng. Đồng thời xác định rõ đầu mối báo sự cố khi hệ thống gặp vấn đề.

## Vận hành cao điểm và mở rộng

Giám sát các chỉ số cơ bản: tải CPU, dung lượng đĩa, hàng đợi email, thời gian phản hồi trang ticket. Đặt ngưỡng cảnh báo trước mùa cao điểm và phân công người theo dõi. Ví dụ, cảnh báo khi CPU vượt 80% liên tục trong 15 phút.

Quy trình nâng cấu hình gồm ba bước: đánh giá tải hiện tại, xác định nút thắt, sau đó nâng RAM hoặc CPU hoặc tách dịch vụ sang VPS riêng. Quy trình xử lý sự cố cần ghi rõ các bước sơ cứu, kênh liên hệ nhà cung cấp và phương án dùng tạm khi hệ thống gián đoạn. Sau mỗi mùa cao điểm, ghi nhật ký sự cố và rút kinh nghiệm.

## Lưu ý bảo mật và tuân thủ dữ liệu khách hàng

Mã hóa đường truyền bằng HTTPS, đặt mật khẩu mạnh, bật xác thực hai lớp cho tài khoản quản trị. Giới hạn truy cập theo IP hoặc VPN nội bộ với dữ liệu khách hàng doanh nghiệp. Sao lưu tách biệt khỏi máy chủ chính và kiểm tra định kỳ khả năng khôi phục.

Về tuân thủ quy định Việt Nam về bảo vệ dữ liệu cá nhân, cần thu thập tối thiểu, có sự đồng ý của khách hàng, và quy định thời hạn lưu rõ ràng. Xây dựng quy định nội bộ về xuất dữ liệu, chia sẻ tệp và xóa dữ liệu khi kết thúc hợp đồng.

## Checklist tóm tắt để tra cứu nhanh

- Xác định khối công việc đặt lên VPS: ticket, CRM, email, tổng đài, lưu trữ tệp.
- Kiểm kê dữ liệu khách hàng và thời hạn lưu theo hợp đồng.
- Phân quyền theo vai trò quản lý, trưởng nhóm, nhân viên, kiểm toán.
- Chọn VPS có datacenter tại Việt Nam, cam kết uptime, hỗ trợ tiếng Việt.
- Cài hệ điều hành, cập nhật bản vá, tắt tài khoản mặc định.
- Cấu hình HTTPS, SPF, DKIM, DMARC.
- Thiết lập sao lưu tự động và thử khôi phục ngay.
- Kiểm thử tình huống ticket ngoài giờ, quá hạn SLA, phản hồi qua email.
- Đặt ngưỡng cảnh báo trước mùa cao điểm.
- Ghi tài liệu bàn giao và nhật ký sự cố sau mỗi mùa cao điểm.
