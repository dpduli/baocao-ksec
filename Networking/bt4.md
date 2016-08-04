#Bài tập môn dịch vụ mạng.

##Bài số 4.

###Mô hình 1.

- Bài này khá dễ và không phải cấu hình nhiều, thao tác tay là chính , khá đơn giản và hay :D

- Mô hình thầy cho :

![scr1](http://i.imgur.com/QxYl3Ji.png)

- Mô hình của mình :

![scr2](http://i.imgur.com/Jrhe5l5.png)

```sh
Lưu ý nhỏ là trước khi nối dây mọi người nên thêm port cho con switch như hình :
```

![](http://i.imgur.com/iupwhr1.png)

- Bắt đầu cấu hình DHCP (như các bài trước)

- Cấu hình webserver (như bài trước)

- Cấu hình Mail-server:

```sh
 Sau khi cấu hình địa chỉ IP cho mail server chúng ta tiếp tục thực hiện như sau :
```

![scr3](http://i.imgur.com/hRiVZTj.png)

```sh
Domain name // là vị trí sau @ ví dụ như @gmail.com thì ở đây là @kma.com
User //tên đăng nhập cũng như là vị trí trước @ , ở đây là datpt@kma.com
Password // pass để đăng nhập 
Sau khi hoàn tất ấn dấu cộng (+) để hoàn tất tạo tài khoản (làm vài user tí còn test)
```

![scr4](http://i.imgur.com/PgXPxy8.png)

```sh
Tiếp theo chúng ta thực hiện cấu hình cho con DNS
Đầu tiên là đặt địa chỉ IP cho nó
Sau đó thiết lập Domain cho web server cũng như Mail
```

![scr5](http://i.imgur.com/0jLufaf.png)

- OK đã hoàn tất test chức năng gửi Mail nữa thôi :D

- Đầu tiên ta lấy 1 con PC bất kỳ để sử dụng chức năng Mail :

![scr6](http://i.imgur.com/Ch1UDVH.png)

- Đây là màn hình đăng nhập của Mail :

![scr7](http://i.imgur.com/lX712N9.png)

```sh
Your Name // tên của bạn, điền bất kỳ.
Email address // Địa chỉ email
Incoming Mail server // điền domain của mail server là được vì ở đây chỉ có 1 mail server
Outgoing Mail server // điền domain của mail server là được vì ở đây chỉ có 1 mail server
User name // là user lúc tạo ở Mail server
Password // :D
Sau đó nhấn Save và xem nó như nào thôi :D
```

![scr8](http://i.imgur.com/hh5lPmw.png)

- Để gửi mail chúng ta ấn vào `Compose` để bắt đầu tại mail.

![scr9](http://i.imgur.com/91s4LTV.png)

- Điền thông tin rồi send thôi :D

- Chúng ta lại lấy 1 con PC khác để đăng nhập vào mail `tienbiu@kma.com`

![scr10](http://i.imgur.com/knZeljv.png)

- Chúc mọi người thành công :D

###Mô hình 2:

- Không có gì đặc biệt cả, cấu hình bình thường sau đó định tuyến bằng `RIPv2` là OK.

- Đề bài :

![scr1](http://i.imgur.com/GYV9N7A.png)