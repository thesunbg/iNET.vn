# [Tên miền](#domain)
* [Danh sách](#danh-sách)
* [Kiểm tra sự tồn tại](#kiểm-tra-sự-tồn-tại)
* [Chuyển mã punycode cho tên miền tiếng việt](#chuyển-mã-puny-code-tên-miền-tiếng-việt)
* [Đăng ký mới](#Đăng-ký-mới)
* [Duy trì](#duy-trì)
* [Ẩn thông tin](#Ẩn-thông-tin-tên-miền)
* [Ký DNSSEC](#ký-dnssec)
* [Đồng bộ DNSSEC](#đồng-bộ-dnssec)
* [Bỏ ký DNSSEC](#bỏ-ký-dnssec)
* [Ký DNSSEC thủ công](#ký-dnssec-thủ-công)
* [Cập nhật khóa bản ghi DNSSEC trước khi đồng bộ](#ký-dnssec-thủ-công)
* [Xóa ký DNSSEC thủ công](#xóa-ký-dnssec-thủ-công)
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
* [Danh sách đuôi tên miền](#danh-sách-đuôi-tên-miền)
* [Upload bản khai tên miền](#upload-bản-khai-tên-miền)
* [Upload chứng minh thư khách hàng](#upload-chứng-minh-thư-khách-hàng)


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
   "customerId": '',
   "fromIssueDate": "2018-01-01 00:00",
   "toIssueDate": "2018-01-01 00:00",
   "fromRenewDate": "2018-01-01 00:00",
   "toRenewDate": "2018-01-01 00:00",
   "fromExpireDate": "2018-01-01 00:00",
   "toExpireDate": "2018-01-01 00:00",
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
**customerId**: id khách hàng  
**fromIssueDate**: ngày đăng ký từ  (YYYY-MM-DD HH:MI)  
**toIssueDate**: ngày đăng ký tới  (YYYY-MM-DD HH:MI)  
**fromRenewDate**: ngày duy trì từ  (YYYY-MM-DD HH:MI)  
**toRenewDate**: "ngày duy trì tới  (YYYY-MM-DD HH:MI)  
**fromExpireDate**: ngày hết hạn từ  (YYYY-MM-DD HH:MI)  
**toExpireDate**: ngày hết hạn tới  (YYYY-MM-DD HH:MI)  

## [Kiểm tra sự tồn tại](#checkavailable)
Kiểm tra sự tồn tại của tên miền có thể đăng ký được hay không
> **API:** /api/rms/v1/domain/checkavailable  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "name": "test.vn"
}
```
**name (bắt buộc)**: tên miền, nếu là tên miền tiếng việt thì là chuỗi punycode của trường idnName  

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
   "name": "test.vn",
   "period": 1,
   "customerId": 0,
   "nsList": [{"hostname": "ns1.inet.vn"},{"hostname": "ns2.inet.vn"}], 
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
         "taxCode": "0123456789"
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
         "gender": "male",
         "idNumber": "030810700",
         "birthday": "01/01/1971"
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
         "type": "technique",         
         "gender": "male",
         "idNumber": "030810700",
         "birthday": "01/01/1971"
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
         "type": "billing",         
         "gender": "male",
         "idNumber": "030810700",
         "birthday": "01/01/1971"
      }
   ]
}
```
**name (bắt buộc)**: tên miền, nếu là tên miền tiếng việt thì là chuỗi punycode của trường idnName  
**idnName**: tên miền tiếng việt  
**period (bắt buộc)**: số năm đăng ký, <= 10 năm  
**customerId (bắt buộc)**: id của khách hàng  
**nsList (bắt buộc)**: danh sách nameserver  
**contacts (bắt buộc)**: danh sách contact của tên miền    
**contacts.fullname**: tên đầy đủ của contact    
**contacts.organization**: contact thuộc tổ chức hay không(với tên miền .vn thì 3 contact admin, billing, technique bắt buộc phải là cá nhân)    
**contacts.email**: email của contact    
**contacts.country**: mã quốc gia của contact    
**contacts.province**: mã tỉnh thành của contact    
**contacts.address**: địa chỉ của contact    
**contacts.phone**: số điện thoại của contact(nhập +84-XXX hoặc 0XXX)    
**contacts.fax**: số fix của contact    
**contacts.gender**: giới tính của contact(nếu contact là cá nhân): n     
**contacts.idNumber**: số CMT của contact(nếu contact là cá nhân)    
**contacts.birthday**: ngày sinh của contact(nếu contact là cá nhân, định dạng DD/MM/YYYY)    
**contacts.taxCode**: mã số thuế của contact(nếu contact là tổ chức)    
**contacts.type**: loại contact: chủ thể(registrant), quản trị(admin), thanh toán(billing), technique(kỹ thuật)...

## [Duy trì](#renew)
Duy trì tên miền
> **API:** /api/rms/v1/domain/renew  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0,
   "period": 1
}
```
**id (bắt buộc)**: id tên miền  
**period (bắt buộc)**: số năm đăng ký, <= 10 năm  

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
   "recordType": "recordType",
   "data": "data",
}
```
**domainId (bắt buộc)**: id tên miền  
**keyTag (bắt buộc)**: keyTag  
**alg (bắt buộc)**: alg  
**digest (bắt buộc)**: digest  
**digestType (bắt buộc)**: digestType
**recordType (bắt buộc)**: recordType
**data (bắt buộc)**: data

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
   "recordType": "recordType",
   "data": "data",
}
```
**domainId (bắt buộc)**: id tên miền  
**keyTag (bắt buộc)**: keyTag  
**alg (bắt buộc)**: alg  
**digest (bắt buộc)**: digest  
**digestType (bắt buộc)**: digestType
**recordType (bắt buộc)**: recordType
**data (bắt buộc)**: data


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
> **API:** /api/rms/v1/domain/updaterecord  
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
         "id": "id record c",
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
   "id": 0,
   "name": "exampl"
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

## [Danh sách đuôi tên miền](#danh-sách-đuôi-tên-miền)
Danh sách đuôi tên miền
> **API:** /api/rms/v1/suffix/list  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "suffix": "vn"
}
```
> **Dữ liệu trả về mẫu(JSON):**   
```
[{
"suffix":"vn",
"type":"vn",
"priority":3,
"popular":1,
"regOrigin":295000,
"regPromotion":247500,
"renOrigin":455000,
"renPromotion":402500,
"transferOrigin":0,
"transferPromotion":0,
"promotionFrom":"02/25/2019 00:00",
"promotionTo":"02/26/2019 00:00"
}
```
**suffix**: đuôi tên miền  
**type**: loại tên miền: vn, gtld, new gtld  
Các trường còn lại không sử dụng cho đại lý.  


## [Upload bản khai tên miền](#upload-bản-khai-tên-miền)
Upload bản khai tên miền
> **API:** /api/rms/v1/domain/uploadcontract  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": id tên miền,
   "file": {
      "base64Content":xxx, //chuỗi base64 của file bản khai
      "name": "filename",
      "size": 123456
   }
}
```


## [Upload chứng minh thư khách hàng](#upload-chứng-minh-thư-khách-hàng)
Upload chứng minh thư của khách hàng
> **API:** /api/rms/v1/contact/uploadidnumber  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": id contact tên miền,
   "documentType": "frontEnd", (hoặc backEnd là mặt sau)
   "file": {
      "base64Content":xxx, //chuỗi base64 của file 
      "name": "filename",
      "size": 123456
   }
}

Nhiều contact có cùng email thì chỉ cần upload một file CMT duy nhất.
