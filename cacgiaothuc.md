##Công việc tuần 9

**Tìm hiểu về SSH**

- SSH là một giao thức mạng là một giao thức mạng dùng để thiết lập kết nối mạng một cách bảo mật.

- SSH hoạt động ở lớp trên trong mô hình phân lớp TCP/IP . Các công cụ của SSH như OpenSSH cung cấp cho người dùng cách thức để thiết lập kết nối mạng được mã hóa để tạo một kênh kết nối riêng tư.

- SSH là chương trình tương tác giữa máy chủ và máy khách có sử dụng cơ chế mã hóa đủ mạnh nhằm ngăn chặn các hiện tượng như nghe trộm , đánh cắp thông tin trên đường truyền. 

- Sử dụng SSH là phương pháp hữu hiệu bảo mật dữ liệu trên đường truyền từ hệ thống này đến hệ thống khác.


*Các bước làm việc của SSH*

- Định danh Host , xác định định danh của hệ thống tham gia phiên làm việc SSH.

- Mã hóa, thiết lập kênh làm việc mã hóa.

- Chứng thực,  xác thực người sử dụng có quyền đăng nhập hệ thống.

https://www.youtube.com/watch?v=xCWFLjLjNsk

**FTP và SFTP**

- FTP viết tắt của "file transfer protocol" (Giao thức truyền tập tin) thường được dùng để trao đổi tập tin qua mạng lưới truyền thông dùng giao thức TCP/IP. Hoạt động của FTP cần có 2 máy (1 máy server và 1 máy client). Máy chủ FTP dùng để chạy phần mềm cung cấp dịch vụ FTP , máy khách chạy phần mềm FTP dành cho người sử dụng dịch vụ.

- FTP thường chạy trên 2 cổng 20 và 21, và chỉ chạy trên nền tảng TCP.

- Mục đích của FTP :

 * khuyến khích việc dùng chung tập tin.
 * Khuyến khích việc sử dụng máy tính ở xa một cách gián tiếp.
 * Che đậy sự khác biệt về hệ thống lưu trữ tập tin giữa các máy chủ , cho người dùng không cần quan tâm tới sự riêng tư của chúng.
 * Truyền tải dữ liệu một cách đáng tin cậy và có hiệu quả cao.

- Tuy nhiên, FTP rất dễ gặp những vấn đề bảo mật do các dữ liệu truyền tải không về được mã hóa, nó còn có đặc tính cho phép một người dùng nặc danh gửi dữ liệu lên máy chủ.

*sFTP*

- sFTP viết tắt của "sercure file transfer protocol" hoặc "SSH file transfer protocol" . là một giao thức trao đổi dữ liệu giữa máy khách và máy chủ , nhưng các dữ liệu được trao đổi sẽ được mã hóa trước khi chuyển đến máy chủ hoặc máy khách , hoạt động như một bản mở rộng của SSH thay thế cho FTP vốn không an toàn.

- kết nối vào sFTP ở Windows: dùng các phần mềm như FileZilla, FlashFXP, Cyberduck, WinSCP.

https://youtu.be/xTdmn7B5KVQ
