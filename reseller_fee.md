# [Biểu phí](#fee)
* [Tính toán giá dịch vụ](#tính-toán-giá-dịch-vụ)
* [Lấy biểu phí của đại lý](#lấy-biểu-phí-đại-lý)

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


## [Lấy biểu phí đại lý](#lấy-biểu-phí-đại-lý)
Lấy biểu phí của đại lý
> **API:** /api/rms/v1/fee/getall  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
 
}
```
> **Dữ liệu trả về mẫu(JSON):**   
```
{
    "feeDefId": 32,  
    "type": "register",  
    "serviceType": "domain",  
    "price": 646800,  
    "priceOrigin": 646800,
    "vat": 10,
    "planId": 12,
    "suffixId": 919
}
```
**feeDefId**: id của biểu phí đại lý  
**type**: loại phí: register(đăng ký mới), renew(duy trì), register-vn-service(phí dịch vụ đăng ký cho tên miền .vn), renew-vn-service(phí dịch vụ duy trì cho tên miền .vn), change-registrant(chuyển tên chủ thể), transfer(chuyển nhà đăng ký), registrar-lock(dịch vụ khóa tên miền cấp nhà đăng ký), registry-lock(dịch vụ khóa tên miền cấp Registry VNNIC), dnssec(phí DNSSEC)   
**serviceType**: dịch vụ ['domain', 'hosting', 'email', 'vps']  
**price**: Giá dịch vụ đã chiết khấu,chưa bao gồm VAT  
**priceOrigin**: Giá dịch vụ chưa chiết khấu  
**vat**: Phần trăm VAT  
**planId**: id của danh sách plan
**suffixId**: id của suffix
