#Bài tập Dịch vụ mạng.

##Bài số 7.

**Đề bài**

![scr1](http://i.imgur.com/d7M7a3ml.png)

**Thực hiện**

![scr4](http://i.imgur.com/Lei4LXpl.png)

- Trước tiên chúng ta cấu hình tên cho Router + địa chỉ IP:

```sh
Router(config)#hostname R1
R1(config)#interface f0/0
R1(config-if)#ip address 172.16.2.2
R1(config-if)#ip address 172.16.2.2 255.255.255.0
R1(config-if)#no shutdown
```

- Cấu hình domain name và thiết lập user password:

```sh
R1(config)#ip domain-name datpt
R1(config)#username datpt secret anhdat96
```

- Tạo Crypto key:

```sh
R1(config)#crypto key generate rsa
How many bits in the modulus [512]: 1024
```

- Thiết lập truy cập:

```sh
R1(config)#line vty 0 4
R1(config-line)#transport input ssh // CHỉ cho phép truy cập bằng SSH
R1(config-line)#login local
R1(config-line)#exit
R1(config)#enable secret anhdat96 // password để truy cập vào enable
```

- Thiết lập số lần xác thực và thời gian:

```sh
R1(config)#ip ssh authentication-retries 5
R1(config)#ip ssh time-out 40
```

- Cấu hình địa chỉ IP trên PC:

![scr2](http://i.imgur.com/PnQOc4Rl.png)

- Mở `Command prompt` trên PC và thực hiện test:

![scr3](http://i.imgur.com/Mwm9tUkl.png)



