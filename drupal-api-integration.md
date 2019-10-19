# Drupal 8 API for Systems Integration Documentation

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/


## Regions and Countries

Only published countries on PW are included.

### URL: /sso-unisdr/api/integration/regions_countries

```shell
GET /sso-unisdr/api/integration/regions_countries
```

### JSON Response

```shell
[
   {
      "ctry_id":60,
      "ctry_title":"Fiji",
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
| ctry_id          | Country ID                     | int             |
| ctry_title       | Country name                   | plain text      |
| ctry_iso3_code   | ISO3 code                      | plain text      |
| ctry_un_code     | UN Country ID                  | plain text      |
| cont_id          | PreventionWeb region ID        | int             |
| cont_title       | PreventionWeb region name      | plain text      |
| overview_map_url | Overview Map URL               | plain text; URL |
| flag_url         | Flag URL                       | plain text; URL |
| pw_country_url   | PreventionWeb country page URL | plain text; URL |
| undrr_region     | Collection                     | Array           |
| - isdr_reg_id    | UNDRR region ID                | int             |
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
GET /sso-unisdr/api/integration/undrr_focalpoints
GET /sso-unisdr/public/api/drupal/integration/undrr_focalpoints?undrr_region_id=1
```

### JSON Response

```shell
[
   {
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
| ctry_id           | Country ID                     | int                                                              |
| ctry_title        | Country name                   | plain text                                                       |
| ctry_iso3_code    | ISO3 code                      | plain text                                                       |
| fp_type           | Focal point type               | plain text; possible values: Sendai FW (official), NP (official) |
| org_id            | Organization ID                | int                                                              |
| org_title_long    | Organization name              | plain text                                                       |
| org_title_acronym | Organization acronym           | plain text                                                       |
| org_url           | Organization website URL       | plain text                                                       |
| phone1            | Organization phone 1           | plain text                                                       |
| flag_url          | Flag URL                       | plain text; URL                                                  |
| pw_country_url    | PreventionWeb country page URL | plain text                                                       |
| undrr_region      | Collection                     | Array                                                            |
| - isdr_reg_id     | UNDRR region ID                | int                                                              |
| - isdr_reg_title  | UNDRR region name              | plain text                                                       |














