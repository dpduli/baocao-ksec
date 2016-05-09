##Công việc tuần 4

**Tìm hiểu về cách cài đặt phần mềm trên các distro khác nhau.**

- Các distro khác nhau thường khác nhau trước hết là ở công cụ quản lí gói.
 * Với họ Debian: sử dụng gói *.deb thì công cụ cài phần mềm là dpkg, công cụ quả lí gói là apt/aptitude.
 * Với Ubuntu là Advanced Packkaging Tool
 *  Các HĐH dùng gói *rpm thì công cụ cài là rpm, công cụ quản lí gói là yum (vói dòng redhat) hoặc zypper/yast (với dòng SUSE). Ngoài ra các hệ điều hành như Slackware, Gentoo, Puppy đều có công cụ quản lí khác nhau. 

* Các phần mềm trong Linux không chỉ chạy trên Linux mà nó còn chạy trên nhiều hệ thống khác nhau trong họ Unix. Thậm chí nó còn có thể chạy trên nhiều vi xử lí khác nhau vì thế các phần mềm trên Linux không tự đóng gói sẵn cho chúng ta lên sẽ gây lên việc khó khăn hơn trong cài đặt.

*cách cài đặt phần mềm trên Linux*

**1. cài phần mềm từ source trên Linux**

- Điều đầu tiên trước khi tiến hành cài đặt là phải có mã nguồn của gói trước đó. Thông thường các gói được trả về là .gz và .bz2 đây đều là 2 chuẩn nén khác nhau sau khi giải nén thì các gói sẽ có dạng mới là tar. Thế nhưng để dễ dàng và tiết kiệm dung lượng ổ nhớ ta có thể gộp thành 1 câu lệnh như sau: 

> - Với gói .gz : #tar -zxvf tengoi.gz
> - Với gói .z2 : #tar -jxvf tengoi.bz2

- Sau khi giải nén xong tập tin thì tìm đến tập tin và tìm kiếm file cài đặt. Hầu hết thì các gói đều tuân theo tuần tự : 

> câu lệnh : #./configure<br/>
> câu lệnh :make<br/>
> câu lệnh : make install

- Loại bỏ một một gói đã cài đặt, thông thường chúng ta sẽ tìm đến thư mục mã nguồn và thực hiện 1 trong 3 câu lệnh sau :

> câu lệnh thứ nhất : make uninstall<br/>
> câu lệnh thứ hai : make clean<br/>
> câu lệnh thứ ba : make distclean

**2. cài đặt phần mềm trên Redhat-Centos**

- Bản thân RPM không chứa các file cài đặt, nó chỉ chứa các thông tin về file sẽ được cài đặt.

- Cách đơn giản nhất để cài đặt một gói RPM là dùng lệnh.

ví dụ cài gói foobar-1.0-1.i386.rpm ta sẽ thực hiện như sau :

> rpm -ivh  foobar-1.0-1.i386.rpm

- Để uninstall package đã được cài :

> rpm -e foobar

- Để tìm thông tin 1 file RPM ta dùng câu lệnh :

> rpm -qpi koules-1.4-1.i386.rpm

- cài đặt với các gói nén TAR.GZ trước tiên ta bung nén :

> câu lệnh bung nén : #tar xvzf file.tar.gz

- Sau khi bung nén một thư mục chứa các file trong file nén được tạo ra. Vào thư mục này và cài đặt, thông thường theo các bước 

> câu lệnh : #./configure<br/>
> câu lệnh :make<br/>
> câu lệnh : make install

**3. Cài đặt phần mềm trên Ubuntu-Debian**

- cài đặt các file .deb: file này chỉ cần kích đúp vào file vào trình cài đặt tự mở sau đó click vào install package và chờ quá trình cài đặt hoàn tất.

- cài đặt các file .rpm: sử dụng gói Alien để chuyển sang .deb cho dễ cài đặt.
 * dùng lệnh 

> sudo apt-get install alien

để cài đặt gói Alien.<br/>
sau đó gõ pass ứng với user đang logon, nhập Y đề đồng ý cài đặt. tiếp đến

> cd Desktop<br/>
> alien -k filename.rpm

để covert sang file file .deb

- cài đặt file.bin
 * vào terminal gõ lệnh
> cd Desktop<br/>
> sudo chmod +x filename.bin<br/>
> ./filename.bin
