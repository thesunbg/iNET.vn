# [Email](#email)
* [Danh sách](#danh-sách)
* [Chi tiết](#chi-tiết)
* [Đăng ký mới](#Đăng-ký-mới)
* [Đăng ký dùng thử](#Đăng-ký-dùng-thử)
* [Duy trì](#duy-trì)
* [Nâng cấp gói](#nâng-cấp-gói)
* [Gen DKIM](#gen-dkim)
* [Lấy thông tin bản ghi](#lấy-thông-tin-bản-ghi)
* [Tạo mới tài khoản email](#tạo-mới-tài-khoản-email)
* [Cập nhật tài khoản email](#cập-nhật-tài-khoản-email)
* [Xóa tài khoản email](#xóa-tài-khoản-email)
* [Gen link đăng nhập tài khoản email](#gen-link-đăng-nhập-email)
* [Tạo mới nhóm email](#tạo-mới-nhóm-email)
* [Cập nhật nhóm email](#cập-nhật-nhóm-email)
* [Xóa nhóm email](#xóa-nhóm-email)
* [Đồng bộ tài khoản email](#Đồng-bộ-tài-khoản-email)
* [Danh sách gói cước](#danh-sách-gói-cước)

## [Danh sách](#search)
Tìm kiếm danh sách email của đại lý
> **API:** /api/rms/v1/email/search  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "page": 0,
   "pageSize": 10,
   "domainName": "querystring",
   "customerId": 0,
   "status": "querystring",
   "planName": "Gói A",
   "type": "type",
   "fromIssueDate": "2018-01-01 00:00",
   "toIssueDate": "2018-01-01 00:00",
   "fromRenewDate": "2018-01-01 00:00",
   "toRenewDate": "2018-01-01 00:00",
   "fromExpireDate": "2018-01-01 00:00",
   "toExpireDate": "2018-01-01 00:00",
}
```
**page**: trang  
**pageSize**: bản ghi trên một trang  
**domainName**: tên miền email  
**customerId**: id của khách hàng  
**status**: trạng thái    
**planName**: gói cước  
**type**: loại email  
**fromIssueDate**: ngày đăng ký từ  (YYYY-MM-DD HH:MI)  
**toIssueDate**: ngày đăng ký tới  (YYYY-MM-DD HH:MI)  
**fromRenewDate**: ngày duy trì từ  (YYYY-MM-DD HH:MI)  
**toRenewDate**: "ngày duy trì tới  (YYYY-MM-DD HH:MI)  
**fromExpireDate**: ngày hết hạn từ  (YYYY-MM-DD HH:MI)  
**toExpireDate**: ngày hết hạn tới  (YYYY-MM-DD HH:MI)  

## [Chi tiết](#detail)
Chi tiết gói email
> **API:** /api/rms/v1/email/gettotalquota  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói email   

## [Đăng ký mới](#create)
Tạo mới gói email
> **API:** /api/rms/v1/email/create  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "domainName": "example.com",
   "type": "email-new",
   "planName": "Gói A",   
   "customerId": 0,
   "period": 12,
}
```
**domainName (bắt buộc)**: tên miền email  
**type**: loại hosting ['email-new']  
**planName (bắt buộc)**: gói cước['Gói A','Gói B','Gói C','Gói D','Gói E']  
**period (bắt buộc)**: số tháng đăng ký  
**customerId (bắt buộc)**: id của khách hàng  

## [Đăng ký dùng thử](#create-trial)
Đăng ký dùng thử gói email
> **API:** /api/rms/v1/email/createtrial  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "domainName": "example.com",
   "type": "email-new",
   "planName": "Gói A",   
   "customerId": 0,
   "period": 12,
}
```
**domainName (bắt buộc)**: tên miền gói email  
**type**: loại hosting ['email-new']  
**planName (bắt buộc)**: gói cước['Gói A','Gói B','Gói C','Gói D','Gói E']  
**period (bắt buộc)**: số tháng đăng ký  
**customerId (bắt buộc)**: id của khách hàng  

## [Duy trì](#renew)
Duy trì gói email
> **API:** /api/rms/v1/email/renew  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "period": 12,
   "expireDate": "2018-01-01 00:00",
}
```
**id (bắt buộc)**: id gói email   
**period (bắt buộc)**: số tháng duy trì  
**expireDate (bắt buộc)**: ngày hết hạn hiện tại của gói email (YYYY-MM-DD HH:MI)  

## [Nâng cấp gói](#change-plan)
Nâng cấp gói email mới
> **API:** /api/rms/v1/email/changeplan  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "planId": 12
}
```
**id (bắt buộc)**: id gói email   
**planId (bắt buộc)**: id của gói cước(chi tiết tại [Danh sách gói cước](#danh-sách-gói-cước))

## [Gen DKIM](#gen-dkim)
Gen ra DKIM cho gói email
> **API:** /api/rms/v1/email/gendkim  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói email   

## [Lấy thông tin bản ghi](#getrecordverify)
Lấy ra danh sách thông tin bản ghi chính xác để  trỏ tên miền cho gói email có thể gửi email không bị đánh dấu SPAM  
> **API:** /api/rms/v1/email/getrecordverify  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói email   

## [Tạo mới tài khoản email](#create-email-account)
Tạo mới tài khoản email  
> **API:** /api/rms/v1/emailaccount/create  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "emailId": 0,
   "username": "",
   "displayName": "",
   "password": "",
   "quota": 0,
   "status": "",
   "emailForward": "",
   "description": "",
}
```
**emailId (bắt buộc)**: id gói email   
**username (bắt buộc)**: email của tài khoản   
**displayName (bắt buộc)**: tên hiển thị của tài khoản  
**password (bắt buộc)**: mật khẩu(bao gồm ký tự hoa, ký tự đặc biệt và ký tự số)   
**quota (bắt buộc)**: Cấp dung lượng cho tài khoản(tính theo MB)   
**status (bắt buộc)**: trạng thái ['active', 'suspended', 'locked']   
**emailForward**: chuyển tiếp email, mỗi email chuyển tiếp cách nhau một dấu phẩy  
**description**: mô tả thêm cho từng gói  

## [Cập nhật tài khoản email](#update-email-account)
Cập nhật tài khoản email  
> **API:** /api/rms/v1/emailaccount/update  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "emailId": 0,
   "username": "",
   "displayName": "",
   "password": "",
   "quota": 0,
   "status": "",
   "emailForward": "",
   "description": "",
}
```
**id (bắt buộc)**: id tài khoản email   
**emailId (bắt buộc)**: id gói email   
**username (bắt buộc)**: email của tài khoản   
**displayName (bắt buộc)**: tên hiển thị của tài khoản  
**password (bắt buộc)**: mật khẩu(bao gồm ký tự hoa, ký tự đặc biệt và ký tự số)   
**quota (bắt buộc)**: Cấp dung lượng cho tài khoản(tính theo MB)   
**status (bắt buộc)**: trạng thái ['active', 'suspended', 'locked']   
**emailForward**: chuyển tiếp email, mỗi email chuyển tiếp cách nhau một dấu phẩy  
**description**: mô tả thêm cho từng gói  

## [Xóa tài khoản email](#delete-email-account)
Xóa tài khoản email  
> **API:** /api/rms/v1/emailaccount/delete  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "emailId": 0
}
```
**id (bắt buộc)**: id tài khoản email   
**emailId (bắt buộc)**: id gói email   

## [Gen link dăng nhập tài khoản email](#gen-link-email-account)
Gen link đăng nhập cho tài khoản email   
> **API:** /api/rms/v1/emailaccount/createusersession  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "emailId": 0
}
```
**id (bắt buộc)**: id tài khoản email   
**emailId (bắt buộc)**: id gói email   

## [Tạo mới nhóm email](#create-group-email)
Tạo mới nhóm email   
> **API:** /api/rms/v1/email/createdistribution  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "emailId": 0,
   "name": "",
   "displayName": 0,
   "description": 0,
   "status": 0,
   "emailMemberList": [{username: 'test'}, {username: 'test2'}]
}
```
**emailId (bắt buộc)**: id gói email   
**name (bắt buộc)**: tên nhóm   
**displayName (bắt buộc)**: Tên hiển thị   
**description**: mô tả   
**status (bắt buộc)**: trạng thái   
**emailMemberList (bắt buộc)**: Danh sách tài khoản email  

## [Cập nhật nhóm email](#update-group-email)
Cập nhật nhóm email   
> **API:** /api/rms/v1/email/updatedistribution  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "emailId": 0,
   "name": "",
   "displayName": 0,
   "description": 0,
   "status": 0,
   "emailMemberList": [{username: 'test'}, {username: 'test2'}]
}
```
**id (bắt buộc)**: id nhóm email   
**emailId (bắt buộc)**: id gói email   
**name (bắt buộc)**: tên nhóm   
**displayName (bắt buộc)**: Tên hiển thị   
**description**: mô tả   
**status (bắt buộc)**: trạng thái   
**emailMemberList (bắt buộc)**: Danh sách tài khoản email  

## [Xóa nhóm email](#delete-group-email)
Xóa nhóm email   
> **API:** /api/rms/v1/email/deletedistribution  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "emailId": 0
}
```
**id (bắt buộc)**: id nhóm email   
**emailId (bắt buộc)**: id gói email   

## [Đồng bộ tài khoản email](#sync-email-account)
Đồngbộ tài khoản email trên server
> **API:** /api/rms/v1/email/syncemailaccount  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id nhóm email   


## [Danh sách gói cước](#plan-list)
Danh sách gói cước trên hệ thống
> **API:** /api/rms/v1/plan/list  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "serviceType": "email",
   "name": "name",
   "type": "type"
}
```
**serviceType**: dịch vụ ['hosting', 'email', 'vps']  
**name**: tên gói cước  
**type**: l  
