#Bài tập môn dịch vụ mạng.

##Bài số 6.

**Đề bài**

![scr1](http://i.imgur.com/HzhShLbl.png)

**Thực hiện**

![scr2](http://i.imgur.com/1a3Eqeil.png)

- Thực hiện cấu hình trên Router 1:

```sh
Router(config)#interface f0/0
Router(config-if)#ip address 172.16.3.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface s2/0
Router(config-if)#ip address 172.16.1.3 255.255.255.0
Router(config-if)#clock rate 64000
Router(config-if)#no shutdown
```

- Thực hiện cấu hình trên Router 2:

```sh
Router(config)#interface f0/0
Router(config-if)#ip address 172.16.2.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#exit
Router(config)#interface s2/0
Router(config-if)#ip address 172.16.1.2 255.255.255.0
Router(config-if)#no shutdown
```

- Tiến hành định tuyến trên 2 Router:

Tại Router 1:

```sh
Router(config)#router rip
Router(config-router)#version 2
Router(config-router)#network 172.16.1.0
Router(config-router)#network 172.16.3.0
Router(config-router)#no auto-summary
```

Tại Router 2:

```sh
Router(config)#router rip
Router(config-router)#version 2
Router(config-router)#network 172.16.1.0
Router(config-router)#network 172.16.2.0
Router(config-router)#no auto-summary
```

- Cấu hình cho PC client dùng để truy cập telnet vào R1:

![scr3](http://i.imgur.com/J1oZAGjl.png)

- Thực hiện kiểm tra xem client và Router đã thông chưa?

![scr4](http://i.imgur.com/oFFYDghl.png)

- Cấu hình cho phép telnet trên Router 1:

```sh
Router(config)#line vty 0 4 //Mở 5 cổng từ 0-4 để telnet từ xa
Router(config-line)#password anhdat96 // đặt password khi yêu cầu truy cập từ xa
Router(config-line)#login // Yêu cầu nhập password khi truy cập
Router(config-line)#exit
Router(config)#enable secret anhdat96 // Đặt password đảm bảo bảo mật để có thể truy cập vào enable trong Router.
```

- Tiến hành telnet bằng `Command prompt` trên PC:

![scr5](http://i.imgur.com/PhQr0m9l.png)

- Vào router xem có sự thay đổi không?

![scr6](http://i.imgur.com/qK3DtWtl.png)