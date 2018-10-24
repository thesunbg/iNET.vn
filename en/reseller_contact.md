# [Contact](#contact)
* [List](#danh-sách)
* [Create new](#tạo-mới)
* [Detail](#chi-tiết)
## [List](#search)
Search contact list of reseller
> **API:** /api/rms/v1/contact/search  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "page": 0,
   "pageSize": 30,
   "fullname": "querystring",
   "registrar": "querystring",
   "organizationName": "querystring",
   "email": "querystring",
   "phone": "querystring",
   "fax": "querystring",
   "address": "querystring",
   "country": "querystring",
   "province": "querystring"
}
```
**page**: page, default 0  
**pageSize**: number of clients return, default 30   
**fullname**: Contact name
**registrar**: registrar 
**organizationName**: Name of organization 
**email**: email  
**phone**: phone  
**fax**: fax  
**address**: address 
**country**: country 
**province**: province 

## [Create new](#create)
Create new contact
> **API:** /api/rms/v1/contact/create  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "fullname": "Nguyễn Văn A",
   "registrar": "hitek",
   "organizationName": "",
   "email": "a@example.vn",
   "phone": "+84-123456778",
   "fax": "+84-123456778",
   "address": "247 cau giay",
   "country": "VN",
   "province": "HNI",
   "dataExtend": "{\"gender\":\"male\",\"idNumber\":\"030810700\",\"birthday\":\"01/01/1971\"}",
}
```
**fullname (required)**: last name [middle name] first name (example: Nguyễn Văn A)  
**registrar (required)**: registrar  
**organizationName**: Name of organization (if contact is contact)  
**email (required)**: email  
**phone (required)**: phone  (+CC-YYYYYYYYY)
**fax**: fax  
**address (required)**: address  
**country (required)**: [country code](https://github.com/donvinet/iNET.vn-En/blob/master/reseller_category.md#country)  
**province (required)**: [province code](https://github.com/donvinet/iNET.vn-En/blob/master/reseller_category.md#province)  
**dataExtend (required)**: data extend  
**gender (if contact is personal)**: gender ['male', 'female']  
**idNumber (if contact is personal)**: Number ID  
**birthday (if contact is personal)**: birthday, format DD/MM/YYYY  
**taxCode (if contact is organization)**: tax code

## [Detail](#detail)
Contact details
> **API:** /api/rms/v1/contact/get  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (required)**: id contact  
