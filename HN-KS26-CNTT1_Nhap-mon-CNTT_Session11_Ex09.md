## Phần 1. Phân tích bài toán (I/O)

### 1. Các tham số VLOOKUP
Cột|Lookup_value|Table_array|Col_index_num
|-|-|-|-
|D - Tên tác giả|`TRIM(C2)`|`DanhMucTacGia!$A$2:$E$81`|2
E - Phòng|`TRIM(C2)`|`DanhMucTacGia!$A$2:$E$81`|4
F - Thù lao|`TRIM(C2)`|`DanhMucTacGia!$A$2:$E$81`|5

### 2. Xử lý 3 bẫy dữ liệu

-   `TRIM`: loại bỏ khoảng trắng thừa.
    
-   `IFERROR`: trả về `Chưa cập nhật` nếu không tìm thấy mã.
    
-   Dấu `$`: cố định vùng tra cứu khi kéo công thức.
    

### 3. Các bước thực hiện

-   Nhập công thức vào D2, E2, F2.
    
-   Kéo công thức xuống dòng 81.
    
-   Kiểm tra các mã tác giả chưa có trong danh mục.
    

## Phần 2. Triển khai và chống lỗi

### 4. Công thức ô D2

```
=IFERROR(VLOOKUP(TRIM(C2),DanhMucTacGia!$A$2:$E$81,2,FALSE),"Chưa cập nhật")
```

### 5. Công thức ô E2 và F2

Ô E2:

```
=IFERROR(VLOOKUP(TRIM(C2),DanhMucTacGia!$A$2:$E$81,4,FALSE),"Chưa cập nhật")
```

Ô F2:

```
=IFERROR(VLOOKUP(TRIM(C2),DanhMucTacGia!$A$2:$E$81,5,FALSE),"Chưa cập nhật")
```

Chỉ cần đổi `Col_index_num` thành 2, 4 hoặc 5 để lấy dữ liệu ở cột tương ứng.

### 6. Nếu bỏ dấu `$`

Kéo công thức từ D2 xuống D5, vùng tra cứu sẽ dịch từ `A2:E81` thành `A5:E84`, có thể gây sai kết quả. Dấu `$` giúp cố định vùng tra cứu.
