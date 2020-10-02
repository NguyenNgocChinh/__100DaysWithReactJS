# Ngày 1
## PHP
* Kết nối DataBase
	$connect = new mysqli('Máy Chủ', 'Tên Đăng Nhập mysql', 'Mật khẩu đăng nhập mysql', 'Tên ĐB');
* Kiểm tra tồn tại của 1 biến trong form
  - method = GET
	$variable = isset($_GET[" name of input "]);
  - method = POST
	$variable = isset($_POST[" name of input "]);
* Thực hiện câu lệnh MYSQL
	$kq = $connect->query($sql);
	-> $kq->num_rows : số dòng chịu tác động sau khi thực thi câu lệnh sql

## Bootstrap 4
* Định dạng màu cho text
	class = " text-danger" : trong đó danger là màu
* Định dạng in đậm cho text
	class = " font-weight-bold"
* Định dạng to nhỏ Element
	class = " Element-lg " : trong đó Element là các button,text... và lg là độ lớn như lg,sm,md...
* Định dạng màu nền ( Background )
	class = " bg-success" : trong đó success là các màu như danger,secondary,....


