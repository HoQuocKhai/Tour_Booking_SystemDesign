# **BẢNG LUỒNG HOẠT ĐỘNG WEBSITE VIETRAVELASIA.COM**

| Bước | Tên bước | Người dùng thực hiện | Hệ thống / backend cần làm | Điểm cần lưu ý / điều kiện đặc biệt |
| :---: | :---: | ----- | ----- | ----- |
| 1 | **Truy cập trang chủ** | Người dùng mở website | Hiển thị homepage: menu, ngôn ngữ/tiền tệ, banner, phần “Tours & Activities”, “Hot Deals”… ([Vietravel Asia](https://vietravelasia.com/?utm_source=chatgpt.com)) | Hỗ trợ đa ngôn ngữ (English), đa tiền tệ (USD) |
| 2 | **Chọn danh mục dịch vụ** | Người dùng chọn “Tours & Activities”, “Transportation”, “Stays”, “Guide” hoặc “Hot Deals” từ menu | Hệ thống lọc và hiển thị danh sách dịch vụ theo danh mục | Có thể có bộ lọc thêm (điểm đến, ngày, giá) |
| 3 | **Tìm kiếm / lọc tour** | Người dùng nhập hoặc chọn điểm đến, ngày, số người, loại tour | Backend trả kết quả phù hợp, hiển thị grid/thẻ tour | Cần xử lý ngày khởi hành, số lượng khách, tình trạng còn chỗ |
| 4 | **Xem chi tiết tour** | Người dùng chọn 1 tour cụ thể từ danh sách | Hiển thị trang chi tiết: mô tả tour, lịch trình, giá, hình ảnh, điều kiện, “Thêm vào giỏ hàng” | Giá phải rõ ràng, có thể hiển thị khuyến mãi, đa tiền tệ |
| 5 | **Thêm vào giỏ hàng (Cart)** | Người dùng chọn “Add to Cart” hoặc tương đương | Hệ thống lưu dữ liệu tạm thời: dịch vụ, số lượng khách, ngày khởi hành, giá → giỏ hàng | Giỏ hàng có thể chứa nhiều dịch vụ khác nhau (tour, transport, stay) |
| 6 | **Đăng nhập / Đăng ký hoặc đặt khách vãng lai** | Nếu người dùng chưa login: chọn “User Login” hoặc “Agent Login” hoặc “Guest checkout” | Hệ thống xác thực user / agent hoặc chuyển tiếp đặt khách vãng lai | Có phân biệt đại lý (Agent) với user thường, quyền khác nhau |
| 7 | **Checkout – nhập thông tin khách** | Người dùng đi tới thanh toán: nhập thông tin cá nhân, số người, lựa chọn dịch vụ, ngày. | Hệ thống lưu form đặt, kiểm tra tính hợp lệ, hiển thị tổng giá, tiền tệ, thuế/chi phí nếu có | Cần xác định chính sách hủy, điều khoản, hiển thị rõ ràng |
| 8 | **Thanh toán** | Người dùng chọn phương thức thanh toán và thanh toán | Hệ thống xử lý thanh toán (gateway), cập nhật trạng thái đặt hàng: “chờ xác nhận” hoặc “xác nhận đã thanh toán” | Cần tích hợp đa phương thức thanh toán, bảo mật thông tin thanh toán |
| 9 | **Xác nhận đặt & tạo đơn hàng** | Sau thanh toán thành công (hoặc đặt trước): hệ thống tạo đơn hàng, gửi email xác nhận cho khách hàng và (nếu có) cho đại lý. | Cập nhật trong hệ thống: trạng thái đơn, gửi email/SMS cho khách | Cần lưu lịch sử đơn hàng trong tài khoản user, có thể link lịch sử đặt cho Agent |
| 10 | **Hỗ trợ sau đặt / dịch vụ khách hàng** | Sau khi đặt, khách có thể yêu cầu hỗ trợ, thay đổi, huỷ hoặc cung cấp feedback | Hệ thống cung cấp giao diện khách hàng / agent để xem trạng thái đơn hàng, thay đổi thông tin, lên lịch dịch vụ | Yêu cầu đa kênh hỗ trợ (email, hotline) vì website nhấn mạnh “Fast Response”. ([Vietravel Asia](https://vietravelasia.com/?utm_source=chatgpt.com)) |
| 11 | **Trải nghiệm dịch vụ & feedback** | Khách hàng tham gia tour / dịch vụ → có thể để lại phản hồi | Hệ thống có thể gửi email/nhắc nhở feedback, lưu review vào hồ sơ dịch vụ | Feedback giúp nâng cao uy tín – trang web có nhấn “Positive Clients Feedback”. ([Vietravel Asia](https://vietravelasia.com/?utm_source=chatgpt.com)) |
| 12 | **Quản lý tài khoản (user/agent)** | Người dùng hoặc Agent đăng nhập xem lịch sử đơn, thay đổi thông tin, thanh toán còn nợ | Hệ thống cung cấp dashboard: thông tin cá nhân, lịch sử đặt, đơn hàng đang chờ, hóa đơn | Phân quyền giữa user thường và agent, bảo mật thông tin, đa tiền tệ/đa thị trường |

# **MODULE 1: USER JOURNEY (TỪ TRANG CHỦ → ĐẶT TOUR)**

| Step | Flow node | Chi tiết hành vi |
| :---: | ----- | ----- |
| 1 | User mở trang chủ | Load homepage \+ banner \+ menu |
| 2 | User chọn ngôn ngữ/tiền tệ (EN / USD) | Website đổi toàn bộ UI |
| 3 | Chọn danh mục dịch vụ | Tours & Activities / Transportation / Stays / Hot Deals |
| 4 | Lọc tour | Theo điểm đến, ngày, số người |
| 5 | Chọn một tour | Nhảy sang trang chi tiết tour |
| 6 | Nhấn “Add to Cart” | Tour được thêm vào Cart |
| 7 | Xem Cart | Kiểm tra danh sách dịch vụ |
| 8 | Chọn “Proceed to Checkout” | Chuyển sang trang thanh toán |
| 9 | Login / Register / Guest checkout | Xác thực người dùng |
| 10 | Đi tới Booking Flow | Bắt đầu module đặt tour |

---

# **MODULE 2: BOOKING FLOW (QUY TRÌNH ĐẶT TOUR)**

| Step | Flow node | Chi tiết |
| :---: | :---: | ----- |
| 1 | Kiểm tra dịch vụ trong Cart | Lấy danh sách tour \+ số lượng khách |
| 2 | Nhập thông tin cá nhân | Tên, email, số điện thoại |
| 3 | Chọn ngày khởi hành | Kiểm tra slot còn hay không |
| 4 | Xác nhận số lượng khách | Tự tính lại giá |
| 5 | Review đơn hàng | Hiển thị giá cuối cùng |
| 6 | Chọn phương thức thanh toán | Card / eWallet / chuyển khoản |
| 7 | Chuyển sang Payment Flow | Xử lý thanh toán |
| 8 | Nhận kết quả từ Payment | Thành công / thất bại |
| 9 | Nếu thành công → tạo đơn hàng | Lưu booking, gán mã đặt |
| 10 | Gửi email xác nhận | Gửi thông tin booking cho khách |

---

# **MODULE 3: PAYMENT FLOW (QUY TRÌNH THANH TOÁN)**

| Step | Flow node | Chi tiết |
| :---: | :---: | ----- |
| 1 | User chọn phương thức thanh toán | Ví dụ: thẻ, cổng thanh toán |
| 2 | Redirect tới cổng thanh toán | Gửi dữ liệu order |
| 3 | User nhập thông tin thanh toán | Thẻ, OTP… |
| 4 | Thanh toán xử lý | Tạo transaction |
| 5 | Gateway trả kết quả về website | Success / Failed |
| 6 | Nếu Success → cập nhật booking | Trạng thái Paid |
| 7 | Nếu Failed → quay lại Checkout | Cho phép thử lại |
| 8 | Gửi email thông báo | Booking confirmation hoặc thất bại |

---

# **MODULE 4: AGENT FLOW (DÀNH CHO ĐẠI LÝ – AGENT LOGIN)**

| Step | Flow node | Chi tiết |
| :---: | :---: | ----- |
| 1 | Agent mở website → chọn Agent Login | Form login khác user |
| 2 | Nhập tài khoản agent | Username \+ password |
| 3 | Xác thực agent | Kiểm tra quyền |
| 4 | Vào dashboard agent | Danh sách khách, booking đã tạo |
| 5 | Agent tạo booking giúp khách | Chọn tour → thêm khách |
| 6 | Xem giá đại lý | Giá khác user thường |
| 7 | Xác nhận đặt | Tạo booking |
| 8 | Theo dõi tình trạng booking | Pending / Confirmed |
| 9 | Gửi thông tin cho khách | Email / in invoice |
| 10 | Quản lý doanh thu đại lý | Tổng booking, báo cáo |

---

# **MODULE 5: TOUR DETAIL PAGE FLOW (TRANG CHI TIẾT TOUR)**

| Step | Flow node | Chi tiết |
| :---: | :---: | ----- |
| 1 | User truy cập chi tiết tour | Từ danh sách tour |
| 2 | Website load dữ liệu tour | Tên, mô tả, lịch trình |
| 3 | Hiển thị hình ảnh | Slider/gallery |
| 4 | Hiển thị giá | Đa tiền tệ |
| 5 | Hiển thị các tùy chọn | Ngày khởi hành / số người |
| 6 | Button: “Add to Cart” | Thêm vào giỏ hàng |
| 7 | Xử lý thêm cart | Cập nhật giỏ hàng |
| 8 | Gợi ý tour liên quan | Related tours |

---

# **MODULE 6: CART FLOW (GIỎ HÀNG)**

| Step | Flow node | Chi tiết |
| :---: | :---: | ----- |
| 1 | User mở Cart | Dropdown hoặc trang riêng |
| 2 | Hiển thị danh sách dịch vụ | Tour, số người, ngày |
| 3 | Calculations | Tổng giá theo currency |
| 4 | Edit cart | Xóa, sửa số lượng |
| 5 | Chọn “Proceed to Checkout” | Bắt đầu Booking Flow |

