# [Hosting](#hosting)
* [Danh sách](#danh-sách)
* [Chi tiết](#Chi-tiết)
* [Đăng ký mới](#Đăng-ký-mới)
* [Đăng ký dùng thử](#Đăng-ký-dùng-thử)
* [Duy trì](#duy-trì)
* [Đổi tên miền chính](#Đổi-tên-miền-chính)
* [Đăng nhập](#Đăng-nhập)
* [Đổi mật khẩu](#Đổi-mật-khẩu)

## [Danh sách](#search)
Tìm kiếm danh sách hosting của đại lý
> **API:** /api/rms/v1/hosting/search  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "page": 0,
   "pageSize": 10,
   "domainName": "querystring",
   "customerId": 0,
   "status": "querystring",
   "serverName": "querystring",
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
**domainName**: tên miền hosting  
**customerId**: id của khách hàng  
**status**: trạng thái  
**serverName**: url server của gói hosting  
**planName**: gói cước  
**type**: loại hosting
**fromIssueDate**: ngày đăng ký từ  (YYYY-MM-DD HH:MI)  
**toIssueDate**: ngày đăng ký tới  (YYYY-MM-DD HH:MI)  
**fromRenewDate**: ngày duy trì từ  (YYYY-MM-DD HH:MI)  
**toRenewDate**: "ngày duy trì tới  (YYYY-MM-DD HH:MI)  
**fromExpireDate**: ngày hết hạn từ  (YYYY-MM-DD HH:MI)  
**toExpireDate**: ngày hết hạn tới  (YYYY-MM-DD HH:MI)  

## [Đăng ký mới](#create)
Tạo mới gói hosting
> **API:** /api/rms/v1/hosting/create  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "domainName": "example.com",
   "type": "linux-new",
   "planName": "Gói A",   
   "customerId": 0,
   "period": 12,
}
```
**domainName (bắt buộc)**: tên miền hosting  
**type**: loại hosting ['linux-new','wordpress-new', 'seo-class-c', 'reseller']  
**customerId (bắt buộc)**: gói cước['Gói A','Gói B','Gói C','Gói D','Gói E']  
**period (bắt buộc)**: số tháng đăng ký  
**customerId (bắt buộc)**: id của khách hàng  

## [Đăng ký dùng thử](#create-trial)
Đăng ký dùng thử gói hosting
> **API:** /api/rms/v1/hosting/createtrial  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "domainName": "example.com",
   "type": "linux-new",
   "planName": "Gói A",   
   "customerId": 0,
   "period": 12,
}
```
**domainName (bắt buộc)**: tên miền hosting  
**type**: loại hosting ['linux-new','wordpress-new', 'seo-class-c', 'reseller']  
**customerId (bắt buộc)**: gói cước['Gói A','Gói B','Gói C','Gói D','Gói E']  
**period (bắt buộc)**: số tháng đăng ký  
**customerId (bắt buộc)**: id của khách hàng  

## [Duy trì](#renew)
Duy trì gói hosting
> **API:** /api/rms/v1/hosting/renew  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "period": 12,
   "expireDate": "2018-01-01 00:00",
}
```
**id (bắt buộc)**: id gói hosting   
**period (bắt buộc)**: số tháng duy trì  
**expireDate (bắt buộc)**: ngày hết hạn hiện tại của gói hosting (YYYY-MM-DD HH:MI)  

## [Đổi tên miền chính](#change-domain-name)
Đổi tên miền chính
> **API:** /api/rms/v1/hosting/changedomainname  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "domainName": "domain.com"
}
```
**id (bắt buộc)**: id hosting  
**domainName (bắt buộc)**: tên miền mới  

## [Đăng nhập](#signin)
Get link đăng nhập gói hosting
> **API:** /api/rms/v1/hosting/urlSignin  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói hosting  

## [Đổi mật khẩu](#change-password)
Đổimật khẩu đăng nhập gói hosting
> **API:** /api/rms/v1/hosting/changepassword  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "password": "newpassword"
}
```
**id (bắt buộc)**: id tên miền  
**password (bắt buộc)**: mật khẩu mới  
