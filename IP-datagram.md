##IP Datagram


- Dữ liệu được truyền trong qua một mạng Internet bằng cách sử dụng IP được thực hiện trong các tin nhắn được gọi là IP datagram.

- Các datagram IPv4 được chia thành 2 phần là tiêu đề và tải trọng. Tiêu đề chứa địa chỉ và kiểm soát các lĩnh vực còn tải trọng mang dư liệu thực tế được gửi qua liên mạng.

- Cấu trúc gói tin:

 * Vesion : Xác định phiên bản của IP được sử dụng để tạo ra gói tin. Mục đích của nó nhằm đảm bảo khả năng tương thích giữa các thiết bị có thể chạy trên các phiên bản khác nhau của IP.
 *  IHL (Internet Header Length) : Định chiều dài của tiêu đề IP 
 *  TOS (Type Of Service) : Được thiết kế để mang thông tin để cung cấp chất lượng của các dịch vụ, chẳng hạn như phân phối ưu tiên cho IP Datagram.
 *  TL (Total Length) : Chỉ định tổng chiều dài của gói tin IP
 *  Identification : Trường này chứa một giá trị 16-bit được phổ biến cho mỗi đoạn thuộc về một thông điệp cụ thể; cho datagram ban đầu được gửi unfragmented nó vẫn được điền vào, vì vậy nó có thể được sử dụng nếu các gói tin phải được phân mảnh bởi một bộ định tuyến trong thời gian giao hàng. Trường này được sử dụng bởi người nhận để lắp ráp lại tin nhắn mà không vô tình pha trộn các mảnh vỡ từ các thông điệp khác nhau. Điều này là cần thiết vì các mảnh vỡ có thể đến từ nhiều tin nhắn pha trộn với nhau, kể từ khi gói dữ liệu IP có thể được nhận ra trật tự từ bất kỳ thiết bị.
 *  Flags : Flags kiểm soát xem một gói tin bị phân mảnh và / hoặc có thể được phân mảnh . Flags có cấu trúc như sau: ![image](http://www.upsieutoc.com/images/2015/09/29/ct1.png)<br/>Bit 0 : Dành, phải bằng không <br/>Bit 1 : Nơi mà các gói DF ngăn chặn các gói tin không bị phân mảnh <br/>Bit 2 : more fragments.
 *  Phân mảnh bù đắp (Fragment offset) : Khi phân mảnh của một thông điệp xảy ra nó sẽ xác định bù đắp của một đoạn cụ thể so với sự khởi đầu của đoạn này đi.
 *  TTL (Time To Live) : Chỉ định thời gian sống của gói tin trên mạng. Thường bị giảm đi khi đi qua hộp kế tiếp (trừ khi đó là tính chất bắc cầu)
 *  Nghị định thư : Phần này xác định các giao thức được sử dụng trong phần dữ liệu của gói tin IP.
 *  Tiêu đề Checksum : Checksum 16-bit được dùng để kiểm tra lỗi của header.
 *  Nguồn địa chỉ : Là địa chỉ IPv4 của người gửi gói tin. Địa chỉ này có thể được thay đổi trong vận chuyển bằng một địa chỉ mạng thiết bị.
 *  Địa chỉ đích : Là địa chỉ IPv4 của người nhận gói tin  cũng có thể được thay đổi trong quá trình gửi tin.
 *  Dữ liệu : phần dữ liệu của các gói dữ liệu không được bao gồm trong các gói tin checksum . Nội dung của nó được giải thích dựa trên giá trị của lĩnh vực tiêu đề Protocol. Một số giao thức phổ biến cho các phần dữ liệu : ![image](http://www.upsieutoc.com/images/2015/09/29/ct2.png)
