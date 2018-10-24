# [Customer](#customer)
* [List](#danh-sách)
* [Create new](#tạo-mới)
* [Update information](#cập-nhật-thông-tin)
* [Forgot password](#quên-mật-khẩu)
* [Update password](#cập-nhật-mật-khẩu)
* [Detail](#cập-nhật-mật-khẩu)
* [Hold](#tạm-ngưng)
* [Active](#kích-hoạt)
## [List](#search)
Find Reseller's customers
> **API:** /api/rms/v1/customer/search  
> **MethodMe:** POST  
> **Body should be a JSON object(JSON):**   
```
{
   "email": "querystring",
   "fullname": "querystring",
   "phone": "querystring",
   "page": 0,
   "pageSize": 30,
   "fromCreatedDate": "01/01/2017 00:00",
   "toCreatedDate": "01/01/2017 00:00"
}
```
**email**: customer email  
**fullname**: full name   
**phone**:phone  
**page**: page, default 0  
**pageSize**: number of clients return, default 30   
**fromCreatedDate**: create date from (MM/DD/YYYY HH:MI)  
**toCreatedDate**: create date to (MM/DD/YYYY HH:MI)  

## [Create new](#create)
Create a new customer
> **API:** /api/rms/v1/customer/create  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "email": "customer1@examples.vn",
   "password": "password",
   "fullname": "Nguyễn Văn A",
   "organizationName": "Company A",
   "gender": "male", 
   "birthday": "01/01/2017 00:00", 
   "country": "VN", 
   "province": "HNI", 
   "address": "Address 1",
   "phone": "phone 1",
}
```
**email (required)**: customer email  
**password (required)**: password
**fullname (required)**: Last name [middle name] first name(example: Nguyễn Văn A)  
**organizationName**: Name of organization 
**gender**: gender ['male', 'female']  
**birthday**: birthday  
**country**: [country code](https://github.com/donvinet/iNET.vn-En/blob/master/reseller_category.md#country)  
**province**: [province code](https://github.com/donvinet/iNET.vn-En/blob/master/reseller_category.md#province)  
**address (required)**: address  
**phone (required)**: phone number(+CC-YYYYYYYYY)  

## [Update information](#update)
Update customer's information
> **API:** /api/rms/v1/customer/update  
> **Method:** POST  
> **Body should be a JSON object(JSON):**   
```
{
   "id": 0,
   "fullname": "Nguyễn Văn A",
   "organizationName": "Company A",
   "gender": "male", 
   "birthday": "01/01/2017 00:00", 
   "country": "VN", //List country at here
   "province": "HNI", //List privince at here
   "address": "Sddress 1",
   "phone": "Phone 1",
}
```
**id (required)**: customer ID
**fullname (required)**: last name [middle name] first name(example: Nguyễn Văn A)  
**organizationName**: Name of organization  
**gender**: gender ['male', 'female']  
**birthday**: birthday  
**country**: [Country code](https://github.com/donvinet/iNET.vn-En/blob/master/reseller_category.md#country)  
**province**: [Province code](https://github.com/donvinet/iNET.vn-En/blob/master/reseller_category.md#province)  
**address (required)**: address
**phone (required)**: phone (+CC-YYYYYYYYY)  


## [Forgot password](#forgotpassword)
Get tokens forgotten login password of the customer, entered information is email
> **API:** /api/rms/v1/customer/forgotpassword  
> **Method:** POST  
> **Body should be a JSON object(JSON):**   
```
{
   "email": "customer@example.vn"
}
```
**email (required)**: customer email   

## [change password](#changepassword)
Update customer's login password
> **API:** /api/rms/v1/customer/changepassword  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0,
   "password": "newpassword",
   "passwordForgotToken": "token"//
}
```
**id (required)**: customer's id    
**password (required)**: customer's id   
**passwordForgotToken (required)**: [password Forgot Token](https://github.com/donvinet/iNET.vn-En/blob/master/reseller_customer.md#forgot-pasword)   

## [Detail](#get)
Get customer information via id
> **API:** /api/rms/v1/customer/get
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (required)**: customer's id  

Get customer information via email
> **API:** /api/rms/v1/customer/getbyemail  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "email": "customer@example.vn"
}
```
**email (required)**: customer's email   

## [suspend](#suspend)
Suspend customer account
> **API:** /api/rms/v1/customer/suspend  
> **Method:** POST  
> **Body should be a JSON object (JSON):**  
```
{
   "id": 0
}
```
**id (required)**: customer's id

## [Active](#active)
Cctivate customer accounts
> **API:** /api/rms/v1/customer/active  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "id": 0
}
```
**id (required)**: customer's id
