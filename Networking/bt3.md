#Bài tập môn dịch vụ mạng.

##Bài tập số 3.

###Mô hình số 1.

- Như những bài trước bài này mình cũng lấy mô hình giống của thầy, còn số liệu mình sẽ thay đổi theo của mình.

- Đây là mô hình của đề bài :

![scr1](http://i.imgur.com/9G8VBau.png)

```sh
Lưu ý: Trong đề bài mà thầy cho tất cả đều là /8 nhé :D
```

- Còn đây là mô hình của mình : 

![scr3](http://i.imgur.com/gWtwOgC.png)

**Lưu ý** khi vẽ mô hình

 Các bạn sẽ bị thiếu port ở Router vì thế trước khi nối dây các bạn phải thêm cổng vào như hình :

![scr2](http://i.imgur.com/RNdPx4P.png)

- OK chúng ta bắt đầu đi vào cấu hình theo đề bài :D

- Đầu tiên chúng ta cấu hình địa chỉ IP cho Router :

```sh
Router(config)#interface f0/0
Router(config-if)#ip address 172.16.1.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface f1/0
Router(config-if)#ip address 172.16.2.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface f4/0
Router(config-if)#ip address 172.16.3.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
```

- OK , bước tiếp theo chúng ta đi vào cấu hình WEB-server :

- Đầu tiên là cấu hình địa chỉ IP cho Web-server.

![scr4](http://i.imgur.com/i8VnbvA.png)

```sh
IP address // là địa chỉ của web-server
Subnetmask // là subnet của dải mạng
Default gateway // là địa chỉ gateway của dải mạng đó
DNS server // là địa chỉ của DNS server , ở đây mình đặt DNS server là 172.16.2.10 nhưng chưa cấu hình ở DNS server.
```

- Sau đó vào phần `config` để bật dịch vụ web HTTP lên, mặc định là bật rồi. Chúng ta có thể chỉnh sửa trang web ngay tại đây.

![scr5](http://i.imgur.com/5qhXv3F.png)

- Tiếp theo là cấu hình DNS server :

- Đầu tiên là cấu hình địa chỉ DNS server :

![scr6](http://i.imgur.com/dOyoY4C.png)

- Sau đó thiết lập DNS:

![scr7](http://i.imgur.com/BQVsHyL.png)

- Thêm vào một tên miền bất kì với address là địa chỉ của web-server sau đó lưu lại và bật dịch vụ DNS lên.

- Sau đó cấu hình máy chủ DHCP .

- Đặt địa chỉ IP cho DHCP server

![scr8](http://i.imgur.com/ZpwrDpI.png)

- Thiết lập DHCP 

![scr9](http://i.imgur.com/HyJn7Jk.png)

- Bật DHCP trên host để lấy địa chỉ :

![scr10](http://i.imgur.com/GGwgNyR.png)

- Thực hiện kiểm tra cấu hình , mọi người cứ gửi 2 gói để check nhé :D , gửi gói đầu tiên nó thường ko nhận được.

![scr11](http://i.imgur.com/V9LKEKp.png)

- Check thử xem DNS và Web-server đã ngon chưa , ta vào bằng 1 máy bất kì rồi chọn `web browser`

![scr12](http://i.imgur.com/Lmu61H5.png)

- Sau đó nhập địa chỉ và kiểm tra thành quả :D

![scr13](http://i.imgur.com/HWE2hV8.png)