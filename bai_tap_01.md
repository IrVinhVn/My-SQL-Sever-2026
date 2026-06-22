📊 Báo Cáo Thực Hành: Quản Lý Sinh Viên
Thông Tin Sinh Viên:

🧑‍🎓 Sinh viên thực hiện: Hoàng Công Vinh

🆔 Mã Sinh Viên: K235480106100

🏫 Lớp: K59KMT.K01

🗄️ Môn học: Hệ Quản Trị Cơ Sở Dữ Liệu

⚙️ Phần 1: Cấu hình và Cài đặt Hệ thống  
1: Cấu hình chế độ xác thực (Mixed Mode)
Thiết lập SQL Server cho phép đăng nhập bằng cả 2 phương thức: Windows Authentication và SQL Server Authentication.
<img width="2560" height="1440" alt="Screenshot 2026-04-10 181451" src="https://github.com/user-attachments/assets/db63f7c6-99e3-4701-adfb-7aa6f7e1da8e" />

2: Cấu hình cổng động (Dynamic Port) TCP/IP
Kích hoạt TCP (Enable + Active: Yes) cho địa chỉ 127.0.0.1. Thiết lập cổng động (Dynamic Port) là 3xxxx (trong đó xxxx là 4 số cuối của mã số sinh viên).
<img width="2560" height="1440" alt="Screenshot 2026-04-10 184750" src="https://github.com/user-attachments/assets/973ee183-b58d-4411-8cc2-f6f009d6ca16" />

3: Kiểm tra trạng thái dịch vụ (Service)
Xác nhận service SQL Server đang ở trạng thái Running và đã mở đúng cổng vừa cấu hình.
<img width="338" height="17" alt="Screenshot 2026-06-22 115333" src="https://github.com/user-attachments/assets/4283ab4e-a93e-45b0-960c-25915017b0ef" />

4: Cài đặt công cụ quản trị
Hoàn tất cài đặt phần mềm SQL Server Management Studio (SSMS).
<img width="2560" height="1440" alt="Screenshot 2026-04-11 145003" src="https://github.com/user-attachments/assets/26663eaa-173e-4735-9846-ca7267421598" />

5: Kiểm tra đăng nhập trên SSMS
Thực hiện đăng nhập thành công vào SQL Server bằng 2 phương thức đã cấu hình:

>5.1. Bằng Windows Authentication:
<img width="2560" height="1440" alt="Screenshot 2026-04-10 221551" src="https://github.com/user-attachments/assets/37628c39-9bf9-46c9-8ef9-164dfdd86f18" />

>5.2. Bằng SQL Server Authentication:
<img width="2560" height="1440" alt="Screenshot 2026-04-10 221606" src="https://github.com/user-attachments/assets/c48c7ff7-fa17-47a9-9285-2242a34dd033" />

📂 Phần 2: Khởi tạo Cơ sở Dữ liệu và Thiết kế Bảng  
6: Khởi tạo Cơ sở dữ liệu (Database)
Sử dụng lệnh CREATE DATABASE để tạo cơ sở dữ liệu mới. Tùy chỉnh đường dẫn lưu file dữ liệu và file log sang ổ đĩa khác ổ C:.

>6.1. Thiết lập đường dẫn (Path):
<img width="2560" height="1440" alt="Screenshot 2026-04-10 222338" src="https://github.com/user-attachments/assets/0ca3867a-527c-4057-8524-3b5d16d0d972" />

>6.2. Kiểm tra file vật lý đã được tạo ra tại thư mục:
<img width="2560" height="1440" alt="Screenshot 2026-04-10 222515" src="https://github.com/user-attachments/assets/b732b8f8-9a0d-409c-8dcd-04d21578bf1c" />

7: Thiết kế Bảng dữ liệu (Table)
Tạo bảng dữ liệu tương thích với cấu trúc của file CSV mẫu, thiết lập Khóa chính (Primary Key) cho trường masv.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 103100" src="https://github.com/user-attachments/assets/9d77b8c7-df62-44ec-bb50-a1471994d8e6" />

📝 Phần 3: Thao tác Dữ liệu (DML) và Truy vấn  
8: Import dữ liệu
Nhập dữ liệu từ file [data mẫu (CSV)](https://raw.githubusercontent.com/duycop/hqtcsdl_baitap_01/refs/heads/main/svtnut.csv) vào bảng vừa khởi tạo.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 103100" src="https://github.com/user-attachments/assets/fd315c97-5f53-4095-aa5e-28fe0d0b732b" />

9: Kiểm tra dữ liệu Import
Sử dụng lệnh đếm số dòng (COUNT) để xác nhận dữ liệu đã được import đầy đủ (kết quả khoảng 12020 dòng).
<img width="2560" height="1440" alt="Screenshot 2026-04-11 124445" src="https://github.com/user-attachments/assets/79c1acfa-b57c-43d6-b629-465e65887a33" />

 10: Thêm dữ liệu cá nhân (INSERT)
Thực thi lệnh thêm (insert) 1 bản ghi chứa thông tin cá nhân của bản thân vào bảng sinh viên.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 125308" src="https://github.com/user-attachments/assets/1bdc9b6d-781f-419f-941a-9cc3b32e8da9" />

 11: Cập nhật dữ liệu (UPDATE)
Cập nhật trường noisinh thành giá trị 'Sao Hoả' đối với những bản ghi có cả noisinh và diachi đều mang giá trị NULL.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 130258" src="https://github.com/user-attachments/assets/f4f80db6-b876-49fd-9b59-b0112cd5b00b" />

 12: Trích xuất dữ liệu sang bảng mới (SELECT INTO)
Sử dụng câu lệnh SELECT ... INTO để tạo bảng mới mang tên SaoHoa, chứa thông tin các sinh viên có nơi sinh ở 'Sao Hoả'.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 130632" src="https://github.com/user-attachments/assets/9a42c559-f138-4c0d-b911-a7a1a2e2eac9" />

 13: Kiểm tra bảng sao lưu
Truy vấn dữ liệu để kiểm tra bảng SaoHoa vừa được tạo.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 130637" src="https://github.com/user-attachments/assets/5fdf3a18-b9b3-4028-a91e-fa66c1a3bd5d" />

 14: Xóa dữ liệu có điều kiện (DELETE)
Thực thi lệnh xóa những sinh viên trong bảng SaoHoa có cùng Họ với sinh viên đang làm bài. 
>(Ví dụ: Sinh viên làm bài họ Hoàng -> Xóa toàn bộ sinh viên họ Hoàng).
<img width="2560" height="1440" alt="Screenshot 2026-04-11 130845" src="https://github.com/user-attachments/assets/c11195f6-2b7c-41a6-b78f-58782977bfc1" />

 15: Kiểm tra kết quả sau khi xóa
Truy vấn lại bảng SaoHoa để xác nhận đã xóa những sinh viên cùng Họ với sinh viên đang làm bài trong các bản ghi đã được xóa thành công.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 131059" src="https://github.com/user-attachments/assets/be4c93b3-2565-4720-9c1f-7039b76527ce" />

💾 Phần 4: Sao lưu, Dọn dẹp và Phục hồi Hệ thống
 16: Xuất Script (Backup)
Sử dụng tính năng Generate Scripts (chọn xuất cả Struct và Data) để sao lưu toàn bộ kết quả ra file dulieu.sql.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 141341" src="https://github.com/user-attachments/assets/f344d366-2cb6-4749-9878-8ea33ab27723" />

 17: Xóa Database và kiểm tra tệp vật lý
Thực hiện xóa cơ sở dữ liệu. Sau khi xóa thành công, kiểm tra lại thư mục lưu trữ (tại  6) để xác nhận 2 file vật lý không còn tồn tại.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 141748" src="https://github.com/user-attachments/assets/e55aaec0-3113-4553-a0e1-a192e4c8771a" />

18: Tạo cửa sổ mới để gõ lệnh: mở file dulieu.sql của đã lưu chạy toàn bộ các lệnh này. REFRESH lại cây liệt kê các database => kiểm chứng kết quả
<img width="2560" height="1440" alt="Screenshot 2026-04-11 141936" src="https://github.com/user-attachments/assets/5fab1b6e-7150-43a7-bdaa-804519c84d16" />

