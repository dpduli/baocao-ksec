##Câu hỏi tuần 4

- Khác với IIS trên Windows, Apache trên Unix có 3 chế độ hoạt động khác nhau winnt, prefork và worker. Đây là điểm mà IIS không bì đc với apache.

- Với Apache prefork và worker cho phép mở nhiều child process, với 1 thread/1 child process (prefork) hoặc many thread/1 child process (worker). Do đó apache chp phép xử lý mạnh hơn với prefork và càng mạnh hơn nữa với worker nhưng càng mạnh mẽ thì lại chiếm dụng càng nhiều tài nguyên. CÒn về ổn định nhất thì là prefork.

- Với frefork và một server Unix tầm trung có thể chia sẻ cho khoảng 500 người dùng nhiều dịch vụ khác cùng lúc, Apache có thể đạt tới mức xử lý 5000 request/1 second.
