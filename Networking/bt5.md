#Bài tập môn dịch vụ mạng.

##Bài tập số 5.

**Đề bài**

![scr1](http://i.imgur.com/8s5JYBAl.png)

**Thực hiện**

![scr2](http://i.imgur.com/LhU0yftl.png)

- OK bắt đầu chúng ta cấu hình địa chỉ IP cho router. Vì router đóng vai trò định tuyến cho nên các cổng thuộc router phải để là 
gateway (Ví dụ mạng là 10.10.10.0/24 thì đặt địa chỉ cho cổng trên router là 10.10.10.1/24)

```sh
Router(config)#interface f1/0
Router(config-if)#ip address 172.16.2.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface f0/0
Router(config-if)#ip address 172.16.3.1 255.255.255.0
Router(config-if)#no shutdown
```

- Tiếp theo là cấu hình cho DNS server:

- Đặt địa chỉ cho DNS:

![scr3](http://i.imgur.com/tqFZTHnl.png)

- Cấu hình DNS:

![scr4](http://i.imgur.com/r4HxqEvl.png)

- Cấu hình cho FTP server.

- Cấu hình địa chỉ IP :

![scr5](http://i.imgur.com/8P9Qc3dl.png)

- Cấu hình dịch vụ FTP, cụ thể ở đây là tạo user và ủy quyền cho user:

![scr6](http://i.imgur.com/TfgPVp5l.png)

- Đặt địa chỉ cho PC và thực hiện ping kiểm tra :

![scr7](http://i.imgur.com/PDHYrHUl.png)

- OK bây giờ chúng ta vào `Command prompt` để thực hiện truy cập bằng ftp:

![scr8](http://i.imgur.com/ZW1Mf2Al.png)

![scr9](http://i.imgur.com/cPI4LaRl.png)