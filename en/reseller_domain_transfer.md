# [Change Registrar](#domaintransfer)
* [List](#danh-sách)
* [Unlock](#mở-khóa)
* [Lock](#khóa)
* [Accept](#chấp-nhận)
* [Reject](#từ-chối)
* [Send request](#gửi-yêu-cầu)
* [Cancel request](#hủy-bỏ-yêu-cầu)
## [List](#search)
Search list of domain change registrar 
> **API:** /api/rms/v1/domaintransfer/list  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "page": 0,
   "pageSize": 30,
   "name": "example.vn"
}
```
**page**: page, default 0  
**pageSize**: number of clients return, default 30  
**name**: Domain  

## [Unlock](#unlock)
Unlock domain name to switch to new registrar
> **API:** /api/rms/v1/domaintransfer/unlock  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (required)**: Domain's ID  

## [Lock](#lock)
Lock domain
> **API:** /api/rms/v1/domaintransfer/lock  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (required)**: Domain's ID  

## [Approve](#approve)
Accept to change registrar
> **API:** /api/rms/v1/domaintransfer/approve  
> **Method:** POST  
> **Body should be a JSON object(JSON):**   
```
{
   "id": 0
}
```
**id (required)**: Domain's id  

## [Reject](#reject)
Reject to change registrar
> **API:** /api/rms/v1/domaintransfer/reject  
> **Method:** POST  
> **Body should be a JSON object(JSON):**   
```
{
   "id": 0
}
```
**id (required)**: Domain's ID

## [Request](#request)
Submit request domain transfer
> **API:** /api/rms/v1/domaintransfer/request  
> **Method:** POST  
> **Body should be a JSON object(JSON):**   
```
{
   "name": "example.vn",
   "authCode": "xxxxxx",
   "registrar": "hitek"
}
```
**name (required)**: Domain
**authCode (required)**: Domain's auth code
**registrar (required)**: Registrar request

## [Cancel](#cancel)
Cacel request change registrar
> **API:** /api/rms/v1/domaintransfer/cancel  
> **Method:** POST  
> **Body should be a JSON object(JSON):**   
```
{
   "id": 0
}
```
**id (required)**: Domain's id
