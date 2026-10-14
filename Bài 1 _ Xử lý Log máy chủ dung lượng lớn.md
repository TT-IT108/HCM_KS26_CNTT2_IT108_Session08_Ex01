**Bài 1 : Xử lý Log máy chủ dung lượng lớn** 

### **Phần 1: Phân tích**

\+Tại sao Notepad bị treo? File log 800 MB chứa lượng dữ liệu lớn, việc nạp và hiển thị toàn bộ nội dung có thể tiêu tốn nhiều RAM, khiến máy chậm hoặc bị treo.

\+Tại sao cat lỗi trong CMD? cat không phải lệnh mặc định của CMD truyền thống nên hệ thống báo không nhận diện được lệnh.

\+Tại sao cat chạy trong PowerShell? Vì cat là alias của Get-Content, được PowerShell hỗ trợ sẵn.

### **Phần 2: Bộ lệnh PowerShell**

Câu 1\. Xem toàn bộ nội dung file:

Get-Content .\\server\_log\_800MB.log

Câu 2\. Xem 10 dòng cuối để kiểm tra lỗi mới nhất: 

Get-Content .\\server\_log\_800MB.log \-Tail 10

Với file 800 MB, nên dùng \-Tail 10 khi chỉ cần kiểm tra log mới nhất để tránh xử lý toàn bộ file không cần thiết. 

