# Content Type / Content / Rosources

## Images

See documentation for more details https://github.com/unisdr/VC-API-Documentation/blob/master/unwomen.md#images

## Publications

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* page integer (optional), page number
* per_page integer (optional), number of records per page (200 is the default and maximum value)

### URL: /sso-unisdr/api/integration/pw/publications-theme-infra

The result is filtered by the following PW theme:
* Critical Infrastructure (313)
* Urban risk and planning (339)
* Social impacts and resilience (336)
* Structural safety (338)

### JSON Response

```shell
{
  "current_page": 1,
  "data": [
		{
			"nid": 82170,
			"type": "publication",
			"title": "Flooded credit markets: Physical climate risk and small business lending",
			"langcode": "en",
			"changed": 1702399812,
			"created": 1702388041,
			"published_at": 1702399812,
			"array_organization_id": [
				"574",
				"577"
			],
			"array_organization_name": [
				"European Commission",
				"European Commission Joint Research Centre"
			],
			"array_themes": [
				"317",
				"331"
			],
			"array_hazards": [],
			"array_countries_regions": [
				"72"
			],
			"url": "https:\/\/www.preventionweb.net\/publication\/flooded-credit-markets-physical-climate-risk-and-small-business-lending",
			"image_id": 92143,
			"field_title_original": null,
			"field_publication_type": "Documents and publications",
			"field_year_of_publication": 2023,
			"body_trimmed": "This publication documents how European banks charge higher interest rates on loans granted to firms in areas at high risk of flooding. ",
			"array_authors": [
				"Caterina Rho ",
				"Luca Barbaglia",
				"Serena Fatica"
			]
		},
    ...
  ],
  "first_page_url": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/publications-theme-infra?page=1",
  "from": 1,
  "last_page": 1,
  "last_page_url": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/publications-theme-infra?page=1",
  "next_page_url": null,
  "path": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/arise\/pw\/publications-theme-infra",
  "per_page": 200,
  "prev_page_url": null,
  "to": 113,
  "total": 113,
  "status": 200,
  "success": 1
}
```



# Taxonomy

## PreventionWeb Countries and Regions

This endpoint lists all countries and regions. Regions are record with parent_target_id = 0 while parent_target_id != 0 are countries. 

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

The field cont_id was retained to retain reference to legacy data. New record created in the new system will not have cont_id.

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

The field scat_id was retained to retain reference to legacy data. New record created in the new system will not have scat_id.

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

The field scat_id was retained to retain reference to legacy data. New record created in the new system will not have scat_id. 

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

## UNDRR Countries

### URL: /sso-unisdr/api/integration/taxonomy/undrr_country

### JSON Response
```shell
[
  {
    "uuid": "fce824db-999d-43a8-814d-179ad6e49269",
    "country": "Afghanistan",
    "iso_code3": "AFG",
    "un_code": "004",
    "array_undrr_region_id": [
      "66"
    ],
    "ctry_id": 1
  },
  {
    "uuid": "a1f2f07c-1c04-42be-a9c6-295ccbb1a7bf",
    "country": "Albania",
    "iso_code3": "ALB",
    "un_code": "008",
    "array_undrr_region_id": [
      "67"
    ],
    "ctry_id": 2
  },
  {
    "uuid": "6bd89ac8-81e9-4ddb-b0b0-68098af2ea59",
    "country": "Niue",
    "iso_code3": "NIU",
    "un_code": "570",
    "array_undrr_region_id": [
      "68",
      "66"
    ],
    "ctry_id": 194
  },
  ...
]
```

## UNDRR Regions

### URL: /sso-unisdr/api/integration/taxonomy/undrr_region

### JSON Response

```shell
[
  {
    "uuid": "323f4b97-8c24-4037-9555-f8609adcef9f",
    "tid": 63,
    "name": "Africa"
  },
  {
    "uuid": "9ef45c73-f014-4798-a513-5ce1518d8d8c",
    "tid": 64,
    "name": "Americas"
  },
  {
    "uuid": "319257a7-b8dd-455c-9110-27c531c42856",
    "tid": 65,
    "name": "Arab States"
  },
  {
    "uuid": "6f0bda11-9842-4c14-b9af-e9740e5baef5",
    "tid": 66,
    "name": "Asia and Pacific"
  },
  {
    "uuid": "bb36dc0f-abd7-4042-b4eb-45efeef4c309",
    "tid": 67,
    "name": "Europe"
  },
  {
    "uuid": "7b4254af-6e2d-4dfa-aaf5-742c099f3cd2",
    "tid": 68,
    "name": "Suva"
  }
]
```
