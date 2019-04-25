# [Cloud VPS](#vps)
* [Danh sách](#danh-sách)
* [Chi tiết](#chi-tiết)
* [Đăng ký mới](#Đăng-ký-mới)
* [Duy trì](#duy-trì)
* [Nâng cấp gói](#nâng-cấp-gói)
* [Danh sách gói cước](#danh-sách-gói-cước)
* [Danh sách image](#danh-sách-image)
* [Cập nhật ghi chú](#cập-nhật-ghi-chú)
* [Cài đặt image](#cài-đặt-image)
* [Tạo volume](#Tạo-volume)
* [Xóa volume](#Xóa-volume)
* [Tạo máy chủ](#Tạo-máy-chủ)
* [Lấy thông tin máy chủ](#Lấy-thông-tin-máy-chủ)
* [Đăng nhập console](#đăng-nhập-console)
* [Xem vết hệ thống](#xem-vết-hệ-thống)
* [Xem biểu đồ](#xem-biểu-đồ)
* [Khởi động máy chủ](#Khởi-động-máy-chủ)
* [Tắt máy chủ](#Tắt-máy-chủ)
* [Khởi động lại máy chủ(cứng)](#Khởi-động-lại-cứng-máy-chủ)
* [Khởi động lại máy chủ(mềm)](#Khởi-động-lại-mềm-máy-chủ)
* [Xóa máy chủ](#Xóa-máy-chủ)
* [Biểu phí tùy chỉnh](#Biểu-phí-tùy-chỉnh)

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
   "planId": 0,   
   "customerId": 0,
   "period": 12
}
```
**planId (bắt buộc)**: planId của gói Cloud VPS(Xem trong danh sách plan)  
**period (bắt buộc)**: số tháng đăng ký  
**customerId (bắt buộc)**: id của khách hàng  

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

## [Cập nhật ghi chú](#update-note)
Cập nhật trường ghi chú cho gói Cloud VPS. Mục đích ghi chú riêng dễ nhận biết gói Cloud VPS
> **API:** /api/rms/v1/vps/updatenote  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "note": "note"
}
```
**id (bắt buộc)**: id gói Cloud VPS   
**note (bắt buộc)**: ghi chú  

## [Cài đặt image](#choose-image)
Cài image cho Cloud VPS
> **API:** /api/rms/v1/vps/chooseimage  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "image": "image"
}
```
**id (bắt buộc)**: id gói Cloud VPS   
**image (bắt buộc)**: Tên của image  

## [Tạo volume](#create-volume)
Tạo volume cho Cloud VPS
> **API:** /api/rms/v1/vps/createvolume  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "image": "image"
}
```
**id (bắt buộc)**: id gói Cloud VPS   
**image**: Tên của image, không bắt buộc  

## [Xóa volume](#delete-volume)
Cài image cho Cloud VPS
> **API:** /api/rms/v1/vps/deletevolume  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   

## [Tạo máy chủ](#create-server)
Tạo máy chủ cho Cloud VPS
> **API:** /api/rms/v1/vps/createserver  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   

## [Lấy thông tin máy chủ](#get-server)
Lấy thông tin máy chủ gói Cloud VPS
> **API:** /api/rms/v1/vps/getserver  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   

## [Đăng nhập console](#console)
Lấy đường dẫn console cho Cloud VPS
> **API:** /api/rms/v1/vps/console  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   

## [Xem vết hệ thống](#logaction)
Xem vết gói Cloud VPS
> **API:** /api/rms/v1/vps/getlogaction  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   


## [Xem biểu đồ](#geturlgrafana)
Xem biểu đồ truy cập CPU, RAM, Tràffic của Cloud VPS
> **API:** /api/rms/v1/vps/geturlgrafana  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   

## [Khởi động máy chủ](#start-instance)
Khởi động máy chủ Cloud VPS
> **API:** /api/rms/v1/vps/startinstance  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   

## [Tắt máy chủ](#stop-instance)
Tắt máy chủ Cloud VPS
> **API:** /api/rms/v1/vps/shutdownserver  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   


## [Khởi động lại máy chủ(cứng)](#reboot-hard)
Khởi động lại máy chủ (c) Cloud VPS
> **API:** /api/rms/v1/vps/reboothard  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   

## [Khởi động lại máy chủ(mềm)](#reboot-soft)
Khởi động lại máy chủ (mềm) Cloud VPS
> **API:** /api/rms/v1/vps/rebootsoft  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   

## [Xóa máy chủ](#delete-server)
Tắt máy chủ Cloud VPS
> **API:** /api/rms/v1/vps/deleteserver  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id gói Cloud VPS   


## [Biểu phí tùy chỉnh](#plandetail)
Biểu phí tùy chỉnh 
> **API:** /api/rms/v1/plandetail/getbyplanid  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": planid
}
```
**id (bắt buộc)**: id plan gói Cloud VPS   
