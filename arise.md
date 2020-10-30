# Taxonomy

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



## Themes (taxonomy)


### URL: /sso-unisdr/api/drupal/migration/taxonomy_themes

```shell
GET /sso-unisdr/api/drupal/migration/taxonomy_themes
```


### JSON Response

```shell
[
   {
      "scat_id":41,
      "scat_title":"Advocacy & Media"
   },
   {
      "scat_id":31,
      "scat_title":"Capacity Development"
   },
   ...
]
```





## Language (taxonomy)

### URL: /sso-unisdr/drupal/migration/taxonomy_languages

```shell
GET /sso-unisdr/drupal/migration/taxonomy_languages
```
### JSON Response

```shell
[
   {
      "lng_id":6,
      "lng_title":"Arabic"
   },
   {
      "lng_id":5,
      "lng_title":"Chinese"
   },
   {
      "lng_id":1,
      "lng_title":"English"
   },
   {
      "lng_id":2,
      "lng_title":"French"
   },
   {
      "lng_id":8,
      "lng_title":"Russian"
   },
   {
      "lng_id":4,
      "lng_title":"Spanish"
   }
]
```

### Field definition

| Field     | Description | Type/Value |
|-----------|-------------|------------|
| lng_id    | ID          | int        |
| lng_title | Language    | plain text |



## Hazards (taxonomy)

### URL: /sso-unisdr/api/drupal/migration/taxonomy_hazards

```shell
GET /sso-unisdr/api/drupal/migration/taxonomy_hazards
```


### JSON Response

```shell
[
   {
      "scat_id":67,
      "scat_title":"Avalanche"
   },
   {
      "scat_id":56,
      "scat_title":"Cold Wave"
   },
   ...
]
```

### Field definition

| Field      | Description | Type/Value |
|------------|-------------|------------|
| scat_id    | ID          | int        |
| scat_title | Hazard name | plain text |








# Content Type

CONDITION: Pre-filtered by content publication date >= 2020 and theme = private sector


## Documents and publications

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/arise/integration/publications

```shell
GET /sso-unisdr/api/arise/integration/publications
```

### JSON Response

```shell
[
  {
    "ent_id": 35650,
    "ent_sec_id": 8,
    "field_image_id": "35650",
    "field_title": "Natural disaster management: collaborative communities for safer futures",
    "ent_dateadded": "2013-11-26 11:40:57",
    "ent_datemodified": "2018-08-27 13:11:33",
    "field_body_trimmed": "This policy paper examines the performance of frameworks related to natural disaster management in Queensland and the challenges remaining. It proposes the adoption of a series of recommendations in order to place Queensland in a stronger, more resilient position in the face of future disasters: (i) ...",
    "field_authors": "",
    "field_title_original": "",
    "field_year_of_publication": 2013,
    "current_url": [
      {
        "id": "8356501",
        "ent_id": 35650,
        "url": "https:\/\/www.preventionweb.net\/publications\/view\/35650"
      }
    ],
    "field_country": [
      {
        "ctry_id": 9,
        "ctry_iso3_code": "AUS"
      }
    ],
    "field_organization": [
      {
        "org_id": 13633,
        "org_title_long": "Left Right Think-Tank",
        "org_title_acronym": "Left Right"
      }
    ],
    "field_region": [
      {
        "cont_id": 4
      }
    ],
    "field_hazards": [
      {
        "scat_id": 143
      }
    ],
    "field_themes": [
      {
        "scat_id": 42
      },
      {
        "scat_id": 104
      },
      {
        "scat_id": 106
      },
      {
        "scat_id": 108
      },
      {
        "scat_id": 653
      }
    ]
  },
   ...
]
```

### Field definition

| Field                  | Description                             | Type/Value                                                   |
|------------------------|-----------------------------------------|--------------------------------------------------------------|
| field_image_id         | Image ID                                | int (fk), linked to images endpoint                          |
| pub_type_id            | Publication type ID                     | int (fk), linked to publication type endpoint                |
