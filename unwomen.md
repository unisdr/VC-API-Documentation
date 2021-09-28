# Content Type

CONDITION: Pre-filtered by content publication date >= 2020 and theme = private sector


## Documents and publications

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### URL: /sso-unisdr/api/integration/pw/collections/unwomen/{collection_node_id}

### JSON Response

```shell
[
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



