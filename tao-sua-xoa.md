##Công việc tuần 3

**Tạo sửa xóa user, group**

- Ubuntu là hệ điều hành đa người dùng vì thế mỗi người muốn sử dụng được máy đều phải có một account . Một account bao gồm Username và password.

- có 2 loại user là super user và regular user. Để tạo một người dùng mới, thay đổi thuộc tính của một người dùng hay xóa bỏ một người dùng  chỉ khi có quyền của một super user. Mỗi user có một định danh riêng là UID.

- cách kiểm tra UID ta gõ lệnh "sudo cat /etc/passwd". File nàu lưu trữ tất cả các thông tin về user như sau:

![image](http://www.upsieutoc.com/images/2015/10/03/cv31.png)

- Trong đó mỗi user nằm trên một dòng bao gồm các trường : Tên tào khoản, mật khẩu (đã được mã hóa) , UID , GID , Tên đầy đủ của người sử dụng, thư mục home và shell đăng nhập.

- Một số UID đặc biệt : UID = 0 (được gán co tài khoản root là super user), UID = 65534 (là tài khoản người dùng), UID từ 1 đến 99 (Được dùng cho các tài khoản dịch vụ).

- Để tạo một user mới ta dùng cú pháp useradd [tùy chọn] "tên người dùng"

- Các tùy chọn :

  * -d/home_directory: tạo thư mục home cho người dùng.
  * -g group: xác định tài khoản người dùng thuộc nhóm người dùng nào trên hệ thống.
  *  -e date: xác định ngày mà tài khoản bị vô hiệu hóa trên hệ thống.
  *  -G groups: các định tài khoản người dùng thuộc những nhóm người dùng nào trên hệ thống.
  *  -s shell: xác định shell mặc định của người dùng khi đăng nhập vào hệ thống.
  *  -u uid: xác định số user id của ngwofi dùng.

- Để xóa một tài khoản người dùng ta sử dụng câu lệnh: userdel [tùy chọn] "tên người dùng". trong câu lệnh xóa ta có thể thêm tùy chọn "option -r" để xóa thư mục home của người dùng và các file trong thư mục home.

- Chỉnh sửa một tài khoản ta sử dụng cú pháp: usermod [tùy chọn] "tên người dùng". Ta dùng các tùy chọn như phần useradd để sửa những thông số tương ứng như thư mục home, ngày tài khoản bị vô hiệu hóa,....

- Thông tin lưu trữ nhóm người dùng xem bởi lệnh "sudo cat /etc/group"

![image](http://www.upsieutoc.com/images/2015/10/03/cv32.png)

- Mỗi nhóm người dùng , mật khẩu, số group id, và các thành viên của nhóm được lưu trữ trong file này.

- Để tạo một nhóm người dùng mới ta dùng cú pháp: # groupadd [tùy chọn] "tên nhóm người dùng"

- Ta có các tùy chọn như sau :

 * -g gid: Đặt số group id cho nhóm người dùng.
 * -f: Bắt câu lệnh chạy mà không thông báo lỗi nếu đã có một nhóm trên hệ thống trùng với tên nhóm đinh tạo .

- Để xóa một group ta sử dụng câu lệnh: # groupdel "tên nhóm"

- Để chỉnh sửa một nhóm ta sử dụng câu lệnh # groupmod [tùy chọn] "tên nhóm". chức năng của lệnh groupmod giống chức năng của usermod.
