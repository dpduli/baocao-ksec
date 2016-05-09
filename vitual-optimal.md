##Công việc tuần 5

**VirtualHost <host ảo>**

- Host ảo là một phương pháp lưu trữ nhiều tên miền trên một máy chủ. Điều này cho phép một máy chủ chia sẻ tài nguyên của nó , chẳng hạn như bộ nhớ và bộ cử lý chu kỳ mà không đòi hỏi tất cả các dịch vụ được cung cấp để sử dụng các tên máy chủ.

- Có 2 loại lưu trữ chính của lưu trữ ảo là : dựa trên tên (Named based virtual host) và dựa trên IP (IP based virtual host).
 * Named based virtual host: Một apache server cho phép host nhiều website có domain name khác nhau trên cùng một IP. Name based virtual host được sử dụng để cung cấp shared hosting.
 * IP based virtual host: Một apache server cho phép host nhiều website có domain khác nhau trên các IP khác nhau.

- Thông thường muốn upload website lên chúng ta thường phải sử dụng thư mục /var/www. Tuy nhiên đối với virtual chúng ta có thể tùy thích tạo ra một thư mục mới rồi thêm domain vào để sử dụng thư mục đó.

*optimal*

- Thông thường Apache chiếm dụng khá nhiều CPU do sử dụng quá nhiều các tiến trình để thiết lập lại số lượng processes mở file  /etc/httpd/conf/httpd.conf lên và tìm đoạn:

><IfModule prefork.c><br/>
StartServers       8<br/>
MinSpareServers    5<br/>
MaxSpareServers   20<br/>
ServerLimit      256<br/>
MaxClients       256<br/>
MaxRequestsPerChild  4000<br/>
</IfModule>

Ở đoạn trên, ta sửa lại các phần thành những giá trị sau:

StartServers : 1 MinSpareServers : 1 MaxSpareServers : 5 MaxRequestsPerChild : 10000
