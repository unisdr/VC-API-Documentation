# Content Type / Content / Rosources

## Images

See documentation for more details https://github.com/unisdr/VC-API-Documentation/blob/master/unwomen.md#images

## News

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* page integer (optional), page number
* per_page integer (optional), number of records per page (200 is the default and maximum value)

### URL: /sso-unisdr/api/integration/arise/v2/news

### JSON Response

```shell
{
  "current_page": 1,
  "data": [
    {
      "nid": 66754,
      "type": "news",
      "title": "Long power outages after disasters aren’t inevitable – but to avoid them, utilities need to think differently",
      "langcode": "en",
      "changed": 1632753551,
      "created": 1632739071,
      "published_at": 1632753551,
      "array_organization_id": [
        "4464"
      ],
      "array_organization_name": [
        "Conversation Media Group, the"
      ],
      "array_themes": [
        "313",
        "331"
      ],
      "array_hazards": [
        "343",
        "348"
      ],
      "array_countries_regions": [
        "289"
      ],
      "url": "https:\/\/www.preventionweb.net\/news\/long-power-outages-after-disasters-arent-inevitable-avoid-them-utilities-need-think",
      "image_id": null,
      "field_release_date": "2021-09-24",
      "field_news_type_id": 751,
      "field_news_type": "Updates",
      "ent_id": null,
      "body_trimmed": "Major energy disruptions are not inevitable consequences beyond control. Rather, the rising number of large weather-related blackouts in recent years shows that utilities, regulators and government agencies aren’t planning for these events in the right way.",
      "array_authors": [
        "Seth Blumsack"
      ]
    },
    ...
  ],
  "first_page_url": "https:\/\/program.unisdr.org\/sso-unisdr-development\/api\/integration\/arise\/v2\/news?page=1",
  "from": 1,
  "last_page": 1,
  "last_page_url": "https:\/\/program.unisdr.org\/sso-unisdr-development\/api\/integration\/arise\/v2\/news?page=1",
  "next_page_url": null,
  "path": "https:\/\/program.unisdr.org\/sso-unisdr-development\/api\/integration\/arise\/v2\/news",
  "per_page": 200,
  "prev_page_url": null,
  "to": 113,
  "total": 113,
  "status": 200,
  "success": 1
}
```


## Publications

### URL: /sso-unisdr/api/integration/arise/v2/publications



## Events (Meeting and Conferences AND Training)

### URL: /sso-unisdr/api/integration/arise/v2/event_training



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

