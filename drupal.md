
# UNDRR Common Login Documentation

## Implicit Grant Flow OAuth2 API

Requires read/write database permission

### Step 1, login to common login screen

Request oAuth2 authorization code from the server, here is an example of the request URL https://program.unisdr.org/sso-unisdr/oauth/authorize?client_id=CLIENT_ID&response_type=token&scope=*&redirect_uri=CALLBACK_URL

Querystring Parameters:

* client_id integer, client ID provided by UNISDR
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
      "con_org":"UNISDR",
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
