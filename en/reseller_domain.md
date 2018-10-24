# [Domain](#domain)
* [List](#danh-sách)
* [Whois](#kiểm-tra-sự-tồn-tại)
* [Change punycode for Vietnamese domain name](#chuyển-mã-puny-code-tên-miền-tiếng-việt)
* [New Registration](#Đăng-ký-mới)
* [Renew](#duy-trì)
* [Hide information](#Ẩn-thông-tin-tên-miền)
* [Detail domain information](#thông-tin-tên-miền)
* [Update nameserver](#cập-nhật-nameserver)
* [Update nameserver by domain (childdns)](#cập-nhật-nameserver-theo-tên-miền)
* [Domain Records Information](#thông-tin-bản-ghi-tên-miền)
* [Update recards](#cập-nhật-bản-ghi-tên-miền)
* [Resend confirmation email](#gửi-lại-email-để-xác-nhận)
* [Change auth code](#Đổi-mã-auth-code)
* [Change login password](#Đổi-mật-khẩu-đăng-nhập)
* [Trace](#xem-vết)
* [Change Resellers](#chuyển-đại-lý)
* [Transfer admin account](#chuyển-tài-khoản-quản-trị)
## [List](#search)
Search Reseller's domain list
> **API:** /api/rms/v1/domain/search  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "page": 0,
   "pageSize": 10,
   "name": "querystring",
   "idnName": "querystring",
   "registrant": "querystring",
   "suffix": "querystring",
   "registrar": "hitek",
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
**name**: domain
**idnName**: Vietnamese domain name  
**registrant**: Entity name  
**suffix**: domain extension  
**registrar**: registrar [{'DOTVN': 'tên miền .vn'}]  
**status**: domain status[{'active': 'active', {'suspended': 'suspended'}, {'deleted': 'deleted'}]  
**contract**: have a declaration? true/false  
**verifyStatus**: domain confirm? true/false  
**privacyProtection**: domain using security services? true/false  
**fromIssueDate**: issue date from (MM/DD/YYYY HH:MI)  
**toIssueDate**: issue date to (MM/DD/YYYY HH:MI)  
**fromRenewDate**: renew  date from (MM/DD/YYYY HH:MI)  
**toRenewDate**: renew  date to (MM/DD/YYYY HH:MI)  
**fromExpireDate**: Expire date from (MM/DD/YYYY HH:MI)  
**toExpireDate**: Expire date to(MM/DD/YYYY HH:MI)  

## [Check available](#checkavailable)
Whois existence of the domain can be registered or not
> **API:** /api/rms/v1/domain/checkavailable  
> **Method:** POST  
> **Body should be a JSON object):**   
```
{
   "name": "xn--tnmin-hsa0954c.vn",
   "idnName": "tênmiền.vn",
   "registrar": "hitek"
}
```
**name (required)**: domain, If it is Vietnamese domain name is the punnymode of the idnName field 
**idnName**: Vietnamese domain name  
**registrar (required)**: registrar [{'hitek': 'tên miền .vn'}]

## [Transfer puny code for Vietnames domain name](#validateidnname)
Transfer puny code for Vietnames domain name
> **API:** /api/rms/v1/domain/validateidnname  
> **Method:** POST  
> **Body should be a JSON object(JSON):**   
```
{
   "idnName": "domain.vn",
}
```
**idnName**: Vietnames domain name  

## [Create new](#create)
Domain registration
> **API:** /api/rms/v1/domain/create  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "name": "xn--tnmin-hsa0954c.vn",
   "idnName": "domain.vn",
   "period": 1,
   "customerId": 0,
   "registrar": "hitek", 
   "nsList": [''], 
   "contacts": [
      {
         "fullname": "A Company",
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
**name (required)**: domain, if Vietnamese domain name is the punnymode of the idnName field
**idnName**: Vietnamese domain name 
**period (required)**: number of years registration, <= 10 years  
**customerId (required)**: ID Customer  
**registrar (required)**: registrar[{'hitek': 'domain .vn'}]  
**nsList **: nameserver list, Empty will take the default of Resellers's configuration 
**contacts (required)**: contact list of domain name, [detail](https://github.com/dotvnapi/dotvn-api/blob/master/reseller_contact.md)    

## [Renew](#renew)
Renew domain
> **API:** /api/rms/v1/domain/renew  
> **method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0,
   "period": 1,
   "expireDate": "01/01/2017 00:00"
}
```
**id (required)**: Domain ID  
**period (required)**: year of registration, <= 10 years  
**expireDate (required)**: expire date of domain (MM/DD/YYYY HH:MI)  

## [Privacy Protection](#privacyprotection)
Privacy Protection on whois
> **API:** /api/rms/v1/domain/privacyprotection  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (required)**: Domain ID

## [Domain Information](#detail)
Detail information of domain
> **API:** /api/rms/v1/domain/detail  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (required)**: Domain ID    

## [Update nameserver](#updatedns)
Update nameserver of domain
> **API:** /api/rms/v1/domain/updatedns
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0,
   "nsList": [
      {
         "hostname": "ns3.it.vn"
      },
      {
         "hostname": "ns4.it.vn"
      }
   ]
}
```
**id (required)**: Domain ID 
**nsList (required)**: New nameserver

## [Update nameserver by domain](#updatechilddns)
Update nameserver by domain (childdns)
> **API:** /api/rms/v1/domain/updatechilddns
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0,
   "hostList": [
      {
         "hostname": "ns3.it.vn",
         "ipv4": "192.168.1.1"
      },
      {
         "hostname": "ns4.it.vn",
         "ipv4": "192.168.1.1"
      }
   ]
}
```
**id (required)**: Domain ID 
**hostList (required)**: New nameserver 


## [Get record information's domain](#getrecord)
Get the record of domain
> **API:** /api/rms/v1/domain/getrecord  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (reqiured)**: Domain ID

## [Update record](#updaterecord)
Update record information of domain
> **API:** /api/rms/v1/domain/getrecord  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
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
**id (required)**: Domain ID
**recordList (required)**: record, action = "add": add record, action = "del": del record  

## [Send email to verification](#resendemailverification)
Resend email to verification domain
> **API:** /api/rms/v1/domain/resendemailverification  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (required)**: Domain ID

## [Change auth code](#changeauthcode)
Change auth code for domain
> **API:** /api/rms/v1/domain/changeauthcode  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (required)**: Domain ID

## [Change password](#changepassword)
Change login password for the domain
> **API:** /api/rms/v1/domain/changepassword  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0,
   "password": "newpassword"
}
```
**id (required)**: Domain ID
**password (required)**: new password  

## [Log](#log)
See log of the domain
> **API:** /api/rms/v1/logdomain/search  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "domainId": 0,
   "actionName": "change-dns",
   "fromCreatedDate": "01/01/2017 00:00",
   "toCreatedDate": "01/01/2017 00:00",
}
```
**domainId (required)**: Domain ID 
**actionName**: action[{'update-record': 'update record'}, {'update-status': 'update status'}, {'update-ns': 'update nameserver'}, {'change-password': 'change password'}]  
**fromCreatedDate**: Created date from  
**toCreatedDate**: Created date to

## [Change Resellers](#changeorganization)
Change domain to new Reseller
> **API:** /api/rms/v1/roid/changeorganization  
> **method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0,
   "orgId": 1
}
```
**id (required)**: Domain ID
**orgId (required)**: New Reseller's ID  

## [Change admin account](#changecustomer)
Change domain administrator
> **API:** /api/rms/v1/roid/changecustomer  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0,
   "customerId": 1
}
```
**id (required)**: Domain ID 
**customerId (required)**: new customer's id
