##Công việc tuần 5

**Nguyên tắc xử lý của webserver**

- webserver : máy chủ mà trên đó cài đặt phần mềm chạy website . Đôi khi người ta cũng gọi nó là phần mềm chạy webserver. tất cả các webserver đều chạy đc các file như *.html, *.htm. Tuy nhiên mỗi websever lại phục vụ cho một số kiểu file chuyên biệt chẳng hạn như ISS của microsoft dành cho *.aspx, *.asp,... Apache dành cho *.php ,... 

- Nguyên tắc hoạt động của Webserver

![image](http://www.upsieutoc.com/images/2015/10/17/cvt51.png)

- Khi webserver nhận một yêu cầu từ web browser, nó sẽ ánh xạ đường dẫn URL (ví dụ : abcxyz.com.vn) thành một tập tin cục bộ trên máy web server.

- Máy chủ sau đó tự nạp thông tin đó qua mạng đến web browser của người dùng.

- Web browser và web server dùng giao thức http trong quá trình trao đổi dữ liệu.

*cơ chế nhận kết nối*

- Với phiên bản đầu tiên, webserver hoạt động theo mô hình sau:
 * Tiếp nhận các yêu cầu từ webbrowser
 * Trích nội dung từ đĩa
 * chạy các chương trình CGI
 * Truyền dữ liệu ngược lại cho client.

- Tuy vậy cách hoạt động của mô hình không hoàn toàn tương thích lẫn nhau. Một webserver đơn giản phải theo các các luật logic sau :
 * Chấp nhận kết nối
 * Sinh ra các nội dung tĩnh hoặc động cho browser
 * Đóng kết nối
 * Chấp nhận kết nối
 * Lập lại quá trình trên.

- Điều này sẽ chạy tốt đói vs những website đơn giản, nhưng server sẽ bắt đầu gặp phải vấn đề do có nhiều người truy cập hoặc có quá nhiều trang web động phải tốn thời gian tính toán để cho ra kết quả.

- Webserver có xu hướng tận dụng ưu điểm của hai phương pháp khác nhau để giải quyết vấn đề này là : đa tiến trình hoặc đa tiểu trình hoặc các hệ lai giữa chúng.
