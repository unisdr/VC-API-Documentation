
# UNDRR Common Login Documentation

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/

## General

### Encrypt password

Form Post Parameter:

* password string

```shell
POST /sso-unisdr/api/user/encrypt_password
```

Error response:

```shell
{
  "status": 400,
  "error": [
    "Do not use simple words or patterns for password."
  ],
  "success": false
}
```

Success response:

```shell
{
  "status": 200,
  "success": true,
  "password_encrypted": "XX"
}
```

### Get application/client name

Querystring Parameters:

* client_id integer
* client_home_url string


```shell
GET /sso-unisdr/api/client/get_name?client_id=XX&client_home_url=XX
```

https://program.unisdr.org/sso-unisdr-development/api/client/get_name?client_id=13&client_home_url=http://unisdr.digitalchannels.technology


Success response:

```shell
{"status":200,"success":true,"data":{"name":"XX"}}
```

## Client Credentials Grant Flow OAuth2

https://oauth.net/2/grant-types/client-credentials/

### Client

#### Request client credential access token

Form Post Parameters:

* grant_type string, value should be ‘client_credentials’
* client_id integer, client ID given by UNDRR
* client_secret string, secret provided by UNDRR
* scope string (optional), value should be ‘*’ or null

```shell
POST /sso-unisdr/oauth/token
```

Example PHP code:

```shell
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "/sso-unisdr/oauth/token",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "grant_type=client_credentials&client_id=XX&client_secret=XX&scope=*",
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

Response Body:

```shell
[ACCESS TOKEN]
```


#### Registration

Standard registration URL https://www.preventionweb.net/myprofile/register

Registration URL coming from other applications e.g. Sendain Framework Voluntary commitments https://sendaicommitments.unisdr.org. There will be additional information displayed on the page upon email approval.

https://www.preventionweb.net/myprofile/register?url=https%3A%2F%2Fsendaicommitments.unisdr.org&client_id=9

Authentication: Client credentials grant

Header Parameters:

* Accept string, value ‘application/json’
* Authorization string, value 'Bearer [Client: ACCESS TOKEN]'

Form Post Parameters:

* email string, value should be a valid email address
* password string, the encrypted text must use bcrypt encryption, use the API endpoint on the general section to encrpyt the password
* con_id integer, foreign key of Drupal user table (user.id), this a way for common login to associate the account information with drupal

```shell
POST /sso-unisdr/api/user/registration
```

Example PHP code:

```shell
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "/sso-unisdr/api/user/registration",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "email=XX&password=XX&con_id=XX",
  CURLOPT_HTTPHEADER => array(
    "accept: application/json",
    "authorization: Bearer XX",
    "content-type: application/x-www-form-urlencoded"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

Error response:

```shell
{
   "status":400,
   "error":[
      "The email address field is required.",
      "The password field is required.",
      "Password must contain at least one number and one uppercase and lowercase letter, and at least 12 characters.",
      "Do not use simple words or patterns for password.",
      "The Contact ID is required."
   ]
}
```

Success response:

```shell
{
  "status": 200,
  "error": []
}
```


#### Reset password

Endpoint to call after completing the reset password flow. This endpoint can also be use by Drupal administrator to reset the password of the user.

The system will revoke the token automatically.

https://www.preventionweb.net/myprofile/forgotpassword

Authentication: Client credentials grant

Header Parameters:

* Accept string, value ‘application/json’
* Authorization string, value 'Bearer [Client: ACCESS TOKEN]'

Form Post Parameters:

* email string, value should be a valid email address
* password_new string, plain text

```shell
POST /sso-unisdr/api/user/forgot_password_reset
```

Example PHP code:

```shell
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "/sso-unisdr/api/user/forgot_password_reset",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "email=XX&password_new=XX",
  CURLOPT_HTTPHEADER => array(
    "accept: application/json",
    "authorization: Bearer XX",
    "content-type: application/x-www-form-urlencoded"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```


Success response:

```shell
{
  "status": 200,
  "error": [],
  "success": true
}
```

Error response:

```shell
{
   "status":400,
   "error":[
      "The email address doesn't exists.",
      "New password must contain at least one number, one uppercase and lowercase letter, and at least 12 characters.",
   ]
}
```


#### Change email

Endpoint to call after completing the change email flow.

The system will revoke the token automatically.

Authentication: Client credentials grant

Header Parameters:

* Accept string, value ‘application/json’
* Authorization string, value 'Bearer [Client: ACCESS TOKEN]'

Form Post Parameters:

* email_current string, value should be a valid email address
* email_new string, value should be a valid email address that doesn't exists yet in the system

```shell
POST /sso-unisdr/api/user/change_email
```

Example PHP code:

```shell
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "/sso-unisdr/api/user/change_email",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "email_current=XX&email_new=XX",
  CURLOPT_HTTPHEADER => array(
    "accept: application/json",
    "authorization: Bearer XX",
    "content-type: application/x-www-form-urlencoded"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

Error response:

```shell
{
   "status":400,
   "error":[
      "The email new and email current must be different.",
      "The email has already been taken.",
   ]
}  
```




#### Check if email address doesn't exists

Endpoint to call to check if the email address doesn't exists in our database.

Authentication: Client credentials grant

Header Parameters:

* Accept string, value ‘application/json’
* Authorization string, value 'Bearer [Client: ACCESS TOKEN]'

Form Post Parameters:

* email string, value should be a valid email address

```shell
POST /sso-unisdr/api/user/email_not_exists
```

Success response:

```shell
{
  "status": 200,
  "error": [],
  "success": true
}
```

Error response:

```shell
{
   "status":400,
   "error":[
      "The email address is a required field.",
      "Invalid email address.",
      "The email address already exists.",
   ]
}  
```

### Delete Account (by admin)

Drupal admin delete the account of the user from the admin interface of Drupal then sends a remote call to common login to delete the access credentials.

Active tokens will be set to invalid when request is successful.

Authentication: Client credentials grant

Header Parameters:

* Accept string, value ‘application/json’
* Authorization string, value 'Bearer [Client: ACCESS TOKEN]'

Form Post Parameters:

* email string, value should be a valid email address
* drupal_id integer, primary of users table in Drupal

```shell
POST /sso-unisdr/api/admin/delete_account
```

Success response:

```shell
{
  "status": 200,
  "error": []
}
```


## User Authenticated Flow using Password Grant

Info about password grant https://oauth.net/2/grant-types/password/

Return format:

```shell
{"token_type":"Bearer","expires_in":86400,"access_token":XX","refresh_token":"XX"}
```

The user gets authenticated using the password flow grant https://www.preventionweb.net/myprofile/login. The common login gives the successful authenticated user an access token and refresh token, the application should save this information on the user session.


### Update Drupal ID

Update existing common login account with Drupal ID.

TODO: Discuss with Everis if this is okay

Form Post Parameters:

* email string, value should be a valid email address
* drupal_id integer, primary key of Drupal user table (user.id), this a way for common login to associate the account information with drupal


### Check logged in account email address and password

This function was used to verify the logged in account credentials before performing the change password and email function.

Authentication: Password grant

Header Parameters:

* Accept string, value ‘application/json’
* Authorization string, value 'Bearer [User: ACCESS TOKEN]'

Post Parameters:

* email string, account email address
* password string, account password in plain text

```shell
POST /sso-unisdr/api/user/check_emailaddress_password
```

Success response:

```shell
{
  "status": 200,
  "success": true
}
```

Error response:

```shell
{
  "message": "Server Error"
}
```


#### Change account password

Please note that when the password was changed all active user tokens will be invalidated by the system.

TODO: add web hooks functionality to notify oAuth2 Clients that token for the account has been invalidated.

Authentication: Password grant

Header Parameters:

* Accept string, value ‘application/json’
* Authorization string, value 'Bearer [User: ACCESS TOKEN]'

Form Post Parameters:

* email string, account email address
* password string, account password in plain text
* password_new string, plain text

```shell
POST /sso-unisdr/api/user/change_password
```

Success response:

```shell
{
  "status": 200,
  "error": []
}
```

### Delete Account (user)

Active tokens will be set to invalid when request is successful.

Authentication: Password grant

Header Parameters:

* Accept string, value ‘application/json’
* Authorization string, value 'Bearer [User: ACCESS TOKEN]'

```shell
POST /sso-unisdr/api/user/delete_account
```

Success response:

```shell
{
  "status": 200,
  "error": []
}
```


### Revoke User Token

When the user logged-out of the system, call this function to invalidate all the active tokens.

Authentication: Password grant

Header Parameters:

* Accept string, value ‘application/json’
* Authorization string, value 'Bearer [User: ACCESS TOKEN]'

```shell
POST /sso-unisdr/api/user/revoke_token
```

Success response:

```shell
{
  "status": 200,
  "error": []
}
```

## Implicit Grant Flow OAuth2 API

### Step 1, login to common login screen

Request oAuth2 authorization code from the server, here is an example of the request URL https://program.unisdr.org/sso-unisdr/oauth/authorize?client_id=CLIENT_ID&response_type=token&scope=*&redirect_uri=CALLBACK_URL

Querystring Parameters:

* client_id integer, client ID provided by UNDRR
* redirect_uri string, redirect URI or callback URL provided by the client, must be exactly as saved in the database
* response_type string, value should be ‘token’
* scope string, value should be ‘*’ or null
* state string (optional)

```shell
GET /sso-unisdr/oauth/authorize?client_id=CLIENT_ID&response_type=token&scope=*&redirect_uri=CALLBACK_URL
```

Correct credentials will redirect to the callback URL, the access token is available in the URL.

```shell
[CALLBACK URL]#access_token=[ACCESS TOKEN]&token_type=Bearer&expires_in=86400
```




### Step 2, retrieve user information

Retrieve logged-in users information.

Header Parameters:

* Accept string, value ‘application/json’
* Authorization  string, value 'Bearer [ACCESS TOKEN received from step 2]'

```shell
GET /sso-unisdr/api/user
```

Returns users information in JSON format:

```shell
{  
   "status":200,
   "success":1,
   "data":{  
      "con_id":123321,
      "con_fname":"Nho",
      "con_lname":"Eod",
      "con_org":"UNDRR",
      "con_position":"Programmer",
      "con_email":"some_email@email.com",
      "name":"Nho Eod"
   }
}
```


### Step 4, logout

Revoke active session, cookies and token. e.g. https://program.unisdr.org/sso-unisdr/logout?redirect_uri=https%3A%2F%2Fvc-dev.eac-bkk.org%2Fauth%2Flogout



Query String Parameter:

* redirect_uri string, vURL to redirect after calling the logout function. Value should be a valid URL otherwise the redirect will be ignored.

```shell
GET /sso-unisdr/logout?redirect_uri=https%3A%2F%2Fvc-dev.eac-bkk.org%2Fauth%2Flogout
```


## Password Validation 

Checks the password if it is valid based on the dictionaries and REGEX

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/check_password

```shell
GET /sso-unisdr/api/drupal/migration/check_password
```

### JSON Response

```shell
[
  {
    "status": 200,
    "success": true,
    "password_encrypted": "$2y$10$v2kyiP3yIPIUz56GJkV4pedGi8X5lqpAJR6YlICSxTAHRe3QzOKPy",
    "error": ["The password must contain at least one number, one uppercase and lowercase letter, and at least 12 characters."]
  }
]
```

### Field definition

| Field                 | Description                | Type/Value              |
|-----------------------|----------------------------|-------------------------|
| status                | Status code of request     | int 				       |
| success            	| True if valid else false   | bool (true|false)       |
| password_encrypted    | The encrypted password     | plain text              |
| error    				| Error message     		 | plain text              |


