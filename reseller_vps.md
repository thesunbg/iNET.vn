# [Cloud VPS](#vps)
* [Danh sách](#danh-sách)
* [Chi tiết](#chi-tiết)
* [Đăng ký mới](#Đăng-ký-mới)
* [Duy trì](#duy-trì)
* [Nâng cấp gói](#nâng-cấp-gói)
* [Danh sách gói cước](#danh-sách-gói-cước)
* [Danh sách image](#danh-sách-image)

## [Danh sách](#search)
Tìm kiếm danh sách Cloud VPS của đại lý
> **API:** /api/rms/v1/vps/search  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "page": 0,
   "pageSize": 10,
   "name": "querystring",
   "customerId": 0,
   "status": "querystring",
   "planName": "Gói A",
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
**name**: tên gói Cloud VPS  
**customerId**: id của khách hàng  
**status**: trạng thái  
**planName**: gói cước  
**fromIssueDate**: ngày đăng ký từ  (YYYY-MM-DD HH:MI)  
**toIssueDate**: ngày đăng ký tới  (YYYY-MM-DD HH:MI)  
**fromRenewDate**: ngày duy trì từ  (YYYY-MM-DD HH:MI)  
**toRenewDate**: "ngày duy trì tới  (YYYY-MM-DD HH:MI)  
**fromExpireDate**: ngày hết hạn từ  (YYYY-MM-DD HH:MI)  
**toExpireDate**: ngày hết hạn tới  (YYYY-MM-DD HH:MI)  

## [Chi tiết](#detail)
Chi tiết gói Cloud VPS
> **API:** /api/rms/v1/vps/get  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   

## [Đăng ký mới](#create)
Tạo mới gói Cloud VPS
> **API:** /api/rms/v1/vps/create  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "planName": "Gói A",   
   "customerId": 0,
   "period": 12,
   "image": "tên image"
}
```
**planName (bắt buộc)**: gói cước['Gói A','Gói B','Gói C','Gói D','Gói E']  
**period (bắt buộc)**: số tháng đăng ký  
**customerId (bắt buộc)**: id của khách hàng  
**image (bắt buộc)**: tên image của gói VPS  

## [Duy trì](#renew)
Duy trì gói Cloud VPS
> **API:** /api/rms/v1/vps/renew  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "period": 12,
   "expireDate": "2018-01-01 00:00",
}
```
**id (bắt buộc)**: id gói Cloud VPS   
**period (bắt buộc)**: số tháng duy trì  
**expireDate (bắt buộc)**: ngày hết hạn hiện tại của gói hosting (YYYY-MM-DD HH:MI)  

## [Nâng cấp gói](#change-plan)
Nâng cấp gói Cloud VPS mới
> **API:** /api/rms/v1/vps/changeplan  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "planId": 12
}
```
**id (bắt buộc)**: id gói Cloud VPS   
**planId (bắt buộc)**: id của gói cước(chi tiết tại [Danh sách gói cước](#danh-sách-gói-cước))

## [Danh sách gói cước](#plan-list)
Danh sách gói cước trên hệ thống
> **API:** /api/rms/v1/plan/list  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "serviceType": "hosting",
   "name": "name",
   "type": "type"
}
```
**serviceType**: dịch vụ ['hosting', 'email', 'vps']  
**name**: tên gói cước  
**type**: l  

## [Danh sách image](#image-list)
Danh sách image trên hệ thống
> **API:** /api/rms/v1/vps/listimage  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   
}
```
