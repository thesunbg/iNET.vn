# [Biểu phí](#fee)
* [Tính toán giá dịch vụ](#tính-toán-giá-dịch-vụ)

## [Tính toán giá dịch vụ](#tính-toán-giá-dịch-vụ)
Tính toán giá của dịch vụ
> **API:** /api/rms/v1/fee/getprice  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
 "serviceType": "hosting",  
 "action": "register",  
 "planName": "Gói A",  
 "name": "example.vn",
 "type": "wordpress-new", 
 "period": 12 
}
```
**serviceType**: dịch vụ ['hosting', 'email', 'vps']  
**action**: hành động: register(đăng ký mới), renew(duy trì)  
**planName**: Gói A, Gói B, Gói C(áp dụng cho dịch vụ khác tên miền)  
**type**: Trường type trong danh sách gói cước(áp dụng cho dịch vụ khác tên miền)  
**name**: Tên miền muốn đăng ký(áp dụng cho dịch vụ tên miền)  
**period**: Thời gian đăng ký(năm cho dịch vụ tên miền, tháng cho các dịch vụ khác)  
> **Dữ liệu trả về mẫu(JSON):**   
```
{
    "value": 646800,  // Số tiền phải trả iNET(đã bao gồm số tiền VAT ở dưới)
    "valueOrigin": 646800,  //Tiền chưa chiết khấu  
    "vat": 10,  //Phần trăm VAT phải trả  
    "vatValue": 64680,  //Số tiền VAT phải trả  
    "serviceType": "hosting",
    "action": "register",
    "period": 12,
    "planName": "Gói A",
    "type": "wordpress-new"
}
```
