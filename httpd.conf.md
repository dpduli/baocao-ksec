##Công việc tuần 6

**Tìm hiểu về file cấu hình httpd.conf**

- Trong file config chúng ta có những file sample value đặc trưng như :

1. MinSpareServers 5
2. MaxSpareServers 10
3. Keepalive off/on
4. ServerLimit
5. MaxClient
6. MaxRequestsPerChild
7. Timeout

- MaxSpareServer và MinSpareSever kiểm soát xem có bao nhiêu process rảnh rỗi của apache sẽ giữ cho nó còn sống trong khi chờ đợi thêm các request có thêm các yêu cầu đề đưa vào sử dụng. Mỗi child process tiêu thụ các nguồn tài nguyên do đó các maxspareservers đặt quá cao sẽ gay ảnh hường đến vấn đề tài nguyên, còn nếu số lượng máy chủ không sử dụng giảm xuống dưới minspareservers thì apache sẽ phân nhánh tới khi Minspareserver hài lòng.

- Keepalive : là một tính năng của http 1.1 cho phép truyền sữ liệu qua một kết nối duy nhất, kết nối này sẽ đóng sau một khoảng thời gian timeout nào đó không có dữ liệu nào hoặc tổng số lần truyền đặt tới một maximum nào đó.

- MaxKeepAlive Request : là số lượng request tối đa được truyền trong một conection. giá trị của Maxkeepaliverequest có thể đc thay đổi , nên thay đổi số này lớn hơn số resoure tải cùng mà chúng ta ước lượng.

- Keepalive Timeout: Là số giây timeout nếu không có request nào tiếp theo thì connection sẽ được đóng. Nên giữ giái trị này từ 3-5s trong cấu hình mặc định của nó là 300s.

*Đối với prefork*

- serverlimit : là số process tối đa được tạo ra <Mỗi process phục vụ cho một request>.

- Maxclients : tương tự như serverlimit nhưng con số này nhỏ hơn hoặc bằng serverlimit.

- MaxRequestsPerChild : Là số request mà mỗi process sẽ phục vụ trc khi kết thúc, nếu để là 0 thì process sẽ chạy mãi mãi.

*Đối với worker*

- Serverlimit : là số process tối đa được phép tạo ra.

- Thread process: Là số thread tối đa trong mỗi process.

- ThreadsPerChild : là số thread tối đa trong mỗi process.

- MaxClient : là số thread tối đa được tạo, Mỗi thread phục vụ cho một process. Lưu ý rằng MaxClients phải là bội số của ThreadsPerChild và phải nhỏ hơn hoặc bằng ServerLimit x ThreadsPerChild. Ví dụ ServerLimit là 8, ThreadsPerChild là 128 thì MaxClients tối đa là 1024. 

- MaxRequestsPerChild số requests tối đa được phục vụ của mỗi thread, sau khi đạt được số này, thread sẽ bị killed để tạo thread khác.
