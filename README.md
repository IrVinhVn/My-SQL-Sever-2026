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
<img width="2560" height="1440" alt="Screenshot 2026-04-10 184926" src="https://github.com/user-attachments/assets/458fc123-62f7-481f-89d4-a719c0dd27d0" />

4: Cài đặt công cụ quản trị
Hoàn tất cài đặt phần mềm SQL Server Management Studio (SSMS).
<img width="2560" height="1440" alt="Screenshot 2026-04-10 221551" src="https://github.com/user-attachments/assets/fb830c74-967c-400b-b89f-33e4dafc3b82" />

5: Kiểm tra đăng nhập trên SSMS
Thực hiện đăng nhập thành công vào SQL Server bằng 2 phương thức đã cấu hình:

>5.1. Bằng Windows Authentication:
<img width="2560" height="1440" alt="Screenshot 2026-04-10 221606" src="https://github.com/user-attachments/assets/4ef49a7b-2989-4774-9ac3-22366c534ff0" />

>5.2. Bằng SQL Server Authentication:
<img width="2560" height="1440" alt="Screenshot 2026-04-10 222338" src="https://github.com/user-attachments/assets/3441f0ae-9bf5-44a9-92da-de7f130e1f9f" />

📂 Phần 2: Khởi tạo Cơ sở Dữ liệu và Thiết kế Bảng  
6: Khởi tạo Cơ sở dữ liệu (Database)
Sử dụng lệnh CREATE DATABASE để tạo cơ sở dữ liệu mới. Tùy chỉnh đường dẫn lưu file dữ liệu và file log sang ổ đĩa khác ổ C:.

6.1. Thiết lập đường dẫn (Path):
<img width="2560" height="1440" alt="Screenshot 2026-04-10 222515" src="https://github.com/user-attachments/assets/9cf0625b-5b30-4a7d-b48c-4da08350c597" />

6.2. Kiểm tra file vật lý đã được tạo ra tại thư mục:
<img width="2560" height="1440" alt="Screenshot 2026-04-11 103100" src="https://github.com/user-attachments/assets/16fc9bae-e72a-4ab9-9281-a00ed9a70ffc" />

7: Thiết kế Bảng dữ liệu (Table)
Tạo bảng dữ liệu tương thích với cấu trúc của file CSV mẫu, thiết lập Khóa chính (Primary Key) cho trường masv.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 124312" src="https://github.com/user-attachments/assets/e3d92a70-bb4d-424e-9460-47cefde72c95" />

📝 Phần 3: Thao tác Dữ liệu (DML) và Truy vấn
8: Import dữ liệu
Nhập dữ liệu từ file [data mẫu (CSV)](https://raw.githubusercontent.com/duycop/hqtcsdl_baitap_01/refs/heads/main/svtnut.csv) vào bảng vừa khởi tạo.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 124445" src="https://github.com/user-attachments/assets/6186c5f3-ff20-4f13-ad48-9f7a1197ffc8" />

9: Kiểm tra dữ liệu Import
Sử dụng lệnh đếm số dòng (COUNT) để xác nhận dữ liệu đã được import đầy đủ (kết quả khoảng 12020 dòng).
<img width="2560" height="1440" alt="Screenshot 2026-04-11 125308" src="https://github.com/user-attachments/assets/2c4c7c0a-484e-46a8-975a-e745183ff533" />

 10: Thêm dữ liệu cá nhân (INSERT)
Thực thi lệnh thêm (insert) 1 bản ghi chứa thông tin cá nhân của bản thân vào bảng sinh viên.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 130258" src="https://github.com/user-attachments/assets/30a7ba23-5e32-4365-84fd-0964fa60619f" />

 11: Cập nhật dữ liệu (UPDATE)
Cập nhật trường noisinh thành giá trị 'Sao Hoả' đối với những bản ghi có cả noisinh và diachi đều mang giá trị NULL.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 130632" src="https://github.com/user-attachments/assets/e1d471b1-55ab-45fd-b8f0-f9a36d6a3b31" />

 12: Trích xuất dữ liệu sang bảng mới (SELECT INTO)
Sử dụng câu lệnh SELECT ... INTO để tạo bảng mới mang tên SaoHoa, chứa thông tin các sinh viên có nơi sinh ở 'Sao Hoả'.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 130637" src="https://github.com/user-attachments/assets/dce9d0fd-fc14-41c1-8345-31f1ca91f139" />

 13: Kiểm tra bảng sao lưu
Truy vấn dữ liệu để kiểm tra bảng SaoHoa vừa được tạo.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 130845" src="https://github.com/user-attachments/assets/83cf7a4f-57f5-4f39-b578-2bca14a55cab" />

 14: Xóa dữ liệu có điều kiện (DELETE)
Thực thi lệnh xóa những sinh viên trong bảng SaoHoa có cùng Họ với sinh viên đang làm bài. 
>(Ví dụ: Sinh viên làm bài họ Hoàng -> Xóa toàn bộ sinh viên họ Hoàng).
<img width="2560" height="1440" alt="Screenshot 2026-04-11 131059" src="https://github.com/user-attachments/assets/e83ce8f8-c8c8-4a5f-9dbe-58b06d8ad3ee" />

 15: Kiểm tra kết quả sau khi xóa
Truy vấn lại bảng SaoHoa để xác nhận các bản ghi tương ứng đã được xóa thành công.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 141341" src="https://github.com/user-attachments/assets/ed874f81-5a80-4ea7-b083-897c974fbdcc" />

💾 Phần 4: Sao lưu, Dọn dẹp và Phục hồi Hệ thống
 16: Xuất Script (Backup)
Sử dụng tính năng Generate Scripts (chọn xuất cả Struct và Data) để sao lưu toàn bộ kết quả ra file dulieu.sql.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 141748" src="https://github.com/user-attachments/assets/608a9e44-41ca-4cc7-b44f-a7d61124f98f" />

 17: Xóa Database và kiểm tra tệp vật lý
Thực hiện xóa cơ sở dữ liệu. Sau khi xóa thành công, kiểm tra lại thư mục lưu trữ (tại  6) để xác nhận 2 file vật lý không còn tồn tại.
<img width="2560" height="1440" alt="Screenshot 2026-04-11 141936" src="https://github.com/user-attachments/assets/d50ed1fb-c1c6-421b-a6e5-d06e4fc96c9c" />


