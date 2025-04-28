<!--
Meta Description: # Lệnh END trong SAS: Cách sử dụng và Tác dụng ## Tóm tắt Lệnh END trong SAS được sử dụng để kết thúc một khối lệnh trong một cấu trúc điều kiện hoặc ...
Meta Keywords: lệnh, end, trong, sas, một
-->

# Lệnh END trong SAS: Cách sử dụng và Tác dụng

## Tóm tắt
Lệnh END trong SAS được sử dụng để kết thúc một khối lệnh trong một cấu trúc điều kiện hoặc vòng lặp, giúp kiểm soát luồng thực hiện của chương trình. 

## Tài liệu
### Mục đích
Lệnh END trong SAS thường được sử dụng trong các cấu trúc điều kiện như IF-THEN-ELSE, và trong các vòng lặp như DO. Nó đánh dấu điểm kết thúc cho một khối lệnh, giúp nhóm các lệnh liên quan lại với nhau.

### Cách sử dụng
Lệnh END thường xuất hiện trong các câu lệnh như sau:

- **Cấu trúc IF-THEN-ELSE**:
```sas
IF (điều kiện) THEN DO;
   /* Các lệnh thực hiện khi điều kiện đúng */
END;
```

- **Cấu trúc DO**:
```sas
DO i = 1 TO 10;
   /* Các lệnh thực hiện trong vòng lặp */
END;
```

### Chi tiết
Lệnh END không có tham số và chỉ đơn giản là một từ khóa để kết thúc khối lệnh. Việc sử dụng lệnh này là cần thiết để SAS có thể hiểu được khi nào một khối lệnh kết thúc, từ đó thực hiện các lệnh tiếp theo một cách chính xác.

## Ví dụ
### Ví dụ 1: Cấu trúc IF-THEN-ELSE
```sas
DATA example;
   SET mydata;
   IF age < 18 THEN DO;
      status = 'Trẻ em';
   END;
   ELSE DO;
      status = 'Người lớn';
   END;
RUN;
```

### Ví dụ 2: Vòng lặp DO
```sas
DATA sum_example;
   total = 0;
   DO i = 1 TO 5;
      total + i;
   END;
RUN;
```

## Giải thích
Một số vấn đề thường gặp liên quan đến lệnh END bao gồm:

- **Thiếu lệnh END**: Nếu không có lệnh END, SAS sẽ báo lỗi và không thể thực thi chương trình.
- **Sử dụng lệnh END không đúng vị trí**: Lệnh END phải được đặt ở đúng vị trí để xác định kết thúc khối lệnh, tránh tình trạng sai sót trong logic chương trình.

## Tóm tắt một câu
Lệnh END trong SAS là từ khóa thiết yếu dùng để đánh dấu kết thúc của các khối lệnh trong cấu trúc điều kiện và vòng lặp, đảm bảo chương trình chạy đúng logic.