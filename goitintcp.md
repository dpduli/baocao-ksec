##Công việc tuần 3

**Phân tích gói tin TCP**

- Một gói tin TCP bao gồm 2 phần đó là : header và dữ liệu. Phần header có 11 trường trong đó có 10 trường bắt buộc:

![image](http://www.upsieutoc.com/images/2015/10/03/cv34.png)

- Trường thứ 11 là trường tùy chọn (không bắt buộc).

- Phần header:

 * Source port : số hiệu cổng tại máy tính gửi.
 * Destination port : Số hiệu cổng tại máy tính nhận.
 * Sequence number : Trường này có 2 nhiệm vụ. Nếu cờ SYN bật thì nó là số thứ tự gói ban đầu và byte đầu tiên được gửi có số thứ tự này cộng thêm 1. Nếu không có cờ SYN thì đây là số thứ tự của byte đầu tiên.
 * Acknowledgement number : Nếu cờ ACK bật thì giá trị của trường chính là số thứ tự gói tin tiếp theo mà bên nhận cần.
 * Data offset : Trường có độ dài 4 bít qui định độ dài của phần header (tính theo đơn vị từ 32 bít). Phần header có độ dài tối thiểu là 5 từ (160 bit) và tối đa là 15
từ (480 bít).
 * Reserved Dành cho tương lai và có giá trị là 0.
 * Flags (hay Control bits)

*Bao gồm 6 cờ*

* URG Cờ cho trường Urgent pointer
* ACK Cờ cho trường Acknowledgement
* PSH Hàm Push
* RST Thiết lập lại đường truyền
* SYN Đồng bộ lại số thứ tự
* FIN Không gửi thêm số liệu

**Checksum 16 bit** : kiểm tra cho cả phần header và dữ liệu.</br>
**16 bít của trường kiểm** tra là bổ sung của tổng tất cả các từ 16 bít trong gói tin. Trong
trường hợp số octet (khối 8 bít) của header và dữ liệu là lẻ thì octet cuối được bổ sung với các bít 0. Các bít này không được truyền. Khi tính tổng, giá trị của trường kiểm tra được thay thế bằng 0. Nói một cách khác, tất cả các từ 16 bít được cộng với nhau. Kết quả thu được sau khi đảo giá trị từng bít được điền vào trường kiểm tra. Về mặt thuật toán, quá trình này
giống với IPv4.</br>
**Điểm khác nhau** chỉ ở chỗ dữ liệu dùng để tính tổng kiểm tra.

- Phần dữ liệu: Trường cuối cùng không thuộc về Header . Giá trị của trường này là thông tin dành cho các tầng trên (trong mô hình 7 lớp OSI) . Thông tin về giao thức của tầng trên không được chỉ rõ trong phần header mà phụ thuộc vào cổng đc chọn.
