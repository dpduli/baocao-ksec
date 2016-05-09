##Công việc tuần 7,8

**Định nghĩa cách dữ liệu được lưu trữ trong MySQL**

- Create Database : Được dùng để tạo cơ sở dữ liệu mới, trống.

- Drop Database : Được dùng để hủy hoàn toàn một cơ sở dữ liệu sẵn có.

- USE : Được dùng để chọn một cơ sở dữ liệu làm mặc định.

- Creat Table : Được dùng để tạo bảng mới , nơi mà dữ liệu của chúng ta thực sự được lưu trữ.

- Alter Table : Được dùng để sửa một định nghĩa bảng sẵn có.

- Describe : Hiển thị cấu trúc của một bảng.

**Thao tác với dữ liệu**

- SELECT : Được dùng khi muốn đọc hay lựa chọn dữ liệu.

- INSERT : Được dùng khi muốn thêm hoặc chèn dữ liệu mới.

- UPDATE : Được dùng khi bạn muốn thay (hoặc cập nhật) dữ liệu sẵn có.

- DELETE : Được dùng khi bạn muốn loại bỏ (hoặc xóa) dữ liệu sẵn có.

- REPLACE : Được dùng khi bạn muốn thêm hoặc thay đổi (hoặc đổi chỗ) dữ liệu mới hoặc dữ liệu đã có.

- TRUNCATE : Được sử dụng khi bạn muốn làm trống hay xóa tất cả dữ liệu từ mẫu.

**Tạo database , user và set quyền user**

- Để tạo được một database trước tiên chúng ta phải đăng nhập vào mysql bằng câu lệnh

> mysql -u root -p <br/>

sau đó điền password để tiếp tục:

![image](http://www.upsieutoc.com/images/2015/10/29/tuan71.png)

- sau đó sử dụng câu lệnh tạo database

> create database "tên database";<br/>

![image](http://www.upsieutoc.com/images/2015/10/29/tuan72.png)

- dùng lệnh show để xem chúng ta hiện đang có những database nào : 

> show databases;

![image](http://www.upsieutoc.com/images/2015/10/29/tuan73.png)

*set quyền user*

- Trong mySQL chúng ta có các quyền thuộc về user như sau :
 * all : tất cả các quyền <user root>
 * create : cho phép tạo mới table hoặc database
 * drop : cho phép xóa table hoặc database
 * delete : cho phép xóa dữ liệu trong bản ghi table
 * insert : cho phép thêm bản ghi mới vào bảng csdl
 * select : cho phép sử dụng lệnh select để tìm kiếm dữ liệu
 * update : cho phép cập nhật cơ sở dữ liệu
 * grant option : cho phép gán hoặc xóa quyền của người dùng khác.

- Để thiết lập quyền cho user ta dùng câu lệnh :

> grant Quyền on dbname.* to username@localhost;

![image](http://www.upsieutoc.com/images/2015/10/29/tuan74.png)

- sau khi thiết lập quyền cho user xong ta tiến hành đặt password và kiểm tra lại :

> set password for root@localhost password=('******')<br/>
> show databases;

![image](http://www.upsieutoc.com/images/2015/10/29/tuan75.png)




**Sự khác nhau giữa wordpress và joomla**

*Wordpress*

- Wordpress rất dễ sử dụng, chúng ta có thể tạo blog tạo trang wordpress chỉ trong vài phút.

- Wordpress hỗ trợ SEO khá tốt.

- Wordpress hoạt động rất nhẹ nhàng và ít tốn tài nguyên.

- Wordpress thích hợp cho các trang blog và xuất bản nội dung kiểu nhóm nhỏ.

*Joomla*

- Joomla có thể xây dựng các website từ nhỏ đến lớn vừa.

- Giao diện của Joomla rất đẹp được cung cấp bởi nhiều công ty cả miễn phí đến mang tính chất thương mại.

- Joomla có các viện ứng dụng (extensions) khổng lồ được thiết kế bởi nhiều lập trình viên trên thế giới và hầu hết là miễn phí. Tuy nhiên việc các ứng dụng được thiết kế bởi nhiều lập trình viên như thế sẽ dẫn tối các lỗi bảo mật tiềm tàng , chúng ta có giải pháp bảo mật cho các extensions này nhưng phải trả phí.

- Khả năng SEO của Joomla rất là kém.

- Không chạy tốt trên máy chủ Window.

- Mã nguồn tương đối lớn dẫn đến chiếm dụng nhiều tài nguyên của hệ thống.

