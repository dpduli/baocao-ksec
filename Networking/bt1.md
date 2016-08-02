#Bài tập Dịch Vụ Mạng.

##Bài tập 1.

###1. Mô hình 1.

![scr1](http://i.imgur.com/XJD2uzd.png)

**Thực hiện**

- Đầu tiên mở `Packet Tracer` lên và chọn các thiết bị như mô hình :

![scr2](http://i.imgur.com/buS4vpG.png)

- Tiếp theo chọn vào server , vào mục `config` rồi `DHCP` và thiết lập.

![scr3](http://i.imgur.com/ptKpNwS.png)

- Sau đó chúng chúng ta thiết lập những thông số như hình sau đây : 

![scr4](http://i.imgur.com/EYSJ9VR.png)

- Các bước :
 <ul>
  <li>Cần phải bật server DHCP</li>
  <li>Địa chỉ default gatewate của địa chỉ mạng bạn dự định đặt</li>
  <li>Địa chỉ bắt đầu của dải và subnetmask</li>
  <li>Số lượng địa chỉ cấp phát tối đa</li>
  <li>Sau đó Lưu lại thiết lập</li>
 </ul>

 - Bước tiếp theo chọn mục `desktop` rồi chọn `IP configuration`

 ![scr5](http://i.imgur.com/Ti5RUb0.png)

 - Sau đó thiết lập như hình sau :

 ![scr6](http://i.imgur.com/Nwsw4eW.png)

- Trong đó:
 <ul>
  <li>IP address : là địa chỉ của DHCP server</li>
  <li>Subnetmask : là subnet của dải mạng bạn đặt</li>
  <li>Default gateway: :D</li>
  <li>DNS server: Đặt là 0.0.0.0</li>
 </ul>

- Bây giờ thiết lập nhận địa chỉ cấp phát tự động (DHCP) trên các PC . Thực hiện như sau : 

  Đầu tiên chọn vào con PC sau đó chọn mục `desktop` rồi chọn `IP configuration`

  ![scr7](http://i.imgur.com/rFHvsHv.png)

  Sau đó chọn DHCP nếu báo successful là thành công.

  ![scr8](http://i.imgur.com/ps2FsYl.png)

  Thực hiện `Ping` hoặc gửi `Gói tin PDU` để kiểm tra :D


###Mô hình 2:

![scr9](http://i.imgur.com/pp88gFd.png)

- Đối với mô hình dùng wireless device chúng ta thực hiện như sau .
 
  Đầu tiên vẫn là thực hiện chọn các thiết bị như mô hình đề bài cho :D

![scr11](http://i.imgur.com/q8kHVkz.png)

  Sau đó : 
     
     CHọn vào thằng Linksys rồi sau đó chọn `GUI` (dùng trình duyệt web để truy cập vào quản lý device với user : admin và pass admin)

     Thiết lập như hình sau :

![scr10](http://i.imgur.com/i6yGV4D.png)
 
      Các giá trị thì như mô hình 1 đã giải thích . Tiếp đó kéo xuống ấn vào `savechange`

      Tiếp đến chúng ta phải bật wireless trên laptop để có thể nhận đc cấu hình từ động từ wireless device

      Thực hiện như sau :

 - Ấn vào laptop và tắt nó đi đồng thời gỡ thiết bị `CGE` trả về vị trí của nó :

 ![scr12](http://i.imgur.com/eP5Eiws.png)

 - Sau đó chọn thiết bị `Linksys` gắn vào :

 ![scr13](http://i.imgur.com/w2CbIot.png)

 - Tiếp theo bật laptop lên để nhận cấu hình từ wiless device:

 ![scr14](http://i.imgur.com/szM8Txm.png)

 - Khi thiết lập xong latop sẽ kết nối với wireless cũng như nhận địa chỉ như sau :

 ![scr15](http://i.imgur.com/Tp9CdJX.png)

 - Chúc mọi người thành công :D


