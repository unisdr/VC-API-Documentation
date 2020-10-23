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

### Important

* Publication type (pub_type_id) 1,4,5,6 include to PreventionWeb domain.

### References

* Destination pages [URL]
* Content type mapping [URL]

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/publications

```shell
GET /sso-unisdr/api/drupal/migration/publications
```

### JSON Response

```shell
[
   {
      "ent_id":547,
      "field_image_id": "547",
      "current_url":[],
      "field_title":"Gender perspective: working together for disaster risk reduction",
      "ent_dateadded":"2007-09-03 16:08:26",
      "ent_datemodified":"2019-10-16 14:35:49",
      "field_user_comments":"[SWH] updated style and added attachment 10 Dec 07",
      "field_editors_comments":"",
      "field_body":"<p><em>Good practices and lessons learned<\/em>:<br \/><br \/>\n<br \/><br \/>\nThis publication is part of ongoing efforts facilitated by the UNISDR secretariat to build a global partnership for mainstreaming gender issues into the disaster risk reduction process. Such efforts have become urgent because disaster risk reduction has long remained a largely male dominated affair, yet it is clear that the full and balanced participation of women and men, and girls and boys make disaster risk reduction more effective. The present good practices have been compiled to draw the attention of practitioners, policy\/decision makers and stakeholders, be they men or women, to the fact that gender-inclusive disaster risk reduction is feasible immediately, even in rural community settings where gender insensitivity is generally pervasive. This publication presents a collection of 15 practices that advance gendered resilience building--a key principle that informs the implementation of the Hyogo Framework for Action.<\/p>",
      "field_authors":"",
      "author_name":"Leoj Ito",
      "field_isbn":"",
      "field_title_original":"",
      "field_number_page":"54 p.",
      "field_year_of_publication":2007,
      "pub_type_id":"5",
      "domain":"www_undrr_org",
      "field_country":[
         {
            "ctry_id":24,
            "ctry_iso3_code":"BRA"
         },
         {
            "ctry_id":76,
            "ctry_iso3_code":"HND"
         },
         {
            "ctry_id":79,
            "ctry_iso3_code":"IND"
         },
         {
            "ctry_id":80,
            "ctry_iso3_code":"IDN"
         },
         {
            "ctry_id":86,
            "ctry_iso3_code":"JAM"
         },
         {
            "ctry_id":112,
            "ctry_iso3_code":"MEX"
         },
         {
            "ctry_id":129,
            "ctry_iso3_code":"PAK"
         },
         {
            "ctry_id":134,
            "ctry_iso3_code":"PER"
         },
         {
            "ctry_id":135,
            "ctry_iso3_code":"PHL"
         },
         {
            "ctry_id":162,
            "ctry_iso3_code":"LKA"
         },
         {
            "ctry_id":177,
            "ctry_iso3_code":"TUR"
         }
      ],
      "field_organization":[
         {
            "org_id":1171
         }
      ],
      "field_region":[

      ],
      "field_hazards":[

      ],
      "field_themes":[
         {
            "scat_id":38
         },
         {
            "scat_id":762
         }
      ],
      "field_related_links":[

      ],
      "field_links":[
         {
	    "id":1212,
            "label":"View full document",
            "url":"https:\/\/www.preventionweb.net\/files\/547_gendergoodpractices.pdf",
	    "lng_id":1
         }
      ],
      "field_open_tags":[

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
