# Content Type / Content / Rosources

## Images

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* ids string (required), image_id comma separated e.g. ?ids=72681,72558
* items_per_page integer (optional), items per page, allowed value [5, 10, 50] (10 is the default value)
* page integer (optional), page number (0 is the default value)

### URL: /sso-unisdr/api/integration/pw/images?ids=xxx

* /sso-unisdr/api/integration/pw/images?ids=72681,72558
* /sso-unisdr/api/integration/pw/images?page=1&ids=72681
* /sso-unisdr/api/integration/pw/images?page=1&items_per_page=5&ids=72681,72558

### JSON Response

```shell
{
  "results": [
    {
      "field_image_id": "73824",
      "nid": "66789",
      "credit": "",
      "caption": "",
      "url": "http:\/\/www.preventionweb.net\/media\/73824\/download",
      "url_portait": "http:\/\/www.preventionweb.net\/sites\/default\/files\/styles\/por\/public\/2021-09\/WorldRiskReport%202021.png?h=d230a86e&amp;itok=cRlBDIaw"
    },
    {
      "field_image_id": "73822",
      "nid": "66783",
      "credit": "",
      "caption": "",
      "url": "http:\/\/www.preventionweb.net\/media\/73822\/download",
      "url_portait": "http:\/\/www.preventionweb.net\/sites\/default\/files\/styles\/por\/public\/2021-09\/Disaster%20risk%20reduction%20through%20digital%20transformation%20in%20the%20western%20hemisphere.png?h=d230a86e&amp;itok=8MNa8P5f"
    },
    ...
  ],
  "pager": {
    "count": 3,
    "pages": 0,
    "items_per_page": "10",
    "current_page": 0,
    "next_page": 0
  }
}
```

## Collection

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* page integer (optional), page number
* per_page integer (optional), number of records per page (200 is the default and maximum value)
* type string (optional), allowed value [news, publication, blog]


### URL: /sso-unisdr/api/integration/pw/collection/unwomen/{collection_node_id}

* /sso-unisdr/api/integration/pw/collection/unwomen/65663
* /sso-unisdr/api/integration/pw/collection/unwomen/65663?page=2
* /sso-unisdr/api/integration/pw/collection/unwomen/65663?type=news
* /sso-unisdr/api/integration/pw/collection/unwomen/65663?type=publication
* /sso-unisdr/api/integration/pw/collection/unwomen/65663?type=blog


### JSON Response

```shell
{
  "current_page": 1,
  "data": [
    {
      "nid": 16349,
      "type": "news",
      "title": "The case for equity to reduce disaster risk: An analysis of Bolivia",
      "langcode": "en",
      "changed": 1631269371,
      "created": 1625564667,
      "published_at": 1625571999,
      "array_organization_id": [
        "363"
      ],
      "array_organization_name": [
        "World Bank, the"
      ],
      "array_themes": [
        "317",
        "322",
        "327"
      ],
      "array_hazards": [],
      "array_countries_regions": [
        "98"
      ],
      "url": "https:\/\/www.preventionweb.net\/news\/case-equity-reduce-disaster-risk-analysis-bolivia",
      "image_id": 72216,
      "body_trimmed": "Bolivia is one of the poorest nations in Latin America. However, it has at least $14 billion per year in potential if it achieves gender equality, urban-rural parity."
    },
    ...
  ],
  "first_page_url": "\/sso-unisdr\/api\/integration\/pw\/collections\/unwomen\/65663?page=1",
  "from": 1,
  "last_page": 5,
  "last_page_url": "\/sso-unisdr\/api\/integration\/pw\/collections\/unwomen\/65663?page=5",
  "next_page_url": "\/sso-unisdr\/api\/integration\/pw\/collections\/unwomen\/65663?page=2",
  "path": "\/sso-unisdr\/api\/integration\/pw\/collections\/unwomen\/65663",
  "per_page": "100",
  "prev_page_url": null,
  "to": 100,
  "total": 464,
  "status": 200,
  "success": 1
}
```


# Taxonomy

## PreventionWeb Countries and Regions

### URL: /sso-unisdr/api/integration/taxonomy/country_region

### JSON Response
```shell
[
  {
    "uuid": "a19ec975-0a4c-4cad-add6-2e7951678eaf",
    "tid": 69,
    "name": "Africa",
    "parent_target_id": 0
  },
  {
    "uuid": "93a2aea0-9ebc-4b60-852f-aa317dc524eb",
    "tid": 76,
    "name": "Algeria",
    "parent_target_id": 69
  },
  ...
]
```

## PreventionWeb Countries

### URL: /sso-unisdr/api/integration/taxonomy/country

### JSON Response
```shell
[
  {
    "uuid": "fce824db-999d-43a8-814d-179ad6e49269",
    "tid": 74,
    "name": "Afghanistan",
    "iso_code3": "AFG",
    "un_code": "004",
    "ctry_id": 1,
    "parent_target_id": 71
  },
  {
    "uuid": "a1f2f07c-1c04-42be-a9c6-295ccbb1a7bf",
    "tid": 75,
    "name": "Albania",
    "iso_code3": "ALB",
    "un_code": "008",
    "ctry_id": 2,
    "parent_target_id": 72
  },
  ...
]
```

## PreventionWeb Regions

### URL: /sso-unisdr/api/integration/taxonomy/region

### JSON Response

```shell
[
  {
    "uuid": "a19ec975-0a4c-4cad-add6-2e7951678eaf",
    "tid": 69,
    "name": "Africa",
    "cont_id": 1
  },
  {
    "uuid": "c6daccaa-1329-47d8-93bc-d22f0fad8a04",
    "tid": 70,
    "name": "Americas",
    "cont_id": 2
  },
  ...
]
```


## PreventionWeb Themes

### URL: /sso-unisdr/api/integration/taxonomy/theme

### JSON Response

```shell
[
  {
    "uuid": "23289da9-3674-4aa4-b17b-0d162c52931c",
    "tid": 307,
    "scat_id": 41,
    "name": "Advocacy & Media"
  },
  {
    "uuid": "c4cd9635-ab1f-46e4-99f8-15c3f8ce26dd",
    "tid": 308,
    "scat_id": 31,
    "name": "Capacity Development"
  },
  ...
]
```

## PreventionWeb Hazards

### URL: /sso-unisdr/api/integration/taxonomy/hazard

### JSON Response

```shell
[
  {
    "uuid": "14dbbe26-ab0f-4fab-bd05-dfcbcced0a7b",
    "tid": 341,
    "scat_id": 67,
    "name": "Avalanche"
  },
  {
    "uuid": "9512e517-01d7-49da-b408-e29199a96eac",
    "tid": 342,
    "scat_id": 56,
    "name": "Cold Wave"
  },
  ...
]
```



