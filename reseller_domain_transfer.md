# [Chuyển đổi nhà đăng ký](#domaintransfer)
* [Danh sách](#danh-sách)
* [Mở khóa](#mở-khóa)
* [Khóa](#khóa)
* [Chấp nhận](#chấp-nhận)
* [Từ chối](#từ-chối)
* [Gửi yêu cầu](#gửi-yêu-cầu)
* [Hủy bỏ yêu cầu](#hủy-bỏ-yêu-cầu)
## [Danh sách](#search)
Tìm kiếm danh sách tên miền chuyển đổi nhà đăng ký
> **API:** /api/rms/v1/domaintransfer/list  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "page": 0,
   "pageSize": 30,
   "name": "example.vn"
}
```
**page**: trang, mặc định 0  
**pageSize**: số lượng KH lấy về, mặc định 30  
**name**: tên miền  

## [Mở khóa](#unlock)
Mở khóa tên miền để chuyển đổi sang nhà đăng ký mới
> **API:** /api/rms/v1/domaintransfer/unlock  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Khóa](#lock)
Khóa tên miền lại
> **API:** /api/rms/v1/domaintransfer/lock  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Chấp nhận](#approve)
Chấp nhận chuyển đổi nhà đăng ký
> **API:** /api/rms/v1/domaintransfer/approve  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Từ chối](#reject)
Chấp nhận chuyển đổi nhà đăng ký
> **API:** /api/rms/v1/domaintransfer/reject  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Gửi yêu cầu](#request)
Gửi yêu cầu chuyển đổi tên miền
> **API:** /api/rms/v1/domaintransfer/request  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "name": "example.vn",
   "authCode": "xxxxxx",
   "registrar": "inet"
}
```
**name (bắt buộc)**: tên miền  
**authCode (bắt buộc)**: mã auth code của tên miền  
**registrar (bắt buộc)**: nhà đăng ký tên miền request

## [Hủy bỏ yêu cầu](#cancel)
Hủy bỏ yêu cầu chuyển đổi nhà đăng ký
> **API:** /api/rms/v1/domaintransfer/cancel  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  
