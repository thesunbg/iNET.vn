# <a href="#Khách hàng">Khách hàng</a>
## <a href="#Danh sách">Danh sách</a>
Tìm kiếm khách hàng của đại lý
> **API:** /rms/v1/customer/search  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "email": "querystring",
   "fullname": "querystring",
   "phone": "querystring"
}
```

## <a href="#Tạo mới">Tạo mới</a>
Tạo một khách hàng mới
> **API:** /rms/v1/customer/create
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "email": "customer1@examples.vn",
   "password": "password",
   "fullname": "Nguyễn Văn A",
   "organizationName": "Company A",
   "gender": "male", //hoặc female: nữ
   "country": "VN", //Danh sách quốc gia tại đây
   "province": "HNI", //Danh sách tỉnh thành tại đây
   "address": "Địa chỉ 1",
   "phone": "Điện thoại 1",
}
```

## <a href="#Cập nhật thông tin">Cập nhật thông tin</a>
Cập nhật thông tin khách hàng
> **API:** /rms/v1/customer/update
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "fullname": "Nguyễn Văn A",
   "organizationName": "Company A",
   "gender": "male", //hoặc female: nữ
   "country": "VN", //Danh sách quốc gia tại đây
   "province": "HNI", //Danh sách tỉnh thành tại đây
   "address": "Địa chỉ 1",
   "phone": "Điện thoại 1",
}
```

## ## <a href="#Lấy thông tin">Lấy thông tin</a>
Lấy thông tin khách hàng qua id
> **API:** /rms/v1/customer/detail
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```

Lấy thông tin khách hàng qua email
> **API:** /rms/v1/customer/detail
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "email": "customer@example.vn"
}
```
