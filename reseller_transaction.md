# [Giao dịch](#transaction)
* [Danh sách](#danh-sách)
* [Chi tiết](#chi-tiết)
## [Danh sách](#search)
Tìm kiếm giao dịch của đại lý
> **API:** /api/rms/v1/transaction/list  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "page": 0,
   "pageSize": 30,
   "onlyOrganization": true,
   "type": "invoice",
   "description": "querystring",
   "transactionKey": "register",
   "serviceType": "domain",
   "customerEmail": "customer@example.vn",
   "resourceId": 0,
   "fromCreatedDate": "01/01/2017 00:00",
   "toCreatedDate": "01/01/2017 00:00"
}
```
**page**: trang, mặc định 0  
**pageSize**: số lượng KH lấy về, mặc định 30  
**onlyOrganization**: chỉ là giao dịch của riêng đại lý, không bao gồm đại lý con, mặc định false  
**type**: loại giao dịch[{'invoice': 'hóa đơn'}, {'refund': 'hoàn phí'}, {'receipt': 'nạp quỹ'}, {'arrear': 'truy thu'}]  
**description**: mô tả giao dịch  
**transactionKey**: mã giao dịch[{'register': 'đăng ký mới'},{'renew': 'duy trì'},{'change-registrant': 'đổi tên chủ thể'},
{'protect-privacy': 'ẩn thông tin'},{'transfer': 'chuyển nhà đăng ký'},{'registry-lock': 'registry lock'},{'registrar-lock': 'registrar lock'},
{'change-dns': 'đổi dns'},{'upgrade-plan': 'nâng cấp gói'},{'modify-plan': 'tùy chỉnh gói'},{'backorder': 'đặt chỗ'}]  
**serviceType**: dịch vụ[{'domain': 'tên miền'}, {'hosting': 'hosting'}, {'email': 'email'}, {'vps': 'Cloud VPS'}]  
**customerEmail**: email khách hàng  
**resourceId**: id của dịch vụ(id của tên miền, hosting...)  
**fromCreatedDate**: ngày tạo mới từ  
**toCreatedDate**: ngày tạo mới tới  

## [Chi tiết](#get)
Lấy thông tin chi tiết của giao dịch
> **API:** /api/rms/v1/transaction/detail
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": 0
}
```
**id (bắt buộc)**: id của giao dịch 

