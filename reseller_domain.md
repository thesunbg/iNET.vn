# [Tên miền](#domain)
* [Danh sách](#danh-sách)
* [Kiểm tra sự tồn tại](#kiểm-tra-sự-tồn-tại)
* [Chuyển mã punycode cho tên miền tiếng việt](#chuyển-mã-puny-code-tên-miền-tiếng-việt)
* [Đăng ký mới](#Đăng-ký-mới)
* [Duy trì](#duy-trì)
* [Ẩn thông tin](#Ẩn-thông-tin-tên-miền)
* [Chi tiết thông tin tên miền](#thông-tin-tên-miền)
* [Cập nhật nameserver](#cập-nhật-nameserver)
* [Cập nhật nameserver theo tên miền(childdns)](#cập-nhật-nameserver-theo-tên-miền)
* [Thông tin bản ghi](#thông-tin-bản-ghi-tên-miền)
* [Cập nhật bản ghi](#cập-nhật-bản-ghi-tên-miền)
* [Gửi lại email xác nhận](#gửi-lại-email-để-xác-nhận)
* [Đổi mã auth code](#Đổi-mã-auth-code)
* [Đổi mật khẩu đăng nhập](#Đổi-mật-khẩu-đăng-nhập)
* [Xem vết](#xem-vết)
* [Chuyển đại lý](#chuyển-đại-lý)
* [Chuyển tài khoản quản trị](#chuyển-tài-khoản-quản-trị)
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
   "registrar": "inet",
   "status": "active",
   "contract": true,
   "verifyStatus": true,
   "privacyProtection": true,
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
**registrar**: nhà đăng ký [{'inet': 'tên miền .vn'},{'inet-global': 'tên miền quốc tế'}]  
**status**: trạng thái tên miền[{'active': 'đang hoạt động', {'suspended': 'đang tạm ngưng'}, {'deleted': 'đã xóa'}]  
**contract**: đã có bản khai? true/false  
**verifyStatus**: tên miền đã được xác nhận? true/false  
**privacyProtection**: tên miền có sử dụng dịch vụ bảo vệ? true/false  
**fromIssueDate**: ngày đăng ký từ  
**toIssueDate**: ngày đăng ký tới  
**fromRenewDate**: ngày duy trì từ  
**toRenewDate**: "ngày duy trì tới  
**fromExpireDate**: ngày hết hạn từ  
**toExpireDate**: ngày hết hạn tới  

## [Kiểm tra sự tồn tại](#checkavailable)
Kiểm tra sự tồn tại của tên miền có thể đăng ký được hay không
> **API:** /api/rms/v1/domain/checkavailable  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "name": "xn--tnmin-hsa0954c.vn",
   "idnName": "tênmiền.vn",
   "registrar": "inet"
}
```
**name (bắt buộc)**: tên miền, nếu là tên miền tiếng việt thì là chuỗi punycode của trường idnName  
**idnName**: tên miền tiếng việt  
**registrar (bắt buộc)**: nhà đăng ký[{'inet': 'tên miền .vn'},{'inet-global': 'tên miền quốc tế'}]

## [Chuyển mã puny code tên miền tiếng việt](#validateidnname)
Chuyển mã puny code cho tên miền tiếng việt
> **API:** /api/rms/v1/domain/validateidnname  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "idnName": "tênmiền.vn",
}
```
**idnName**: tên miền tiếng việt  

## [Đăng ký mới](#create)
Đăng ký tên miền
> **API:** /api/rms/v1/domain/create  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "name": "xn--tnmin-hsa0954c.vn",
   "idnName": "tênmiền.vn",
   "period": 1,
   "customerId": 0,
   "registrar": "inet", 
   "nsList": [''], 
   "contacts": [
      {
         "fullname": "Công ty A",
         "organization": true,
         "email": "company@example.vn",
         "country": "VN",
         "province": "HNI",
         "address": "247 Cầu Giấy",
         "phone": "0438385588",
         "fax": "0438385588",
         "type": "registrant",
         "dataExtend": "{\"gender\":\"male\",\"idNumber\":\"030810700\",\"birthday\":\"01/01/1971\"}"
      },
      {
         "fullname": "Nguyễn Văn A",
         "organization": false,
         "email": "a@example.vn",
         "country": "VN",
         "province": "HNI",
         "address": "247 cau giay",
         "phone": "0974019049",
         "fax": "0974019049",
         "type": "admin",
         "dataExtend": "{\"gender\":\"male\",\"idNumber\":\"030810700\",\"birthday\":\"01/01/1971\"}"
      },
      {
         "fullname": "Nguyễn Văn A",
         "email": "a@example.vn",
         "country": "VN",
         "province": "HNI",
         "address": "247 cau giay",
         "phone": "0974019049",
         "fax": "0974019049",
         "type": "technique",
         "dataExtend": "{\"gender\":\"male\",\"idNumber\":\"030810700\",\"birthday\":\"01/01/1971\"}"
      },
      {
         "fullname": "Nguyễn Văn A",
         "email": "a@example.vn",
         "country": "VN",
         "province": "HNI",
         "address": "247 cau giay",
         "phone": "0974019049",
         "fax": "0974019049",
         "type": "billing",
         "dataExtend": "{\"gender\":\"male\",\"idNumber\":\"030810700\",\"birthday\":\"01/01/1971\"}"
      }
   ]
}
```
**name (bắt buộc)**: tên miền, nếu là tên miền tiếng việt thì là chuỗi punycode của trường idnName  
**idnName**: tên miền tiếng việt  
**period (bắt buộc)**: số năm đăng ký, <= 10 năm  
**customerId (bắt buộc)**: id của khách hàng  
**registrar (bắt buộc)**: nhà đăng ký[{'inet': 'tên miền .vn'},{'inet-global': 'tên miền quốc tế'}]  
**nsList (bắt buộc)**: danh sách nameserver  
**contacts (bắt buộc)**: danh sách contact của tên miền    

## [Duy trì](#renew)
Duy trì tên miền
> **API:** /api/rms/v1/domain/renew  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "period": 1,
   "expireDate": "01/01/2017 00:00"
}
```
**id (bắt buộc)**: id tên miền  
**period (bắt buộc)**: số năm đăng ký, <= 10 năm  
**expireDate (bắt buộc)**: ngày hết hạn hiện tại của tên miền  

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
   "fromCreatedDate": "01/01/2017 00:00",
   "toCreatedDate": "01/01/2017 00:00",
}
```
**domainId (bắt buộc)**: id tên miền  
**actionName**: hành động[{'update-record': 'cập nhật bản ghi'}, {'update-status': 'cập nhật trạng thái'}, {'update-ns': 'cập nhật nameserver'}, {'change-password': 'đổi mật khẩu'}]  
**fromCreatedDate**: ngày tác động từ  
**toCreatedDate**: ngày tác động tới  

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
