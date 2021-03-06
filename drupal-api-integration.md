# Drupal 8 API for Systems Integration Documentation

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/



## Registration

### URL: /sso-unisdr/api/user/drupal_user_registration

```shell
POST /sso-unisdr/api/user/drupal_user_registration
```

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Form Post Parameters
* email string, value should be a valid email address
* password string, the encrypted text must use bcrypt encryption, use the API endpoint on the general section to encrpyt the password
* drupal_id integer, primary key of Drupal user table (user.id), this a way for the common login system to associate the account information with drupal

### Error response:

```shell
{
   "status":400,
   "error":[
      "The email address field is required.",
      "The password field is required.",
      "Password must contain at least one number and one uppercase and lowercase letter, and at least 12 characters.",
      "Do not use simple words or patterns for password.",
      "The drupal_id is required."
   ]
}
```

### Success response:

```shell
{
  "status": 200,
  "error": []
}
```

## Update account drupal ID

### URL: /sso-unisdr/api/user/add_drupal_id

This endpoint will set the drupal_id of an account.

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Parameters
* email, string
* drupal_id, integer

```shell
POST /sso-unisdr/api/drupal/integration/add_drupal_id
```

## UNDRR Regions

### URL: /sso-unisdr/api/drupal/integration/undrr_regions

```shell
GET /sso-unisdr/api/drupal/integration/undrr_regions
```

### JSON Response

```shell
[
   {
      "isdr_reg_id":1,
      "isdr_reg_title":"Africa"
   },
   {
      "isdr_reg_id":2,
      "isdr_reg_title":"Americas"
   },
   {
      "isdr_reg_id":5,
      "isdr_reg_title":"Arab States"
   },
   {
      "isdr_reg_id":3,
      "isdr_reg_title":"Asia and Pacific"
   },
   {
      "isdr_reg_id":4,
      "isdr_reg_title":"Europe"
   },
   {
      "isdr_reg_id":24,
      "isdr_reg_title":"Suva"
   }
]
```

## PreventionWeb Regions

### URL: /sso-unisdr/api/drupal/integration/preventionweb_regions

```shell
GET /sso-unisdr/api/drupal/integration/preventionweb_regions
```

### JSON Response

```shell
[
   {
      "cont_id":1,
      "cont_title":"Africa"
   },
   {
      "cont_id":2,
      "cont_title":"Americas"
   },
   {
      "cont_id":4,
      "cont_title":"Asia"
   },
   {
      "cont_id":3,
      "cont_title":"Europe"
   },
   {
      "cont_id":5,
      "cont_title":"Oceania"
   }
]
```


## Regions and Countries

Only published countries on PW are included.

IMPORTANT NOTE: the approach for overview_map_url and flag_url will be revisited for the PreventionWeb migration. The images should be moved to Drupal media module.

### URL: /sso-unisdr/api/drupal/integration/regions_countries


```shell
GET /sso-unisdr/api/drupal/integration/regions_countries
```

### JSON Response

```shell
[
   {
      "ctry_id":60,
      "ctry_title":"Fiji",
      "ctry_title_sp":"Fiji",
      "ctry_iso3_code":"FJI",
      "ctry_un_code":"242",
      "cont_id":5,
      "cont_title":"Oceania",
      "overview_map_url":"https:\/\/www.preventionweb.net\/english\/images\/countries\/maps\/fji.gif",
      "flag_url":"https:\/\/www.preventionweb.net\/assets\/shared\/images\/flags\/fji.jpg",
      "pw_country_url":"https:\/\/www.preventionweb.net\/english\/countries\/oceania\/fji",
      "undrr_region":[
         [
            {
               "isdr_reg_id":3,
               "isdr_reg_title":"Asia and Pacific"
            },
            {
               "isdr_reg_id":24,
               "isdr_reg_title":"Suva"
            }
         ]
      ]
   },
   ...
]
```

### Field definition

| Field            | Description                    | Type/Value      |
|------------------|--------------------------------|-----------------|
| focalpoint_id    | Focalpoint ID                  | int (pk)        |
| domain           | Domain                         | plain text      |
| ctry_id          | Country ID                     | int (fk)        |
| ctry_title       | Country name                   | plain text      |
| ctry_title_sp    | Country name in Spanish        | plain text      |
| ctry_iso3_code   | ISO3 code                      | plain text      |
| ctry_un_code     | UN Country ID                  | plain text      |
| cont_id          | PreventionWeb region ID        | int (fk)        |
| cont_title       | PreventionWeb region name      | plain text      |
| overview_map_url | Overview Map URL               | plain text; URL |
| flag_url         | Flag URL                       | plain text; URL |
| pw_country_url   | PreventionWeb country page URL | plain text; URL |
| undrr_region     | Collection                     | Array           |
| - isdr_reg_id    | UNDRR region ID                | int (fk)        |
| - isdr_reg_title | UNDRR region name              | plain text      |


## Official Sendai Framework and National Platform focal point

This endpoint will retrieve the Official Sendai Framework and National Platform focal point managed through our intranet. Resultset is cached for 60 minutes.

### Destination pages
* https://ijjqd4.axshare.com/#g=1&p=region__americas___carribean_-_countries

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/integration/undrr_focalpoints

#### Querystring Parameter

* undrr_region_id (optional), integer

```shell
GET /sso-unisdr/api/drupal/integration/undrr_focalpoints
GET /sso-unisdr/api/drupal/integration/undrr_focalpoints?undrr_region_id=1
```

### JSON Response

```shell
[
   {
      "focalpoint_id":287434,
      "ctry_id":153,
      "ctry_title":"Seychelles",
      "ctry_iso3_code":"SYC",
      "fp_type":"Sendai FW (official)",
      "org_id":4985,
      "org_title_acronym":"DRDM",
      "org_title_long":"Division of Risk and Disaster Management",
      "org_url":"http:\/\/www.drdm.gov.sc",
      "phone1":"+248 4672200 ",
      "flag_url":"https:\/\/www.preventionweb.net\/assets\/shared\/images\/flags\/syc.jpg",
      "pw_country_url":"https:\/\/www.preventionweb.net\/english\/countries\/africa\/syc",
      "undrr_region":[
         [
            {
               "isdr_reg_id":1,
               "isdr_reg_title":"Africa"
            }
         ]
      ]
   },
   ...
]
```

### Field definition

| Field             | Description                    | Type/Value                                                       |
|-------------------|--------------------------------|------------------------------------------------------------------|
| focalpoint_id     | Focalpoint ID                  | int (primary key)                                                |
| ctry_id           | Country ID                     | int  (fk)                                                        |
| ctry_title        | Country name                   | plain text                                                       |
| ctry_iso3_code    | ISO3 code                      | plain text                                                       |
| fp_type           | Focal point type               | plain text; possible values: Sendai FW (official), NP (official) |
| org_id            | Organization ID                | int  (fk)                                                        |
| org_title_long    | Organization name              | plain text                                                       |
| org_title_acronym | Organization acronym           | plain text                                                       |
| org_url           | Organization website URL       | plain text                                                       |
| phone1            | Organization phone 1           | plain text                                                       |
| flag_url          | Flag URL                       | plain text; URL                                                  |
| pw_country_url    | PreventionWeb country page URL | plain text                                                       |
| undrr_region      | Collection                     | Array                                                            |
| - isdr_reg_id     | UNDRR region ID                | int  (fk)                                                        |
| - isdr_reg_title  | UNDRR region name              | plain text                                                       |














