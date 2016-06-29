#Ksec Club - An Toàn Hệ Điều Hành.

****

##Mục lục.
[I. Hệ điều hành là gì?] (#hdh)
[II. Một số khái niệm căn bản] (#kn)
[III. Tính cần thiết của một HĐH an toàn] (#canthiet)
[IV. An toàn trong Linux server] (#linux)
 <ul>
 <li>[1. Firewall] (#filewall)</li>
 <li>[2. Iptables] (#iptables)</li>
 <li>[3. SElinux] (#selinux)</li>
 <li>[4. Các vấn đề về install] (#install)</li>
 <li>[5. Giới hạn nguồn hệ thống] (#gioihan)</li>
 </ul>

****
<a name="hdh"></a>
#I. Hệ điều hành là gì?

- Hệ điều hành là một phần mềm chạy trên máy tính, dùng để điều hành, quản lý các thiết bị phần cứng và các tài nguyên phần mềm trên máy tính.
- Hệ điều hành đóng vai trò trung gian trong việc giao tiếp giữa người sử dụng và phần cứng máy tính, cung cấp một môi trường cho phép người sử dụng phát triển và thực hiện các ứng dụng của họ một cách dễ dàng.

<a name="kn"></a>
#II. Một số khái niệm căn bản.

- HĐH an toàn (SOS) : là tập hợp các cơ chế về phần cứng, phần mềm nhầm đảm bảo tính toàn vẹn, bảo mật và sẵn sàn. Nó đề cập chi tiết đến các bước, biện pháp được sử dụng để bảo vệ HĐH trước các mối đe dọa.
- Xác thực (authen) : Là hành động xác minh nhằm xác định được vai trò của một máy trạm hoặc user nào đó truy cập vào tài nguyên mà HĐH quản lý.
- Truy cập (Access) : Là kiểu tương tác riêng giữa các chủ thể và đối tượng dẫn tới luồng thông tin chạy từ thực thể này tới thực thể kia.
- Danh sách kiểm soát truy nhập (ACL) : Là danh sách các thực thể và các quyền truy nhập của họ được phép truy nhập vào một tài nguyên nào đó.
- Dịch vụ an toàn (SS) : các dịch vụ do một tầng của hệ thống truyền thông mở cung cấp, nó đảm bảo an toàn đầy đủ cho các hệ thống hoặc các phiên truyền dữ liệu.

<a name="canthiet"></a>
#III. Tính cần thiết của một HĐH an toàn.

- Hệ điều hành là tầng thấp nhất của hệ thống các phần mềm; nó cung cấp sự truy cập đầy đủ tới phần cứng hệ thống; chịu trách nhiệm quản lý/ cấp phát/ chia sẻ/ bảo vệ các tài nguyên. Do vậy, nếu hệ điều hành không hoàn thiện thì tính an toàn của hệ thống bị xâm phạm ở mức độ cao.
- Hệ điều hành thực hiện các chức năng chính như: điều khiển truy cập ứng dụng bộ nhớ; lập lịch cho CPU; điều khiển và cấp phát tài nguyên. Nên an toàn của một hệ thống máy tính phải được gắn liền với một hệ điều hành an toàn.
Bảo vệ thông tin và tài nguyên: các máy tính đơn lẻ hoặc hệ thống mạng lưu giữ, quản lý nhiều thông tin và tài nguyên.Ví dụ thông tin về cơ sở dữ liệu khách hàng, dữ liệu về an ninh quốc phòng. Đó là những nguồn dữ liệu quan trọng cần được bảo vệ.
- Bảo vệ tính riêng tư: hệ thống máy tính có thể lưu giữ các thông tin cá nhân, có ý nghĩa riêng tư. Ví dụ như thông tin tài chính cá nhân là những thông tin quan trọng, nhạy cảm cần được bảo vệ.
- Phát hiện các lỗ hổng và gỡ rối phần mềm: Trong kinh doanh,các hãng sản xuất thiết bị và phần mềm đều có xu hướng đưa sản phẩm ra thị trường một cách nhanh nhất nhằm tăng tính cạnh tranh và phổ biến cho sản phẩm.
- Tổn thất do người dùng: mặc dù các hệ điều hành đều có tính năng an toàn, nhưng do người dùng cấu hình, sử dụng sai dẫn đến việc làm tăng nguy cơ mất an toàn. Có thể do: chưa được đào tạo đầy đủ, thói quen làm việc không tốt, không kiểm tra và đánh giá thường xuyên, chính sách an toàn của tổ chức…

<a name="linux"></a>
#IV. An toàn trong Linux server.
<a name="firewall"></a>
##1. Firewall.

- Firewall là hàng phòng vệ đầu tiên chống lại những attacker xâm nhập.
- Nó tập hợp những thủ thuật giúp ngăn chặn ý đồ xâm nhập xấu vào hệ thống và lấy cắp thông tin của hệ thống cũng như phá hoại.
- Vì thế luôn luôn phải bật tường lửa trong HĐH.
- Để kích hoạt chức năng tường lửa trong Ubuntu server chúng ta sử dụng lệnh:

```sh
sudo ufw enable
```

![Screenshot_4.png](http://www.upsieutoc.com/images/2016/06/29/Screenshot_4.png)

**Những thiết lập cơ bản cho tường lửa**

-  Ta thiết lập port cho phép lưu lượng SSH đi qua

```sh
sudo ufw allow 22 //Cho phép cả lưu lượng TCp và UDP.
sudo ufw allow 22/tcp //Chỉ cho phép lưu lượng TCP.
sudo ufw allow ssh //kiểm tra trong file "/etc/services" trên hệ thống SSH yêu cầu cho enable nó.
sudo ufw reject out ssh //Chặn lưu lượng SSH ra ngoài mạng.
sudo ufw deny proto tcp from 10.10.10.10 to any port 22 //Từ chối lưu lượng tcp từ địa chỉ này đến port 22 trên máy cục bộ.
sudo ufw status //xe, tất cả những rule được đặt cho firewall
sudo ufw delete reject [rule] //xóa một luật nào đó trên firewall.
sudo ufw reset //đặt lại firewall về chế độ mặc định.
```

- Khi dùng firewall cơ chế `logging` bị vô hiệu hóa mặc định điều này rất nguy hiểm do đó chúng ta cần kích hoạt logging để những thông báo từ tường lửa vẫn được lưu vào syslog.

```sh
sudo ufw logging on
```
<a name="iptables"></a>
##2. Iptables (chặn những kết nối không cần thiết).

- Để đảm bảo an toàn cho hệ thống chúng ta chỉ lên mở những port mà cần thiết sử dụng , còn lại lên chặn hết đi. Để làm được điều này chúng ta sử dụng `IPtables` để thực hiện.
- Để xem danh sách các port chúng ta sử dụng lệnh :

```sh
cat /etc/services
```

- Để chặn hay mở port bất kì chúng ta sử dụng câu lệnh như sau :

```sh
iptables -A [dạng kết nối] --dport [Giá trị port] -j [DROP/ACCEPT]
```

Trong đó
	Dạng kết nối : là INPUT, FORWARD hay OUTPUT
- Ví dụ : Để mở port 80 trên server :

```sh
iptable -A INPUT --dport 80 -j ACCEPT
```

- Để chặn port 80 trên server :

```sh
iptables -A INPUT --dport 80 -j DROP
```
<a name="selinux"></a>
##3. SElinux.

- SELinux (Security-Enhanced Linux) được tạo bởi NSA. Nó giúp chúng ta bảo mật nhân Linux.
- Chúng ta có thể kiểm tra sự hoạt động của SElinux bằng lệnh sau :

```sh
sestatus
```
- Chức năng này cần được khởi động. (Có sẵn trong CentOS và được enable trong quá trình cài đặt.)
- 
<a name="install"></a>
##4. Các vấn đề về install.

- Thông thường chúng ta thường install các package bằng lệnh `apt-get` trong ubuntu cũng như `yum` trong CentOS tuy nhiên cài đặt bằng 2 lệnh này thông thường máy sẽ tải các package từ trên trang chủ về và thiết lập nhiều thông số mặc định cũng như đường dẫn mặc định nếu như attacker tấn công ứng dụng sẽ dễ dàng kiểm soát được ứng dụng mà chúng ta đã built.
- Để hạn chế cũng như làm khó dễ cho attacker chúng ta lên tải file source về rồi cài đặt bằng tay sẽ thiết lập được các đường dẫn cũng như nhiều thông số như thế sẽ gây khó dễ nếu như kẻ xấu có ý đồ tấn công.

<a name="gioihan"></a>
##5. Giới hạn nguồn hệ thống.

- - Mặc định Linux sẽ không sử dụng bất kỳ giới hạn nguồn nào trong các tiến trình của người dùng. Điều này có nghĩa là bất kỳ người dùng nào đều được tự do lấp đầy bộ nhớ làm việc trên máy, hoặc sinh ra các tiến trình lặp vô hạn, trả lại hệ thống không dùng được trong vài giây. Giải pháp khắc phục là thiết lập một số giới hạn nguồn bằng cách chỉnh sửa file “/etc/security/limits.conf”:

```sh
$ sudoedit /etc/security/limits.conf 
```