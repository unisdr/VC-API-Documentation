
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



### Step 2, exchange authorization code to access token

The authorization code that was received from step 1 should be exchanged with the access token by calling the post request with the appropriate form fields, the server will respond with the access token credentials in json format.

Form Post Parameters:

* grant_type string, value should be ‘authorization_code’
* client_id  integer,  client ID given by UNISDR
* client_secret  string, secret provided by UNISDR
* redirect_uri  string, redirect or callback URL of the client
* code string, the code (AUTHORIZATION_CODE) received from step 1

```shell
POST /sso-unisdr-development/oauth/token
```

Returns an access credentials in JSON format:

```shell
{  
   access_token:[ACCESS_TOKEN],
   token_type:bearer,
   expires_in:2592000,
   refresh_token:[REFRESH_TOKEN],
   scope:
}
```




### Step 3, retrieve user information

Retrieve logged-in users information.

Header Parameters:

* Accept string, value ‘application/json’
* Authorization  string, value 'Bearer [ACCESS TOKEN received from step 2]'

```shell
GET /sso-unisdr-development/api/user
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

Revoke active session, cookies and token. e.g. https://program.unisdr.org/sso-unisdr-development/logout?=redirect_uri=https%3A%2F%2Fvc-dev.eac-bkk.org%2Fauth%2Flogout



Query String Parameter:

* redirect_uri string, vURL to redirect after calling the logout function. Value should be a valid URL otherwise the redirect will be ignored.

```shell
GET /sso-unisdr-development/logout?=redirect_uri=https%3A%2F%2Fvc-dev.eac-bkk.org%2Fauth%2Flogout
```




## Client Credentials Flow OAuth2 API

### Retrieve PreventionWeb.net published organization

#### Step 1, request access token

Form Post Parameters:

* grant_type string, value should be ‘client_credentials’
* client_id  integer,  client ID given by UNISDR
* client_secret  string, secret provided by UNISDR
* scope string (optional), value should be ‘*’ or null 

```shell
POST /sso-unisdr-development/oauth/token
```

#### Step 2, call organizations API. Use the access token received from step 1 in the request header.

API call have hit rate of 60 per minute. Unique resultset are cached in two minutes.

Query String Parameter:

* page integer, page number

Header Parameters:

* Accept string, value ‘application/json’
* Authorization  string, value 'Bearer [ACCESS TOKEN received from step 1]'

```shell
GET /sso-unisdr-development/api/organization/get?page=1
```

JSON Response

```shell
{
   "current_page": 1,
   "data": [
      {
         "org_id": 1127,
         "org_title_long": "Save the Children U.S.",
         "org_title_acronym": "",
         "org_is_local_gov": 0,
         "orgtype_id": 3,
         "orgtype_title": "Non-Governmental Organization",
         "orgtype_short": "NGO",
         "address_street": "2000 M Street NW; Suite 500",
         "address_town": "Washington D.C.",
         "address_zip_cde": "20036",
         "country_id": 185,
         "country_iso3": "USA",
         "country_un_code": "840",
         "country_title": "United States of America"
      },
      {
         "org_id": 3099,
         "org_title_long": "UN Office for the Coordination of Humanitarian Affairs - Geneva Office",
         "org_title_acronym": "OCHA",
         "org_is_local_gov": 0,
         "orgtype_id": 1,
         "orgtype_title": "UN & International Organization",
         "orgtype_short": "UN & Intl",
         "address_street": "8-14 Palais de Nations",
         "address_town": "Geneva 10",
         "address_zip_cde": "1211",
         "country_id": 167,
         "country_iso3": "CHE",
         "country_un_code": "756",
         "country_title": "Switzerland"
      },
      ...
   ],
   "first_page_url": "/api/organization/get?page=1",
   "from": 1,
   "last_page": 871,
   "last_page_url": "/api/organization/get?page=871",
   "next_page_url": "/api/organization/get?page=2",
   "path": "/api/organization/get",
   "per_page": 15,
   "prev_page_url": null,
   "to": 15,
   "total": 13065,
   "status": 200,
   "success": 1
}
```


## PreventionWeb Public API

### Retrieve organization type

```shell
GET https://www.preventionweb.net/v2/api/v1/org_type/get/output.json
```
JSON Response

```shell
{  
   "results":[  
      {  
         "id":1,
         "name":"UN & International Organization"
      },
      {  
         "id":2,
         "name":"Governments"
      },
      {  
         "id":8,
         "name":"Regional Intergovernmental Organization"
      },
      {  
         "id":3,
         "name":"Non-Governmental Organization"
      },
      {  
         "id":7,
         "name":"Academic & Research Institution"
      },
      {  
         "id":4,
         "name":"Private Sector"
      },
      {  
         "id":5,
         "name":"News & Media"
      },
      {  
         "id":6,
         "name":"Networks & Other"
      }
   ],
   "total":8,
   "status":200
}
```

