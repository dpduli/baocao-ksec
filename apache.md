##Công việc tuần 4

**Cách cài đặt Apache làm webserver**

- Đăng nhập vào SSH
 * Tất cả máy chủ nhân Linux đều cần đăng nhập vào SSH để tiến hành làm việc.

- Cập nhật package : trước khi làm việc ở Ubuntu lên phiên bản mới nhất với lệnh :

> apt -get update<br/>

- Cài đặt apache : Tên phần mềm trên Ubuntu là Apache2 nên chúng ta sẽ cài đặt với lệnh sau :

> apt -get install apache2<br/>

sau đó chọn Y để tiếp tục.

- Cấu trúc thư mục cấu hình Apache trên Ubuntu. Thư mục chứa các thiết lập của Apache sẽ nằm trong thư mục /etc/apache2 , trong thư mục này có một số thư mục và file cấu hình như sau :
 * conf-available/ – Thư mục này sẽ chứa các file thiết lập cấu hình sẵn của Apache trên Ubuntu, nhưng các thiết lập trong đây sẽ chưa được áp dụng vì Ubuntu không load thiết lập cấu hình trong thư mục này.
 * conf-enabled/ – Thư mục chứa các file thiết lập cấu hình của Apache trên Ubuntu đang được bật. Hãy hiểu là nếu thư mục này có một liên kết tượng trưng (symlink) qua một file module nào đó bên thư mục conf-available thì nó sẽ được bật.
 * mods-available/ – Thư mục chứa các file từng module của Apache trên Ubuntu nhưng chưa được bật.
 * mods-enabled/ – Thư mục chứa các file từng module của Apache trên Ubuntu đang được bật.
 * site-available/ – Thư mục chứa file cấu hình VirtualHost của Apache trên Ubuntu nhưng chưa được bật
 * site-enabled/ – Thư mục chứa file cấu hình VirtualHost của Apache trên Ubuntu đang được bật.
 * apache2.conf – File cấu hình Apache trên Ubuntu.
 * envvars – File thiết lập các biến với giá trị sẵn để sử dụng trong các file cấu hình.
 * magic – File thiết lập của module mod_mime_magic trên Apache.
 * ports.conf – File cấu hình cổng mạng của Apache (mặc định là port 80).

- Thư mục gốc chứa dữ liệu website của apache trên Ubuntu là : /var/www/html

- Sau khi cài đặt Apache, ứng dụng sẽ được thêm vào danh sách init.d của hệ thống, do đó có thể tự khởi động cùng với hệ điều hành. Sử dụng những lệnh sau để khởi động, kích hoạt và ngừng hoạt động của Apache: 

> sudo /etc/init.d/apache2 start #chạy apache<br/>
> sudo /etc/init.d/apache2 stop #dừng apache<br/> 
> sudo /etc/init.d/apache2 restart #khởi động lại apache 
