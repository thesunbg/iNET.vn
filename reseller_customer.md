# [Khách hàng](#customer)
## [Danh sách](#search)
Tìm kiếm khách hàng của đại lý
> **API:** /api/rms/v1/customer/search  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "email": "querystring",
   "fullname": "querystring",
   "phone": "querystring"
}
```

## [Tạo mới](#create)
Tạo một khách hàng mới
> **API:** /api/rms/v1/customer/create  
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

## [Cập nhật thông tin](#update)
Cập nhật thông tin khách hàng
> **API:** /api/rms/v1/customer/update  
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


## [Quên mật khẩu](#forgotpassword)
Lấy mã token quên mật khẩu đăng nhập của khách hàng, thông tin nhập vào là email
> **API:** /api/rms/v1/customer/forgotpassword  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "email": "customer@example.vn"
}
```

## [Cập nhật mật khẩu](#changepassword)
Cập nhật mật khẩu đăng nhập của khách hàng
> **API:** /api/rms/v1/customer/changepassword  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "password": "newpassword",
   "passwordForgotToken": "token"//
}
```
[passwordForgotToken](https://github.com/thesunbg/iNET.vn/blob/master/reseller_customer.md#quên-mật-khẩu)

## [Lấy thông tin](#get)
Lấy thông tin khách hàng qua id
> **API:** /api/rms/v1/customer/detail  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```

Lấy thông tin khách hàng qua email
> **API:** /api/rms/v1/customer/detail  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "email": "customer@example.vn"
}
```
