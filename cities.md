# Cities API Documentation

Client Credentials Flow OAuth2 API

## Step 1, request access token

Form Post Parameters:

* grant_type string, value should be ‘client_credentials’
* client_id  integer,  client ID given by UNISDR
* client_secret  string, secret provided by UNISDR
* scope string (optional), value should be ‘*’ or null 

```shell
POST /sso-unisdr/oauth/token
```

Response Body

```shell
[ACCESS TOKEN]
```


## Retrieve cities records.

API call have hit rate of 100 per minute. Unique api call are cached in two minutes.

Query String Parameter:

* q string (optional), perform simple search on organization name and acronym (minimum 3 and maximum 30 characters)

Header Parameters:

* Accept string, value ‘application/json’
* Authorization  string, value 'Bearer [ACCESS TOKEN received from step 1]'

```shell
GET /sso-unisdr/api/cities/get/all

GET /sso-unisdr/api/cities/get/all?q=Geneva
```

JSON Response

```shell
{  
   "status":200,
   "success":true,
   "total":2,
   "data":[  
      {  
         "cty_id":87,
         "cty_title":"Geneva",
         "cty_latitude":"46.208358",
         "cty_longitude":"6.142701",
         "cty_location":"Geneva, Switzerland",
         "cty_ctry_iso2":"CH",
         "cty_ctry_id":167,
         "cty_is_capital":0,
         "cty_ishidden":0,
         "cty_dateadded":"2011-03-04 15:58:37",
         "cty_datemodified":"2011-03-04 16:50:23",
         "ctry_id":167,
         "ctry_iso3_code":"CHE",
         "ctry_title":"Switzerland",
         "isdr_regions_id":"4",
         "isdr_regions_title":"Europe",
         "geo_region_id":3,
         "geo_region":"Europe"
      }, ....
   ]
}
```

### Retrieve specific city record.

```shell
GET /sso-unisdr/api/cities/get/id/{id}
```


### Retrieve cities of a country.

```shell
GET /sso-unisdr/api/cities/get/country/id/{id}
```


### Retrieve cities under a specific geographical region.

```shell
GET /sso-unisdr/api/cities/get/geo_region/id/{id}
```


#### Retrieve cities under a specific UNISDR region.

```shell
GET /sso-unisdr/api/cities/get/isdr_region/id/{id}
```



## Add new city

Post Parameters:

* cty_title string				(required), city name
* cty_ctry_id							(required), country id


```shell
POST /sso-unisdr/api/cities/add
```


Return in JSON format

```shell
{  
   "status":200,
   "success":true,
   "message":"Record saved.",
   "cty_id":4771
}
```

## Edit city information

Post Parameters:

* cty_title string				(required), city name
* cty_ctry_id							(required), country id
* cty_latitude numeric		(optional), null or 10.23423423
* cty_longitude numeric 	(optional), null or 11.2322343
* cty_location string			(optional)
* cty_is_capital integer	(optional), allowed values 0 or 1


```shell
POST /sso-unisdr/api/cities/edit/{id}
```

Return in JSON format

```shell
{  
   "status":200,
   "success":true,
   "message":"Record saved.",
}
```




## Retrieve PreventionWeb tagged events content


```shell
GET /sso-unisdr/api/mcr/tagged/pw_events/get/all
```


## Retrieve UNISDR tagged news content

```shell
GET /sso-unisdr/api/mcr/tagged/isdr_news/get/all
```


## Retrieve attachments/links of PreventionWeb entry

```shell
GET /sso-unisdr/api/pw/entry/attachments/get/id/{id}
```



## Retrieve cities records with PreventionWeb HFA LGSAT report

```shell
GET /sso-unisdr/api/cities/pw/policy_plans/get/all
```
