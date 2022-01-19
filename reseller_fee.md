# [Biểu phí](#fee)
* [Tính toán giá dịch vụ](#tính-toán-giá-dịch-vụ)
* [Lấy biểu phí của đại lý](#lấy-biểu-phí-đại-lý)
* [Lấy giá bán của đại lý](#lấy-giá-bán-đại-lý)
* 
## [Tính toán giá dịch vụ](#tính-toán-giá-dịch-vụ)
Tính toán giá của dịch vụ
> **API:** /api/rms/v1/fee/getprice  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
 "serviceType": "domain",   
 "action": "register",   
 "name": "example.vn", 
 "period": 1 
}
```
**serviceType**: dịch vụ ['domain','hosting', 'email', 'vps']  
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

## [Lấy giá bán của đại lý](#lấy-giá-bán-đại-lý)
Lấy giá bán của đại lý
> **API:** /api/rms/v1/feeselling/getbysuffixid
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{}
```
```
```
> **Dữ liệu trả về mẫu(JSON):**   
```
{
		"id": 19884,
		"orgId": 4063,
		"type": "register", // Loại register: đang ký mới, renew: giạn, transfer: chuyển NĐK
		"serviceType": "domain",
		"price": 770000, // Giá bán của đại lý cho khách hàng
		"priceCost": 704000, // Giá gốc của iNET
		"suffixId": 919,
		"vat": 0,
		"suffix": "vn",
		"priority": 1
	}
``` 
