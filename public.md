# [Public API](#public-api)
* [Whois](#whois)
* [Kiểm tra bản ghi](#kiểm-tra-bản-ghi)
## [Whois](#whois)
Whois tên miền bất kỳ
> **API:** /api/public/whois/v1/whois/directly 
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "domainName": "example.vn"
}
```
**domainName**: tên miền

## [Kiểm tra bản ghi](#lookup)
Kiểm tra bản ghi tên miền bất kỳ
> **API:** /api/public/nslookup/v1/nslookup/lookup  
> **Phương thức:** POST  
> **Dữ liệu data body mẫu(JSON):**   
```
{
   "domain": "example.vn",
   "type": "lookup"
}
```
**domain (bắt buộc)**: tên miền  
**type (bắt buộc)**: loại bản ghi[lookup, ipv4, ipv6, cname, mx, ns, soa, srv, txt]
