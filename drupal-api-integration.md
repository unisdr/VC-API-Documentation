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




## Sendai Voluntary Commitments - Organization Commitments

This endpoint will retrieve the organizations Sendai Voluntary Commitments. Resultset is cached for 60 minutes.


### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/integration/sfvc/organization_commitments?partnersOrganizationNames=[ORG_NAME]

#### Querystring Parameter

* partnersOrganizationNames (required), string (case sensitive)

```shell
GET /sso-unisdr/api/integration/sfvc/organization_commitments?partnersOrganizationNames=United+Nations+Office+for+Disaster+Risk+Reduction
```

### JSON Response

```shell
{
  "data": [
    {
      "commitmentVersionId": 445,
      "commitmentVersion": "2.0",
      "commitmentIdentifier": "20190307_007",
      "commitmentPublicationStatus": [
        "ACTIVE"
      ],
      "commitmentPublicationStatusValues": [
        "ACTIVE"
      ],
      "status": "PUBLISHED",
      "statusIsFinal": true,
      "title": "Promoting the Making Cities Resilient and Sustainable Campaign in Asia Pacific ",
      "organisation": "United Cities and Local Governments Asia-Pacific",
      "partners": [
        "United Cities and Local Governments",
        "United Nations Office for Disaster Risk Reduction"
      ],
      "implementers": [
        "United Cities and Local Governments Asia-Pacific"
      ],
      "partnerOrgs": [
        {
          "organizationRole": "PARTNER",
          "organizationReferenceKey": "3346",
          "organizationName": "United Cities and Local Governments",
          "organizationAddress": "Carrer Avinyó, 15, Barcelona, Spain",
          "organizationCategory": "NETWORKS_AND_OTHER",
          "organizationWebsite": "http:\/\/www.uclg.org\/",
          "organizationCountryCca3": "ESP"
        },
        {
          "organizationRole": "PARTNER",
          "organizationReferenceKey": "1171",
          "organizationName": "United Nations Office for Disaster Risk Reduction",
          "organizationAddress": "9-11 rue de Varembé, Geneva, Switzerland",
          "organizationCategory": "UN_AND_IO",
          "organizationWebsite": "https:\/\/www.undrr.org\/",
          "organizationCountryCca3": "CHE"
        }
      ],
      "implementerOrgs": [
        {
          "organizationRole": "IMPLEMENTER",
          "organizationReferenceKey": "8672",
          "organizationName": "United Cities and Local Governments Asia-Pacific",
          "organizationAddress": "Mitra Praja Building 2nd Floor, Jl. Sunter Permai Raya No. 1, Jakarta, Indonesia",
          "organizationCategory": "NETWORKS_AND_OTHER",
          "organizationWebsite": "http:\/\/www.uclg-aspac.org\/",
          "organizationCountryCca3": "IDN"
        }
      ],
      "scopes": [
        "Regional - Asia, Oceania"
      ],
      "countries": [],
      "alpha3CountryCodes": [],
      "shortDescription": "The programme contributes to the increase in the number of Local Governments (LGs) that sign the Making Cities Resilient (MCR) Campaign. It fosters the implementation of the Sendai Framework for Disaster Risk Reduction at the local level and supports city DRR action plans to meet Target E.",
      "lastUpdated": "2021-02-02",
      "illustratingPhoto": {
        "fileName": "Hal 16-17.jpg",
        "fileReference": "ddfdeea2-7c53-46f6-b63c-14409df39dff",
        "mimeType": "image\/jpeg",
        "sizeInBytes": 94069,
        "imageURL": "https:\/\/sendaicommitments.undrr.org\/api\/public\/file-storage\/ddfdeea2-7c53-46f6-b63c-14409df39dff\/show"
      },
      "latestPublishedVersion": true,
      "url": "https:\/\/sendaicommitments.undrr.org\/commitments\/20190307_007"
    },
	...
  ],
  "total": 4,
  "status": 200,
  "url_view_all_map": "https:\/\/sendaicommitments.undrr.org\/commitments?partnersOrganizationNames=United+Nations+Office+for+Disaster+Risk+Reduction",
  "url_view_all_list": "https:\/\/sendaicommitments.undrr.org\/commitments?partnersOrganizationNames=United+Nations+Office+for+Disaster+Risk+Reduction&viewType=MAP"
}
```

### Field definition

| Field             | Description                    | Type/Value                                                       |
|-------------------|--------------------------------|------------------------------------------------------------------|











