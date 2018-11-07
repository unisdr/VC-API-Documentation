
# UNISDR Common Login Documentation


## Authorization Code Flow OAuth2 API

### Step 1, login to common login screen

Request oAuth2 authorization code from the server, here is an example of the request URL https://program.unisdr.org/sso-unisdr-development/oauth/authorize?client_id=CLIENT_ID&response_type=code&scope=*&redirect_uri=CALLBACK_URL

Querystring Parameters:

* client_id integer, client ID provided by UNISDR 
* redirect_uri string,  edirect URI or callback URL provided by the client
* response_type string, value should be ‘code’ 
* scope string, value should be ‘*’ or null 
* state string (optional)


```shell
GET /sso-unisdr-development/oauth/authorize?client_id=CLIENT_ID&response_type=code&scope=*&redirect_uri=CALLBACK_URL
```

When user entered the correct login credentials the systen redirects to the callback URL, the ‘autorization code’ is in the URL querystring 'code’, syntax [client call back URL]?code=AUTHORIZATION_CODE, example https://eac.bkk/callback?code=AUTHORIZATION_CODE



### Step2, exchange authorization code to access token

The authorization code that was received from step 1 should be exchanged with the access token by calling the post request with the appropriate form fields, the server will respond with the access token credentials in json format.

Form Post Parameters:

* grant_type string, value should be ‘authorization_code’
* client_id  integer,  client ID given by UNISDR
* client_secret  string, secret provided by UNISDR
* redirect_uri  string, redirect or callback URL of the client
* code string, the code (AUTHORIZATION_CODE) received from step 1

```shell
POST /sso-unisdr-development/oauth/token

Returns an access credentials in json format:

{
access_token: ACCESS_TOKEN,
token_type: bearer,
expires_in: 2592000,
refresh_token: REFRESH_TOKEN,
scope:
}
```




### Step3, retrieve user information

Retrieve logged-in users information.

Header Parameters:

* Accept string, value ‘application/json’
* Authorization  string, value 'Bearer [ACCESS TOKEN received from step 2]'

```shell
GET /sso-unisdr-development/api/user

Returns an users information in json format:

{

}
```


### Step4, logout

Revoke active session, cookies and token. e.g. https://program.unisdr.org/sso-unisdr-development/logout?=redirect_uri=https%3A%2F%2Fvc-dev.eac-bkk.org%2Fauth%2Flogout



Query String Parameter:

* redirect_uri string, vURL to redirect after calling the logout function. Value should be a valid URL otherwise the redirect will be ignored.

```shell
GET /sso-unisdr-development/logout?=redirect_uri=https%3A%2F%2Fvc-dev.eac-bkk.org%2Fauth%2Flogout
```
