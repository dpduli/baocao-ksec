##Công việc tuần 3

**Phân quyền File, User**

- Trong Linux khi phân quyền có 3 quyền hạn cơ bản đó là Read (đọc), Write (ghi), Execute (chạy) để phân quyền cho 3 nhóm đối tượng gồm : Chủ hệ thống, nhóm quản trị và người dùng.

- Mỗi đặc quyền truy cập tương ứng với một trị số 

 * Read - r = 4
 * Write - w = 2
 * execute - x = 1

- Cách biểu diễn [user] [group] [anybody]

 * [user] : quyền của file.
 * [group] : quyền của các user trong group này
 * [anybody] : quyền của các user không nằm trong group này.

- ví dụ ls -al

![image](http://www.upsieutoc.com/images/2015/10/03/cv33.png)

 + với rw------- datkma datkma. có thể biểu diễn dưới dạng số như sau 600. có thể hiểu là user datkma có quyền đọc và viết. các user trong group datkma ko có quyền đọc viết cx như truy nhập, các user ngoài group cũng không có quyền đọc viết hay truy cập.

*Các kiểu phân quyền File : CHMOD và CHOWN*

- Cấu trúc câu lệnh CHMOD : "chmod [tùy chọn] [biểu diễn phân quyền] [tên file hoặc thư mục]"

- Ta có các tùy chọn sau (không bắt buộc)

 * -v : Hiển thị báo cáo sau khi chạy lệnh.
 * -c : hiển thị báo cáo nhưng khi đã thực hiện xong tất cả.
 * -f : Có lỗi xảy ra cũng không thông báo.
 * -R : Áp dụng cho cả file và thư mục con.
 * -help : hiển thị thông báo trợ giúp.

- Một số lệnh phân quyền CHMOD thường gặp:

 * chmod 777 "tên file": cấp quyền truy cập đầy đủ cho mọi đối tượng người dùng.
 * chmod 775 "tên file": cấp quyền truy cập đầy đủ cho hệ thống và nhóm quản trị, đối tượng người dùng chỉ có quyền đọc (read) và chạy (execute) file.
 * chmod 755 "tên file": Cấp quyền truy cập đầy đủ cho chủ hệ thống, chỉ cho phép nhóm quản trị và đối tượng người dùng đọc và chạy các file trong thư mục.
 * chmod 700 "tên file": Chỉ cấp quyền truy cập đầy đủ cho chủ hệ thống và chặn truy cập với mọi đối tượng khác.
 * chmod 500 "tên file": Không cho phép nhóm quản trị và người dùng truy cập vào file trong thư mục, đồng thời giới hạn quyền chủ hệ thống chỉ đọc và chạy để tránh xóa và thay đổi các file trong thư mục này.
 * chmod 660 "ten file": Cho phép chủ hệ thống và nhóm quản trị đọc, sửa, xóa và ghi dữ liệu vào file, nhưng không phân quyền truy cập cho những người dùng khác.

- CHOWN thay đổi chủ sở hữu của File.
 * Để đổi chủ sở hữu cho file thì ta sử dụng câu lệnh: "chown -R [tên user]:[tên group] [file/folder]"

**Các câu lệnh tạo sửa xóa File/Folder**

ls: lấy danh sách tất cả các file và folder trong folder hiện hành.

pwd: xuất đường dẫn của folder làm việc.

cd: thay đổi folder làm việc đến một folder mới.

mkdir: tạo folder mới.

rmdir: xoá folder rỗng.

cp: copy một hay nhiều file đến folder mới.

mv: đổi tên hay di chuyển file, folder.

rm: xóa file.

wc: đếm số dòng, số kí tự... trong file.

touch: tạo file.

cat: xem nội dung file.

vi: khởi động trình soạn thảo văn bản vi.

tar -tzf backup.tar.gz: liệt kê file nén gz.

tar -xvf archive.tar: giải nén một file tar.

wget: download file.

