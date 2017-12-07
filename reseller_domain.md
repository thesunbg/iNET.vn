# [Tên miền](#domain)
## [Danh sách](#search)
Tìm kiếm danh sách tên miền của đại lý
> **API:** /api/rms/v1/domain/search  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "page": 0,
   "pageSize": 10,
   "name": "querystring",
   "idnName": "querystring",
   "registrant": "querystring",
   "suffix": "querystring",
   "status": "querystring",
   "contract": true,
   "verifyStatus": "querystring",
   "privacyProtection": "querystring",
   "fromIssueDate": "01/01/2017 00:00",
   "toIssueDate": "01/01/2017 00:00",
   "fromRenewDate": "01/01/2017 00:00",
   "toRenewDate": "01/01/2017 00:00",
   "fromExpireDate": "01/01/2017 00:00",
   "toExpireDate": "01/01/2017 00:00",
}
```
**page**: 0  
**pageSize**: 30  
**name**: tên miền  
**idnName**: tên miền tiếng việt  
**registrant**: tên chủ thể  
**suffix**: đuôi tên miền  
**status**: trạng thái tên miền['active', 'suspended', 'deleted']  
**contract**: đã có bản khai? true/false  
**verifyStatus**: tên miền đã được verify? true/false  
**privacyProtection**: tên miền có sử dụng dịch vụ bảo vệ? true/false  
**fromIssueDate**: ngày đăng ký từ  
**toIssueDate**: ngày đăng ký tới  
**fromRenewDate**: ngày duy trì từ  
**toRenewDate**: "ngày duy trì tới  
**fromExpireDate**: ngày hết hạn từ  
**toExpireDate**: ngày hết hạn tới  

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
   "gender": "male", 
   "country": "VN", 
   "province": "HNI",
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
