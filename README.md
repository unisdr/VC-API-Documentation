
# UNISDR Common Login Documentation


## Authorization Code Flow OAuth2 API

### Step 1, login to common login screen

Request oAuth2 authorization code from the server, here is an example of the request URL https://program.unisdr.org/sso-unisdr-development/oauth/authorize?client_id=CLIENT_ID&response_type=code&scope=*&redirect_uri=CALLBACK_URL

```shell
GET https://program.unisdr.org/sso-unisdr-development/oauth/authorize?client_id=CLIENT_ID&response_type=code&scope=*&redirect_uri=CALLBACK_URL
```

When user entered the correct login credentials the systen redirects to the callback URL, the ‘autorization code’ is in the URL querystring 'code’, syntax [client call back URL]?code=AUTHORIZATION_CODE, example https://eac.bkk/callback?code=AUTHORIZATION_CODE


