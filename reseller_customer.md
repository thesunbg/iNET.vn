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
   "phone": "querystring",
   "page": 0,
   "pageSize": 30,
   "fromCreatedDate": "01/01/2017 00:00",
   "toCreatedDate": "01/01/2017 00:00"
}
```
**email**: email khách hàng  
**fullname**: tên đầy đủ   
**phone**: số điện thoại  
**page**: trang, mặc định 0  
**pageSize**: số lượng KH lấy về, mặc định 30  
**fromCreatedDate**: ngày tạo mới từ  
**toCreatedDate**: ngày tạo mới tới  

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
email*: email khách hàng  
password*: mật khẩu  
fullname*: tên đầy đủ, bao gồm cả họ  
organizationName: tên tổ chức  
gender: giới tính, ['male', 'female']  
country: [mã quốc gia](https://github.com/thesunbg/iNET.vn/blob/master/reseller_category.md#danh-sách-quốc-gia)  
province: [mã tỉnh thành](https://github.com/thesunbg/iNET.vn/blob/master/reseller_category.md#danh-sách-tỉnh-thành)  
address*: địa chỉ  
phone*: số điện thoại  

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
