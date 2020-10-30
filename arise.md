OpenAPI version 3 documentation is work in progress https://github.com/unisdr/VC-API-Documentation/blob/master/arise.json.

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



## News

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/arise/integration/news

```shell
GET /sso-unisdr/api/arise/integration/news
```

### JSON Response

```shell
[
 {
    "ent_id": 43133,
    "ent_sec_id": 2,
    "field_title": "As ministerial forum opens at Sendai Conference, focus turns to reconstruction after disasters, increased international cooperation in post-2015 framework",
    "ent_dateadded": "2015-03-15 12:09:50",
    "ent_datemodified": "2015-03-16 08:11:11",
    "field_body_trimmed": "In speaking of both cooperation and building back better, participants stressed the need for a forward-looking perspective to build now the kind of resiliency that would be needed in the future, particularly given the knowledge of the increased severity of certain crises due to climate change and other ...",
    "field_release_date": "2015-03-15",
    "ent_lang_id": 1,
    "current_url": [
      {
        "id": "2431331",
        "ent_id": 43133,
        "url": "https:\/\/www.preventionweb.net\/news\/view\/43133"
      }
    ],
    "field_country": [
      {
        "ctry_id": 87,
        "ctry_iso3_code": "JPN"
      }
    ],
    "field_organization": [
      {
        "org_id": 6289,
        "org_title_long": "United Nations Department of Public Information",
        "org_title_acronym": "UN-DPI"
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
| field_release_date     | News release date                       | date (yyyy-mm-dd)                                            |




## Events (Meeting and Conferences AND Training)

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/arise/integration/event_training

```shell
GET /sso-unisdr/api/arise/integration/event_training
```

### JSON Response

```shell
[
  {
    "ent_id": 41789,
    "ent_sec_id": 5,
    "field_title": "Disaster Risk management Public Seminar Series No.5 :The role of the private sector in building resilience to disasters",
    "ent_dateadded": "2015-01-08 11:20:41",
    "ent_datemodified": "2015-01-08 16:44:34",
    "ent_datepublished": "2015-01-08 16:44:34",
    "field_body_trimmed": "In many years, Japan and the World Bank have been working together to support Disaster Risk Management (DRM) efforts by disaster-prone developing countries. In April 2013, the Government of Japan announced Japan-World Bank Program for Mainstreaming DRM in Developing Countries. Subsequently, World Bank ...",
    "field_start_date": "2015-01-13",
    "field_end_date": "2015-01-13",
    "ent_lang_id": 1,
    "trn_type_id": 1,
    "trn_type": "Event",
    "current_url": [
      {
        "id": "5417891",
        "ent_id": 41789,
        "url": "https:\/\/www.preventionweb.net\/events\/view\/41789"
      }
    ],
    "field_country": [
      {
        "ctry_id": 87,
        "ctry_iso3_code": "JPN"
      }
    ],
    "field_organization": [
      {
        "org_id": 125,
        "org_title_long": "World Bank, the",
        "org_title_acronym": "WB"
      },
      {
        "org_id": 16644,
        "org_title_long": "Japan Bosai Platform",
        "org_title_acronym": ""
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
| field_start_date       | Start date of the event                 | date (yyyy-mm-dd)                                            |
| field_end_date         | Start date of the event                 | date (yyyy-mm-dd)                                            |
| trn_type_id            | Event type ID                           | integer; 1 = Event (Meeting & conferences), 3 = Training     |






## Events (Meeting and Conferences AND Training)

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query string parameter:

* ids string, value [123 OR 123,456] field_image_id of the content (optional)

### URL: /sso-unisdr/api/arise/integration/images

```shell
GET /sso-unisdr/api/arise/integration/images
GET /sso-unisdr/api/arise/integration/images?ids=123
GET /sso-unisdr/api/arise/integration/images?ids=123,456
```

### JSON Response

```shell
[
  "0": {
    "field_image_id": 62970,
    "ent_id": 62970,
    "credit": "",
    "caption": "",
    "url": "https:\/\/www.preventionweb.net\/files\/62970_largeImage.jpg"
  },
  "1": {
    "field_image_id": 63004,
    "ent_id": 63004,
    "credit": "",
    "caption": "",
    "url": "https:\/\/www.preventionweb.net\/files\/63004_largeImage.jpg"
  },
   ...
]
```
