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
