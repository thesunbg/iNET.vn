# [Giao dịch](#transaction)
* [Danh sách](#danh-sách)
* [Tạo mới](#tạo-mới)
* [Cập nhật thông tin](#cập-nhật-thông-tin)
* [Quên mật khẩu](#quên-mật-khẩu)
* [Cập nhật mật khẩu](#cập-nhật-mật-khẩu)
* [Chi tiết](#cập-nhật-mật-khẩu)
## [Danh sách](#search)
Tìm kiếm giao dịch của đại lý
> **API:** /api/rms/v1/transaction/list  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "page": 0,
   "pageSize": 30,
   "onlyOrganization": true,
   "type": "invoice",
   "description": "querystring",
   "transactionKey": "register",
   "serviceType": "domain",
   "customerEmail": "customer@example.vn",
   "resourceId": 0,
   "fromCreatedDate": "01/01/2017 00:00",
   "toCreatedDate": "01/01/2017 00:00"
}
```
**page**: trang, mặc định 0  
**pageSize**: số lượng KH lấy về, mặc định 30  
**onlyOrganization**: chỉ là giao dịch của riêng đại lý, không bao gồm đại lý con, mặc định false  
**type**: loại giao dịch[{'invoice': 'hóa đơn'}, {'refund': 'hoàn phí'}, {'receipt': 'nạp quỹ'}, {'arrear': 'truy thu'}]  
**description**: mô tả giao dịch  
**transactionKey**: mã giao dịch[{'register': 'đăng ký mới'},{'renew': 'duy trì'},{'change-registrant': 'đổi tên chủ thể'},
{'protect-privacy': 'ẩn thông tin'},{'transfer': 'chuyển nhà đăng ký'},{'registry-lock': 'registry lock'},{'registrar-lock': 'registrar lock'},
{'change-dns': 'đổi dns'},{'upgrade-plan': 'nâng cấp gói'},{'modify-plan': 'tùy chỉnh gói'},{'backorder': 'đặt chỗ'}]  
**serviceType**: dịch vụ[{'domain': 'tên miền'}, {'hosting': 'hosting'}, {'email': 'email'}, {'vps': 'Cloud VPS'}]  
**customerEmail**: email khách hàng  
**resourceId**: id của dịch vụ(id của tên miền, hosting...)  
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
   "gender": "male", 
   "birthday": "01/01/2017 00:00", 
   "country": "VN", 
   "province": "HNI", 
   "address": "Địa chỉ 1",
   "phone": "Điện thoại 1",
}
```
**email (bắt buộc)**: email khách hàng  
**password (bắt buộc)**: mật khẩu  
**fullname (bắt buộc)**: tên đầy đủ, bao gồm cả họ  
**organizationName**: tên tổ chức  
**gender**: giới tính ['male', 'female']  
**birthday**: ngày sinh  
**country**: [mã quốc gia](https://github.com/thesunbg/iNET.vn/blob/master/reseller_category.md#country)  
**province**: [mã tỉnh thành](https://github.com/thesunbg/iNET.vn/blob/master/reseller_category.md#province)  
**address (bắt buộc)**: địa chỉ  
**phone (bắt buộc)**: số điện thoại  

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
   "gender": "male", 
   "birthday": "01/01/2017 00:00", 
   "country": "VN", //Danh sách quốc gia tại đây
   "province": "HNI", //Danh sách tỉnh thành tại đây
   "address": "Địa chỉ 1",
   "phone": "Điện thoại 1",
}
```
**id (bắt buộc)**: id khách hàng   
**fullname (bắt buộc)**: tên đầy đủ, bao gồm cả họ  
**organizationName**: tên tổ chức  
**gender**: giới tính ['male', 'female']  
**birthday**: ngày sinh  
**country**: [mã quốc gia](https://github.com/thesunbg/iNET.vn/blob/master/reseller_category.md#country)  
**province**: [mã tỉnh thành](https://github.com/thesunbg/iNET.vn/blob/master/reseller_category.md#province)  
**address (bắt buộc)**: địa chỉ  
**phone (bắt buộc)**: số điện thoại  


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
**email (bắt buộc)**: email khách hàng   

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
**id (bắt buộc)**: id khách hàng   
**password (bắt buộc)**: id khách hàng   
**passwordForgotToken (bắt buộc)**: [token quên mật khẩu](https://github.com/thesunbg/iNET.vn/blob/master/reseller_customer.md#quên-mật-khẩu)   

## [Chi tiết](#get)
Lấy thông tin khách hàng qua id
> **API:** /api/rms/v1/customer/get
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id khách hàng   

Lấy thông tin khách hàng qua email
> **API:** /api/rms/v1/customer/getbyemail  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "email": "customer@example.vn"
}
```
**email (bắt buộc)**: email khách hàng   

## [Tạm ngưng](#forgotpassword)
Lấy mã token quên mật khẩu đăng nhập của khách hàng, thông tin nhập vào là email
> **API:** /api/rms/v1/customer/forgotpassword  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "email": "customer@example.vn"
}
```
**email (bắt buộc)**: email khách hàng   
