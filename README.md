# ott

Tables 
app_list
-- id
-- availableBalance
-- key
-- revShare

transactions
-- mobileNo
-- appKey
-- ts
-- packageId
-- 

poviders
-- id
-- providerUsername
-- providerPassword
-- providerBalance
-- url
-- token
-- tokenValidTill

packages
-- id 
-- ottName
-- rate
-- provider



request to renew 
url

{
  appKey:"",
  packageList:[],
  userOttDetails:{
    mobileNo:"",
    email:"",
    name:""
    
  }
}
// how to check the shopify site has only given the request and not anyother person who has managed to get the appKey 

rotateAppKey
//

update the provider rates -- every 12Hrs
// there will be more than one provider





1.To generate a token 

Url: https://qadashboard.playboxtv.in/generateUserToken
Method: POST
Request Body: json body (There will be two keys: email and password)
Format:
{
    "email":String,
    "password":String
}
Response Body => json body status: 201
{
    "success": Boolean,
    "tokens": {
        "accessToken": string
    }
}
If error:
{
    "success": false(Boolean),
    "message": string
}
 
2.Get Customer Details By “customer_id” API Details:
 
Url:https://qadashboard.playboxtv.in/api/getCustomerById
Method: POST
Send JWT access token in headers as 'authorization'
Body: json body (one parameter “customer_id”)
Eg: { “customer_id”:”playbox-457”} 
Note: customer_id is Required
Response: json body
{ success: boolean,
  data: Object
}
 
 
3.Get All Operators Pack by operator email id  API Details:
 
Url:https://qadashboard.playboxtv.in/api/getAllPacks
Method: POST
Send JWT access token in headers as 'authorization'
Body: json body (two parameter “validity” and “email”)
Eg: { “validity”:”30”, “email”:”test@gmail.com”} 
Note: validity can be either one of the following 15, 30, 90, 180, 365
          Validity is optional
          email should be operator’s email
       
Response: json body
{ success: boolean,
  data: array
}
 
4.Create customer and assign pack :
Url: https://qadashboard.playboxtv.in/api/createCustomerAssignPack
Method: POST
Send JWT access token in headers as 'authorization'
 
Body: Json Body
Body Content: 
{
    "customer_id": String, 
    "email" : String (optional), 
    "name" : String, 
    "phone": String eg: “9445563452”, should be 10 digit, 
    "operator_email" : String, 
    "crm_type":String, 
    "server_ip": String, 
    "pack_id": Integer, (will get from getAllPackAPI)
    "date_of_activation":String in MM/DD/YYYY format eg: “10/20/2020”,
    "isp_name":String,
    “txt_partner_id”:String
}
 
 
4.Update customer details 
Url: https://qadashboard.playboxtv.in/api/updateCustomerDetails
Method: POST
Send JWT access token in headers as 'authorization'
 
Body: Json Body
Body Content: 
{
    "customer_id": String, (Required)
    "email" : String, 
    "name" : String, 
    "phone": String eg: “9445563452”, should be 10 digit, 
    "crm_type":String, 
    "server_ip": String, 
    "isp_name":String,
    "bboperator_name":String
 
}
 
Response Body => json body status: 200
{
    "success": Boolean,
    "Data": Object (updated customer details)
}
If error:
{
    "success": false(Boolean),
    "message": string
}
 
 
 







