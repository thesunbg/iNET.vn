# [Authentication](#Authentication)
Các API cho đại lý yêu cầu có mã token để xác thực quyền, sử dụng tài khoản và mật khẩu, địa chỉ IP đã đăng ký với iNET để tiến hành xác thực và lấy mã token.  
Hệ thống sử dụng chuẩn phương thức JSON Web Tokens(RFC 7519). 

> **Host:** dms.inet.vn  
> **Cổng:** 443  
> **API:** /api/sso/v1/user/signin  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "email": "youremail@example.vn",
   "password": "yourpassword"
}
```

> **Dữ liệu trả về(JSON):**   
```
{
   "email": "youremail@example.vn",
   "token": "xxx"
}
```
> Sử dụng chuỗi token nhận được để set vào headers mỗi API gửi đi:  
```
{
    token: xxx
}
```


# [Khách hàng](#Khách hàng)
## [Danh sách khách hàng](#Danh sách khách hàng)
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

## [Tạo mới khách hàng](#Tạo mới khách hàng)
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

## [Cập nhật thông tin khách hàng](#Cập nhật thông tin khách hàng)
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

## [Lấy thông tin khách hàng](#Lấy thông tin khách hàng)
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
