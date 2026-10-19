# Phần 1. Phân tích

- Lookup_value: Mã linh kiện cần tìm, ví dụ A2 trong sheet Don_Hang

- Table_array: Vùng tra cứu Danh_Muc!$A:$C. Dấu $ cố định vùng khi kéo công thức

- Col_index_num: 2 để lấy Tên linh kiện, 3 để lấy Đơn giá

- Range_lookup: FALSE để tìm chính xác mã linh kiện

# Phần 2. Hoàn Thành

Ô B2, điền Tên linh kiện:
```
=IFERROR(VLOOKUP(A2,Danh_Muc!$A:$C,2,FALSE),"#N/A")
```
Ô C2, điền Đơn giá:
```
=IFERROR(VLOOKUP(A2,Danh_Muc!$A:$C,3,FALSE),"#N/A")
```
Kéo công thức xuống các dòng còn lại
