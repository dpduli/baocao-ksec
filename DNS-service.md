##Công việc tuần 6

**Nghiên cứu dịch vụ DNS**

- Dịch vụ tên miền (DNS-Domain Name Service) là một dịch vụ internet, có ánh xạ địa chỉ IP sang tên miền của các máy chủ có thực (FQD-Full Qalified Domain Names-Tên miền đầy đủ đã được chứng nhận) và ngược lại.

- Khi mở một trình duyệt web và nhập tên website, trình duyệt sẽ đến thẳng website mà không cần phải thông qua nhập địa chỉ IP của trang web. Quá trình dịch tên miền thành địa chỉ IP để cho trình duyệt hiểu và truy cập được vào website là công việc của một DNS server . Các DNS giúp nhau qua lại với nhau để dịch địa chỉ IP thành tên và ngược lại. Người sử dụng chỉ cần nhớ tên , không cần phải nhớ địa chỉ IP (Địa chỉ IP là con số rất khó nhớ).

*Phân loại các Domain Name Server.*

- Tên miền riêng (Primary Name Server) : Mỗi một máy chủ tên miền có mọt tên miền riêng. Tên miền riêng này được đăng ký trên internet.

- Tên miền dự phòng - tên miền thứ hai (Secondary Name Server) : Đây là một DNS server được sử dụng để thay thế cho Primary server DNS server bằng cách sao lưu lại tất cả bản ghi dữ liệu trên Primary Name server và nếu Primary Name server bị gián đoạn thì nó sẽ đảm nhận việc phần giải ánh xạ tên miền và địa chỉ IP.

- Caching Name Server : Đây là một server đảm nhiệm việc lưu tất cả những tên miền, địa chỉ IP, đã được phân giải và ánh xạ thành công. Nó được dùng trong các trường hợp sau :
 * Làm tăng tốc độ phân giải bằng cách sử dụng cache
 * Làm giảm bớt gánh nặng phân giải tên máy cho các DNS server
 * Giảm lưu lượng tham gia vào mạng và giảm độ trễ trên mạng (rất quang trọng).
