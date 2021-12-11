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











