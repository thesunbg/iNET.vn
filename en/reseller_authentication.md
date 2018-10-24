# [Generate tokens](#Authentication)
APIs for iNET Resellers require a token code to authenticate, use the account and password, IP address registered with iNET to perform authentication and retrieve the token code.  
The system uses the JSON Web Tokens (RFC 7519) standard. 

> **Host:** dms.inet.vn  
> **Port:** 443  
> **API:** /api/sso/v1/user/signin  
> **Method:** POST  
> **Body should be a JSON object (JSON):**   
```
{
   "email": "youremail@example.vn",
   "password": "yourpassword"
}
```
**Email (required)**: Email account provided to Resellers  
**Password (required)**: Password provided to Resellers

> **Data returned (JSON):**   
```
{
   "email": "youremail@example.vn",
   "token": "xxx"
}
```
> Use the received token string to set the headers for each API’s submission:  
```
{ headers: 
   {
       token: xxx
   }
}
```
