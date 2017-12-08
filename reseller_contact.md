# [Contact](#contact)
* [Danh sách](#danh-sách)
* [Tạo mới](#tạo-mới)
* [Chi tiết](#chi-tiết)
## [Danh sách](#search)
Tìm kiếm danh sách contact của đại lý
> **API:** /api/rms/v1/contact/search  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
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
**page**: trang, mặc định 0  
**pageSize**: số lượng KH lấy về, mặc định 30  
**fullname**: tên contact  
**registrar**: nhà đăng ký  
**organizationName**: tên tổ chức  
**email**: email  
**phone**: số điện thoại  
**fax**: fax  
**address**: địa chỉ  
**country**: quốc gia  
**province**: tỉnh thành  

## [Tạo mới](#create)
Tạo mới contact
> **API:** /api/rms/v1/contact/create  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "fullname": "Nguyễn Văn A",
   "registrar": "inet",
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
**fullname (bắt buộc)**: tên contact  
**registrar (bắt buộc)**: nhà đăng ký  
**organizationName**: tên tổ chức(nếu contact là tổ chức)  
**email (bắt buộc)**: email  
**phone (bắt buộc)**: số điện thoại  
**fax**: fax  
**address (bắt buộc)**: địa chỉ  
**country (bắt buộc)**: [mã quốc gia](https://github.com/thesunbg/iNET.vn/blob/master/reseller_category.md#country)  
**province (bắt buộc)**: [mã tỉnh thành](https://github.com/thesunbg/iNET.vn/blob/master/reseller_category.md#province)  
**dataExtend (bắt buộc)**: thông tin thêm contact  
**gender (nếu contact là cá nhân)**: giới tính ['male', 'female']  
**idNumber (nếu contact là cá nhân)**: số chứng minh thư  
**birthday (nếu contact là cá nhân)**: ngày sinh, định dạng DD/MM/YYYY  
**taxCode (nếu contact là tổ chức)**: mã số thuế  

## [Chi tiết](#detail)
Chi tiết contact
> **API:** /api/rms/v1/contact/get  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id contact  
