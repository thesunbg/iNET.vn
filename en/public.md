# [Public API](#public-api)
* [Whois](#whois)
* [Check record](#kiểm-tra-bản-ghi)
## [Whois](#whois)
Whois any domain name
> **API:** /api/public/whois/v1/whois/directly 
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "domainName": "example.vn"
}
```
**domainName**: Domain name

## [Check record](#lookup)
Whois any domain name
> **API:** /api/public/nslookup/v1/nslookup/lookup  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "domain": "example.vn",
   "type": "lookup"
}
```
**domain (required)**: Domain name  
**type (required)**: type of record[lookup, ipv4, ipv6, cname, mx, ns, soa, srv, txt]
