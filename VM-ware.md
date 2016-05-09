#Bài báo cáo về thiết lập IP tĩnh, IP động và cách thiết lập 2 card mạng trên Ubuntu server.

****

- Mục lục
 <ul>
 <li>[I. Cấu hình địa chỉ IP]  (#phan1)</li>
  <ul>
  <li>[1.1 Cấu hình địa chỉ IP tĩnh.]  (#phan3)</li>
  <li>[1.2 Cấu hình địa chỉ IP động.]  (#phan4)</li>
 </ul>
 <li>[II. Thiết lập 2 card mạng cho máy Ubuntu server]  (#phan2)</li>
 </ul>

****

<a name="phan1"></a>
###I. Cấu hình địa chỉ IP 

- Chúng ta có các cách cơ bản để cấu hình địa chỉ IP như sau:

 <ul>
 <li>Cấu hình địa chỉ IP tạm thời (sẽ mất sau khi chúng ta reboot)</li>
 <li>Cấu hình IP tĩnh (Vẫn giữ nguyên địa chỉ IP sau khi reboot)</li>
 <li>Cấu hình địa chỉ IP động (Nhận địa chỉ IP tự động từ DHCP server)</li>
 </ul>

<a name="phan3"></a>
###1.1 Cấu hình địa chỉ IP tĩnh.

Trước khi cấu hình địa chỉ IP tĩnh chúng ta cần chỉnh sửa lại một chút thông số trong dải mạng của VMware. Trước tiên chúng ta tạo một switch ảo có dải mạng dễ nhớ để trong khi làm việc chúng ta có thể làm nhanh và thuận tiện hơn.

<img src="http://i.imgur.com/PK2dfgv.png" />


Sau đó chúng ta chỉnh cho máy ảo dùng dải mạng mà chúng ta vừa tạo. Để chỉnh sửa chúng ta chọn vào máy chủ , nhấn chuột phải chọn setting => Network adapter. Sau đó chỉnh sửa thông số thành `Custom : specific vitual network` và chọn switch mà bạn đã tạo trước đó. Ở đây tôi chọn VMnet2.

![Screenshot_2.png](http://www.upsieutoc.com/images/2016/04/13/Screenshot_2.png)


Sau đó chúng ta khởi động máy chủ lên và tiến hành cấu hình địa chỉ IP tĩnh cho máy ảo.

Để cấu hình địa chỉ IP cho máy ảo chúng ta cần dùng đến một trong những trình soạn thảo mà Linux đã cung cấp đó là vi, gedit, nano,... Ở đây tôi chọn Vi.

Để tiến hành cấu hình địa chỉ IP tĩnh chúng ta mở file interface của máy lên bằng câu kệnh `sudo vi /etc/network/enterfaces` . Khi đó chúng ta sẽ thấy file cấu hình.

![Screenshot_3.png](http://www.upsieutoc.com/images/2016/04/13/Screenshot_3.png)


Sửa lại file cấu hình . Lưu ý dòng `iface eth0 inet dhcp` chúng ta phải đổi thành `iface eth0 inet static` sau đó thêm các thông số nữa (như hình bên dưới). Address, netmask phải thuộc dải mạng mà chúng ta đã cấu hình cho switch.

![Screenshot_4.png](http://www.upsieutoc.com/images/2016/04/13/Screenshot_4.png)

Sau khi đã hoàn tất chỉnh sửa chúng ta lưu file lại và thoát ra. Khởi động lại dịch vụ (để lấy cấu hình mới) bằng câu lệnh `sudo /etc/init.d/networking restart`. và tiếp đó chúng ta tắt mở cấu hình mạng để lấy cấu hình hiện tại bằng câu lệnh : tắt `sudo ifdown eth0` và mở `sudo ifup eth0` . Sau đó chúng ta kiểm tra lại xem đại chỉ IP đã đúng với những gì chúng ta cài đặt chưa.

Dưới đây là kết quả sau khi thực hiện các bước cấu hình IP tĩnh.

![Screenshot_5.png](http://www.upsieutoc.com/images/2016/04/13/Screenshot_5.png)

<a name="phan4"></a>
###1.2 Cấu hình địa chỉ IP động.

Mặc định thì file cấu hình của chúng ta đã là file cấu hình địa chỉ IP động rồi, nếu như muốn sử dụng IP động DHCP thì chúng ta không cần phải chỉnh sửa gì ở file `/etc/network/interfaces` nữa.

<a name="phan2"></a>
#II. ADD 2 card mạng cho máy chủ Ubuntu server và cấu hình cho 2 card mạng.

Để add 2 card mạng cho máy chủ ubuntu chúng ta kích chuột phải vào máy ảo đó chọn setting => add => network adapter => chọn custom và chọn VMnet mà chúng ta muốn add. Sau khi add xong máy của chúng ta sẽ có 2 card mạng như hình dưới

![Screenshot_6.png](http://www.upsieutoc.com/images/2016/04/13/Screenshot_6.png)


Bây giờ tiến hành cấu hình cho 2 card mạng ở file `/etc/network/interfaces` , file cấu hình như sau.

![Screenshot_7.png](http://www.upsieutoc.com/images/2016/04/13/Screenshot_7.png)


Sau khi đã cấu hình xong chúng ta lưu file lại và reset lại dịch vụ cũng như mở eth0 và eth1 . Như thế chúng ta đã cấu hình thành công 2 card mạng cho máy ubuntu server.

![Screenshot_8.png](http://www.upsieutoc.com/images/2016/04/13/Screenshot_8.png)
