# [Sinh mã token](#Authentication)
Các API cho đại lý yêu cầu có mã token để xác thực quyền  
Cách 1: Sử dụng API token hệ thống cung cấp.  
Truy cập trang quản trị: https://dms.inet.vn/rms/account/organization/setting/api để lấy token của tài khoản 

> Sử dụng chuỗi token nhận được để set vào headers mỗi API gửi đi:  
```
{ headers: 
   {
       token: xxx
   }
}
```
Cách 2: sử dụng tài khoản và mật khẩu, địa chỉ IP đã đăng ký với iNET để tiến hành xác thực và lấy mã token.  

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
**email (bắt buộc)**: Email tài khoản được cung cấp cho đại lý  
**password (bắt buộc)**: Mật khẩu tài khoản được cung cấp cho đại lý

> **Dữ liệu trả về(JSON):**   
```
{
   "email": "youremail@example.vn",
   "token": "xxx"
}
```
> Sử dụng chuỗi token nhận được để set vào headers mỗi API gửi đi:  
```
{ headers: 
   {
       token: xxx
   }
}
```
