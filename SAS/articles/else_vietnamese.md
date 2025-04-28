<!--
Meta Description: # Lệnh ELSE trong SAS: Cú Pháp và Cách Sử Dụng ## Tóm Tắt Lệnh ELSE trong SAS được sử dụng để xác định các điều kiện thay thế trong cấu trúc điều kiện...
Meta Keywords: điều, else, kiện, lệnh, các
-->

# Lệnh ELSE trong SAS: Cú Pháp và Cách Sử Dụng

## Tóm Tắt
Lệnh ELSE trong SAS được sử dụng để xác định các điều kiện thay thế trong cấu trúc điều kiện của ngôn ngữ lập trình. Nó cho phép người dùng thực hiện các hành động khác nhau dựa trên các điều kiện được kiểm tra.

## Tài Liệu
### Mục Đích
Lệnh ELSE được sử dụng trong các cấu trúc điều kiện như IF-THEN-ELSE để điều khiển luồng thực hiện trong các chương trình SAS. Khi điều kiện IF không được thỏa mãn, lệnh ELSE sẽ thực hiện một khối mã thay thế.

### Cú Pháp
Cú pháp cơ bản của lệnh ELSE trong SAS như sau:

```sas
IF điều_kiện THEN hành_động_1;
ELSE hành_động_2;
```

### Chi Tiết
- **Điều kiện:** Là một biểu thức logic mà nếu đúng, SAS sẽ thực hiện khối mã sau từ khóa THEN.
- **Hành động:** Là các câu lệnh mà bạn muốn thực hiện. Nếu điều kiện không thỏa mãn, SAS sẽ thực hiện các câu lệnh sau từ khóa ELSE.

Lệnh ELSE có thể kết hợp với nhiều điều kiện khác nhau và có thể sử dụng nhiều lần để tạo ra các cấu trúc điều kiện phức tạp hơn.

## Ví Dụ
### Ví Dụ 1: Sử Dụng Cơ Bản
```sas
data test;
    x = 5;
    if x > 10 then y = 'Lớn hơn 10';
    else y = 'Nhỏ hơn hoặc bằng 10';
run;
```
Trong ví dụ này, biến `y` sẽ nhận giá trị 'Nhỏ hơn hoặc bằng 10' vì điều kiện x > 10 không được thỏa mãn.

### Ví Dụ 2: Nhiều Điều Kiện
```sas
data test;
    x = 15;
    if x < 10 then y = 'Nhỏ hơn 10';
    else if x < 20 then y = 'Giữa 10 và 20';
    else y = 'Lớn hơn hoặc bằng 20';
run;
```
Kết quả sẽ là y = 'Giữa 10 và 20' vì điều kiện x < 20 được thỏa mãn.

## Giải Thích
### Những Điều Cần Lưu Ý
- **Trật Tự:** Lệnh ELSE phải đứng sau lệnh IF hoặc ELSE IF và không thể đứng một mình.
- **Lỗi Thường Gặp:** Một số lập trình viên mới bắt đầu có thể quên đặt ELSE hoặc không hiểu cách hoạt động của các cấu trúc điều kiện lồng nhau, dẫn đến lỗi logic.

### Ghi Chú Thêm
- Nên sử dụng chú thích trong mã để giải thích các điều kiện phức tạp, giúp người khác dễ dàng hiểu và bảo trì mã nguồn.

## Tóm Tắt Một Câu
Lệnh ELSE trong SAS cho phép bạn kiểm soát luồng thực hiện của chương trình bằng cách chỉ định các hành động thay thế khi điều kiện IF không được thỏa mãn.