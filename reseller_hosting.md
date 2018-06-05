# [Hosting](#hosting)
* [Danh sách](#danh-sách)
* [Chi tiết](#Chi-tiết)
* [Đăng ký mới](#Đăng-ký-mới)
* [Duy trì](#duy-trì)
* [Đăng ký dùng thử](#Đăng-ký-dùng-thử)
* [Đăng nhập](#Đăng-nhập)

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

## [Duy trì](#renew)
Duy trì tên miền
> **API:** /api/rms/v1/domain/renew  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "period": 1,
   "expireDate": "2018-01-01 00:00",
}
```
**id (bắt buộc)**: id tên miền  
**period (bắt buộc)**: số năm đăng ký, <= 10 năm  
**expireDate (bắt buộc)**: ngày hết hạn hiện tại của tên miền  (YYYY-MM-DD HH:MI)  

## [Ẩn thông tin tên miền](#privacyprotection)
Ẩn thông tin tên miền trên whois
> **API:** /api/rms/v1/domain/privacyprotection  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Ký DNSSEC](#enablednssec)
Chỉ áp dụng cho tên miền sử dụng DNS của iNET  
Sau khi ký xong chờ khoảng 30 giây rồi chạy tiếp hàm đồng bộ DNSSEC để đẩy lên EPP server(kiểm tra bản ghi DS của tên miền qua hàm getdnssecbydomainid)
> **API:** /api/rms/v1/domain/enablednssec  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Đồng bộ DNSSEC](#syncdnssec)
Chỉ áp dụng cho tên miền sử dụng DNS của iNET  
Đồng bộ bản ghi DNSSEC lên EPP server  
> **API:** /api/rms/v1/domain/syncdnssec  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Bỏ ký DNSSEC](#disablednssec) 
Chỉ áp dụng cho tên miền sử dụng DNS của iNET  
Bỏ ký DNSSEC cho tên miền
> **API:** /api/rms/v1/domain/disablednssec  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Ký DNSSEC thủ công](#creatednssecmanual)
Ap dụng cho tên miền không sử dụng DNS của iNET  
Sau khi ký xong chờ khoảng 30 giây rồi chạy tiếp hàm đồng bộ DNSSEC để đẩy lên EPP server(kiểm tra bản ghi DS của tên miền qua hàm getdnssecbydomainid)
> **API:** /api/rms/v1/domain/creatednssecmanual  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "keyTag": "keyTag",
   "alg": "alg",
   "digest": "digest",
   "digestType": "digestType",
   "domainId": "domainId",
}
```
**domainId (bắt buộc)**: id tên miền  
**keyTag (bắt buộc)**: keyTag  
**alg (bắt buộc)**: alg  
**digest (bắt buộc)**: digest  
**digestType (bắt buộc)**: digestType

## [Cập nhật khóa bản ghi DNSSEC trước khi đồng bộ](#updatednssecmanual)
Ap dụng cho tên miền không sử dụng DNS của iNET  
Cập nhật các thông tin khóa bản ghi của tên miền
> **API:** /api/rms/v1/domain/updatednssecmanual  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "keyTag": "keyTag",
   "alg": "alg",
   "digest": "digest",
   "digestType": "digestType",
   "domainId": "domainId",
}
```
**domainId (bắt buộc)**: id tên miền  
**keyTag (bắt buộc)**: keyTag  
**alg (bắt buộc)**: alg  
**digest (bắt buộc)**: digest  
**digestType (bắt buộc)**: digestType

## [Xóa ký DNSSEC thủ công](#deletednssecmanual)
Ap dụng cho tên miền không sử dụng DNS của iNET  
Xóa không ký DNSSEC cho tên miền
> **API:** /api/rms/v1/domain/deletednssecmanual  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Thông tin tên miền](#detail)
Lấy thông tin chi tiết của tên miền
> **API:** /api/rms/v1/domain/detail  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Cập nhật nameserver](#updatedns)
Cập nhật nameserver của tên miền
> **API:** /api/rms/v1/domain/updatedns
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "nsList": [
      {
         "hostname": "ns3.inet.vn"
      },
      {
         "hostname": "ns4.inet.vn"
      }
   ]
}
```
**id (bắt buộc)**: id tên miền  
**nsList (bắt buộc)**: nameserver mới  

## [Cập nhật nameserver theo tên miền](#updatechilddns)
Cập nhật nameserver theo tên miền(childdns) của tên miền
> **API:** /api/rms/v1/domain/updatechilddns
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "hostList": [
      {
         "hostname": "ns3.inet.vn",
         "ipv4": "192.168.1.1"
      },
      {
         "hostname": "ns4.inet.vn",
         "ipv4": "192.168.1.1"
      }
   ]
}
```
**id (bắt buộc)**: id tên miền  
**hostList (bắt buộc)**: nameserver mới  


## [Thông tin bản ghi tên miền](#getrecord)
Lấy thông tin bản ghi của tên miền
> **API:** /api/rms/v1/domain/getrecord  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Cập nhật bản ghi tên miền](#updaterecord)
Cập nhật thông tin bản ghi của tên miền
> **API:** /api/rms/v1/domain/getrecord  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "recordList": [
      {
         "type": "A",
         "name": "@",
         "data": "192.168.1.1",
         "action": "add"
      },
      {
         "type": "A",
         "name": "www",
         "data": "192.168.1.1",
         "action": "del"
      }
   ]
}
```
**id (bắt buộc)**: id tên miền  
**recordList (bắt buộc)**: bản ghi tên miền, action = "add": tạo bản ghi, action = "del": xóa bán ghi  

## [Gửi lại email để xác nhận](#resendemailverification)
Gửi lại email để xác nhận tên miền
> **API:** /api/rms/v1/domain/resendemailverification  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Đổi mã auth code](#changeauthcode)
Đổi lại mã auth code cho tên miền
> **API:** /api/rms/v1/domain/changeauthcode  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id tên miền  

## [Đổi mật khẩu đăng nhập](#changepassword)
Đổi lại mật khẩu đăng nhập cho tên miền
> **API:** /api/rms/v1/domain/changepassword  
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

## [Xem vết](#log)
Xem vết tác động của tên miền
> **API:** /api/rms/v1/logdomain/search  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "domainId": 0,
   "actionName": "change-dns",
   "fromCreatedDate": "2018-01-01 00:00",
   "toCreatedDate": "2018-01-01 00:00",
}
```
**domainId (bắt buộc)**: id tên miền  
**actionName**: hành động[{'update-record': 'cập nhật bản ghi'}, {'update-status': 'cập nhật trạng thái'}, {'update-ns': 'cập nhật nameserver'}, {'change-password': 'đổi mật khẩu'}]  
**fromCreatedDate**: ngày tác động từ  (YYYY-MM-DD HH:MI)  
**toCreatedDate**: ngày tác động tới  (YYYY-MM-DD HH:MI)  

## [Chuyển đại lý](#changeorganization)
Chuyển tên miền sang đại lý mới
> **API:** /api/rms/v1/roid/changeorganization  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "orgId": 1
}
```
**id (bắt buộc)**: id tên miền  
**orgId (bắt buộc)**: id của đại lý mới  

## [Chuyển tài khoản quản trị](#changecustomer)
Chuyển người quản trị tên miền
> **API:** /api/rms/v1/roid/changecustomer  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "customerId": 1
}
```
**id (bắt buộc)**: id tên miền  
**customerId (bắt buộc)**: id của khách hàng mới  
