# [Ticket](#ticket)
* [Tạo mới ticket](#tạo-mới-ticket)
* [Phản hồi ticket](#phản-hồi-ticket)
* [Chi tiết ticket](#chi-tiết-ticket)
* [Danh sách ticket](#danh-sách-ticket)

## [Tạo mới ticket](#tạo-mới-ticket)
Tạo mới ticket
> **API:** /api/rms/v1/ticket/create  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
 "subject": "Tiêu đề ticket",  
 "content": "Nội dung ticket",  
 "callbackURL": "Callback URL sau khi phản hồi/đóng ticket gửi lại cho đại lý",  
 "customerEmail": "Email khách hàng",
 "customerName": "Tên khách hàng"
}
```
**subject**: Tiêu đề ticket
**content**: Nội dung ticket  
**callbackURL**: Callback URL sau khi phản hồi/đóng ticket gửi lại cho đại lý  
**customerEmail**: Email khách hàng  
**customerName**: Tên khách hàng  

## [Phản hồi ticket](#phản-hồi-ticket)
Phản hồi ticket
> **API:** /api/rms/v1/ticket/reply  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": id của ticket,  
   "replyContent": nội dung ticket  
}


## [Chi tiết ticket](#chi-tiết-ticket)
Chi tiết ticket
> **API:** /api/rms/v1/ticket/detail  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "id": id của ticket  
}
```

## [Danh sách ticket](#danh-sách-ticket)
Danh sách ticket
> **API:** /api/rms/v1/ticket/list  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "customerEmail": email của khách hàng
}
```

**customerEmail(t**: Email khách hàng  
