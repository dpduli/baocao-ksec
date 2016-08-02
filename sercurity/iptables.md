#Chuyên đề về iptables.

##1. Overveiw.

- Iptables là một rule-based-firewall, hoặt động dựa trên nguyên lý xử lý từng nguyên tắc cho đến khi nó tìm thấy nguyên tắc phù hợp.

**Usage**

- iptables là một tiện ích thường được cài đặt sẫn trên các bản distro của Linux, nhưng nó không được chạy bất kỳ một rule nà. Chúng ta có thể tìm thấy nó gần như ở hầu hết các distro.

```sh
/sbin/iptables
```

##2. Các kiến thức cần có để có thể sử dụng iptables.

###a. NAT.

- Hiểu đơn giản NAT là quá trình thay đổi địa chỉ (private) được dùng bên trong mạng sang địa chỉ public.
- NAT còn được coi là một loại firewall có tác dụng trong việc lọc các gói tin được gửi đến hay gửi từ một địa chỉ IP và cho phép truy cập đến một port cụ thể.

###b. Filter gói tin (quá trình bắt gói tin).

- Filter là quá trình bắt gói tin theo một số yêu cầu.
- Quá trình bắt gói tin được diễn ra như sau : Giả sử một gói tin được đi đến, và nó có các bộ tham số như : địa chỉ nguồn , địa chỉ đích, port nguồn, port đích, TTL, TOS giao thức . Lúc này bộ lọc sẽ dựa vào các tham số trên của gói tin để áp dụng các phương pháp xử lý, ngoài ra còn có thể kết hợp các điều kiện lại với nhau như gói tin TCP có địa chỉ port đich nguồn,v,v...
- Ví dụ chúng ta thiết lập chỉ nhận gói tin tcp và địa chỉ port đích là 80 như sau"

```sh
iptables -A INPUT -p tcp -dport 80 -j ACCEPT
```

###c. Gói tin.

- Phải hiểu rõ được định dạng gói tin. Ví dụ như gói tin TCP thì phần header có các trường nào và ý nghĩa về các trường đó, hiểu biết về port.
##2. Các khái niệm về bảng, chain, rule.

- Trong iptables được chia thành 3 bảng (table):
 <ul>
 <li>Bảng mangle : bảng này để thay đổi QoS của gói tin như thay đổi các tham số TOS, TTL,...</li>
 <li>Bảng NAT: Dùng để thay đổi địa chỉ đích, nguồn, port đích, nguồn của gói tin.</li>
 <li>Bảng filter: áp dụng các chính sách lọc gói tin qua đó cho phép gói tin được qua hay không qua,</li>
 </ul>

- Bình thường bảng NAT và Filter hay được sử dụng còn bảng mangle trong mạng soho thường ít được sử dụng đến nó.

###a. Bảng NAT.

- Trong bảng NAT có các `chain` được xây dựng sẵn trong table NAT.

**chain PREROUTING** 

- Đây là chain dùng để thay đổi địa chỉ đích của gói tin và trong chain PREROUTING targe (tác vụ) được sử dụng là DNAT (Destination NAT)
- Ví dụ:

```sh
iptables -t NAT -A PREROUTING -p tcp --dport 80 -j DNAT --to-destination 10.10.10.10:80
```

- Câu lệnh này có ý nghĩa : ĐỐi với gói tin có port đích là 80 sẽ được đổi địa chỉ thành 10.10.10.10 ví dụ trên đã định nghĩa rõ cho chúng ta nói ra chọn bảng NAT áp dụng rule và trong chain PREROUTING sử dụng target DNAT.

**chain POSTROUTING**

- Đây là chain dùng để thay đổi địa chỉ nguồn của gói tin và target được sử dụng là SNAT (Sources NAT).
- Ví dụ:

```sh
iptables -t NAT -A POSTROUTING -p tcp -j SNAT --to-source 10.10.10.10
```

- Câu lệnh trên có ý nghĩa thay đổi địa chỉ nguồn đối với gói tin tcp thành 10.10.10.10.

**chain OUTPUT**

- Bộ lọc gói tin khi đi ra khỏi tường lửa (gói dữ liệu có nguồn gốc từ tường lửa.)
- NAT sử dụng cho các gói dữ liệu xuất phát từ tường lửa. Rất hiếm khi được sử dụng trong môi trường soho.

**So sánh**

 <table>
  <tr>
   <td></td>
   <td>OUTPUT</td>
   <td>Bộ lọc gói đi ra khỏi tường lửa (gói dữ liệu có nguồn gốc từ các bức tường lửa).</td>
  </tr>
  <tr>
   <td>NAT</td>
   <td>PREROUTING</td>
   <td>Thay đổi địa chỉ đích xảy ra trước khi định tuyến . Tạo điều kiện cho việc chuyển đổi địa chỉ IP đích tương thích với bảng định tuyến của tường lửa. Được sử dụng với NAT của địa chỉ IP đích , còn được gọi là Destination NAt hay DNAT.</td>
  </tr>
  <tr>
   <td>NAT</td>
   <td>POSTROUTING</td>
   <td>Thay đổi địa chỉ đích xảy ra sau khi định tuyến. Điều này có nghĩa rằng không cần phải thay đổi địa chỉ IP đích của gói tin như trong định tuyến trước. Được sử dụng với NAT của địa chỉ IP nguồn bằng cách sử dụng một-một hoặc NAT-một-nhiều. Điều này được gọi là source NAt hay SNAT.</td>
  </tr>
  <tr>
   <td>NAT</td>
   <td>OUTPUT</td>
   <td>NAT sử dụng cho các gói dữ liệu xuất phát từ tường lửa . Rất hiếm khi được sử dụng trong môi trường SOHO.</td>
  </tr>
 </table>

###b. Bảng Filter.

- Trong bảng `Filter` có các chain được built sẵn:
 <ul>
 <li>chian INPUT: đây là chian dùng để lọc các gói tin đầu vào. Chain này là chain các gói tin bắt buộc phải đi qua để có thể được xử lý.</li>
 <li>chain UOTPUT: Đây là chain dùng để lọc các gói tin đầu ra. Chain này là chain sau khi gói tin được xử lý phải đi qua chian này để được ra bên ngoài.</li>
 <li>chain FORWARD: Đây là chain dùng để chuyển gói tin qua lại giữa các card mạng với nhau.</li>
 </ul>

- Các target được sử dụng trong các chain nàu có thể là ACCEPY (đồng ý), DROP (xóa bỏ).

###c. Bảng mangle.

- Trong bảng mangle bao gồm tất cả các chain được xây dựng sẵn là : PREROUTING, POSTROUTING, INPUT, OUTPUT, FORWARD. Bảng mangle rất ít được sử dụng trong mạng SOHO nên sẽ không đề cập đến. 

##3. Quá trình xử lý gói tin trong iptables.

![iptables]()

- Trên là quá trình xử lý gói tin trong iptables. Các gói tin mặc định sẽ phải đi qua bảng này để hoàn thành chu trình xử lý.

- Đầu tiên gói tin từ mạng A đi vào hệ thống firewall sẽ phải đi qua bảng mangle với chain là PREROUTING (với mục đích để thay đổi một số thông tin của gói tin trước khi đưa ra quyết định chỉ đường) sau đó gói tin đến bảng NAT với chain PREROUTING , tại đây địa chỉ đích của gói tin có thể bị thay đổi hoặc không, qua bộ routing và sẽ quyết định xem gói tin đó có thuộc firewall hay không.
 <ul>
 <li></li>
 <li></li>
 </ul>