# Content Type / Content / Rosources

## Publications: Documents & Publications

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* page integer (optional), page number
* per_page integer (optional), number of records per page (200 is the default and maximum value)

### URL: /sso-unisdr/api/integration/pw/publications-docs-theme-infra

The result is filtered by the following PW theme:
* Critical Infrastructure (313)
* Urban risk and planning (339)
* Social impacts and resilience (336)
* Structural safety (338)
* Education & School Safety (318)
* Health & Health Facilities (325)
* Early Warning (316)
* Risk Identification & Assessment (333)
* Small Island Developing States (335)
* Systemic Risk (1013)
* Recovery (332)

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
			"sub_type": "Documents and publications",
			"field_year_of_publication": 2023,
			"summary": "This publication documents how European banks charge higher interest rates on loans granted to firms in areas at high risk of flooding. ",
			"body": "<p class=\"MsoNormal\">El documento presenta una serie de recomendaciones para promover una recuperación y reconstrucción turística resiliente e inclusiva en los municipios más afectados del estado de Guerrero tras el huracán Otis. Se destaca la gestión integral del riesgo de desastres como el enfoque marco que permite considerar los procesos de recuperación de manera holística, buscando evitar, disminuir o transferir los efectos adversos de las amenazas mediante actividades de prevención, mitigación y preparación. Estas pautas adoptan un enfoque integral, incorporando principios de sostenibilidad, igualdad de género, protección, transparencia, accesibilidad e interculturalidad. Se enfatiza la importancia de atender a las poblaciones en situación de vulnerabilidad, impulsar la resiliencia comunitaria y promover la igualdad.&nbsp;<\/p><p class=\"MsoNormal\">El documento identifica impactos diferenciados entre mujeres y hombres, niñas, niños y adolescentes, buscando que las acciones emprendidas no exacerben vulnerabilidades existentes ni generen nuevas. Se proponen recomendaciones específicas para fomentar una participación comunitaria inclusiva, garantizar accesibilidad, atender necesidades de protección, fortalecer alianzas, capacitar en temas de inclusión, impulsar emprendimientos responsables, planificar un turismo sostenible, diseñar espacios públicos seguros, prevenir la violencia y promover transparencia y rendición de cuentas en el proceso de recuperación post-desastre. Todo ello enmarcado en la gestión integral del riesgo como elemento clave para un desarrollo sostenible y resiliente.<\/p>"
		},
    ...
  ],
  "first_page_url": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/publications-docs-theme-infra?page=1",
  "from": 1,
  "last_page": 1,
  "last_page_url": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/publications-docs-theme-infra?page=1",
  "next_page_url": null,
  "path": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/publications-docs-theme-infra",
  "per_page": 200,
  "prev_page_url": null,
  "to": 113,
  "total": 113,
  "status": 200,
  "success": 1
}
```

| Field        	| Description                                                                      	 	 	| Type/Value       	|
|--------------	|----------------------------------------------------------------------------------	 	 	|------------------	|
| nid          	| ID, primary key                                                                     	 	 	| int           	|
| title        	| Title of the publication                                                         	 	 	| text             	|
| langcode     	| 2 characters language code                                                       	 	 	|                  	|
| changed      	| Unix timestamp                                                                   	 	 	| int              	|
| created      	| Unix timestamp                                                                   	 	 	| int              	|
| published_at 	| Unix timestamp                                                                   	 	 	| int              	|
| image_id     	| Reference to image source http://www.preventionweb.net/media/[image_id]/download?startDownload=true 	| int              	|
| field_year_of_publication | Year of publication                                                                      	| int              	|
| type     	|                                                                                                	| text              	|
| sub_type     	|                                                                                                	| text              	|
| summary     	|                                                                                                	| text              	|



## News: Research Brief

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* page integer (optional), page number
* per_page integer (optional), number of records per page (200 is the default and maximum value)

### URL: /sso-unisdr/api/integration/pw/news-reseach-theme-infra

The result is filtered by the following PW theme:
* Critical Infrastructure (313)
* Urban risk and planning (339)
* Social impacts and resilience (336)
* Structural safety (338)
* Education & School Safety (318)
* Health & Health Facilities (325)
* Early Warning (316)
* Risk Identification & Assessment (333)
* Small Island Developing States (335)
* Systemic Risk (1013)
* Recovery (332)

### JSON Response

```shell
{
  "current_page": 1,
  "data": [
		{
			"nid": 81611,
			"type": "news",
			"title": "Wildfire, drought cause $11.2 billion in damage to private timberland in three Pacific states, study finds",
			"langcode": "en",
			"changed": 1699980535,
			"created": 1699875484,
			"published_at": 1699876982,
			"array_organization_id": [
				"81608"
			],
			"array_organization_name": [
				"Journal of Environmental Economics and Management"
			],
			"array_themes": [
				"317",
				"331",
				"333"
			],
			"array_hazards": [
				"344",
				"357"
			],
			"array_countries_regions": [
				"289"
			],
			"url": "https:\/\/www.preventionweb.net\/news\/wildfire-drought-cause-112-billion-damage-private-timberland-three-pacific-states-study-finds",
			"image_id": null,
			"field_release_date": "2023-11-12",
			"sub_type": "Research briefs",
			"summary": "Wildfires and drought have led to $11.2 billion in damages to privately held timberland in California, Oregon and Washington over the past two decades, a new Oregon State University study found."
		},
    ...
  ],
  "first_page_url": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/news-reseach-theme-infra?page=1",
  "from": 1,
  "last_page": 1,
  "last_page_url": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/news-reseach-theme-infra?page=1",
  "next_page_url": null,
  "path": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/news-reseach-theme-infra",
  "per_page": 200,
  "prev_page_url": null,
  "to": 113,
  "total": 113,
  "status": 200,
  "success": 1
}
```

| Field        	| Description                                                                      	 	 	| Type/Value       	|
|--------------	|----------------------------------------------------------------------------------	 	 	|------------------	|
| nid          	| ID, primary key                                                                     	 	 	| int           	|
| title        	| Title of the publication                                                         	 	 	| text             	|
| langcode     	| 2 characters language code                                                       	 	 	|                  	|
| changed      	| Unix timestamp                                                                   	 	 	| int              	|
| created      	| Unix timestamp                                                                   	 	 	| int              	|
| published_at 	| Unix timestamp                                                                   	 	 	| int              	|
| image_id     	| Reference to image source http://www.preventionweb.net/media/[image_id]/download?startDownload=true 	| int              	|
| field_release_date |                                                                                                	| date              	|
| type     	|                                                                                                	| text              	|
| sub_type     	|                                                                                                	| text              	|
| summary     	|                                                                                                	| text              	|




## DRR Community Voices

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* page integer (optional), page number
* per_page integer (optional), number of records per page (200 is the default and maximum value)

### URL: /sso-unisdr/api/integration/pw/blog-theme-infra

The result is filtered by the following PW theme:
* Critical Infrastructure (313)
* Urban risk and planning (339)
* Social impacts and resilience (336)
* Structural safety (338)
* Education & School Safety (318)
* Health & Health Facilities (325)
* Early Warning (316)
* Risk Identification & Assessment (333)
* Small Island Developing States (335)
* Systemic Risk (1013)
* Recovery (332)

### JSON Response

```shell
{
  "current_page": 1,
  "data": [
		{
			"nid": 74650,
			"type": "blog",
			"title": "Acting early before disasters hit: how business help scale up anticipatory action",
			"langcode": "en",
			"changed": 1665589993,
			"created": 1665587001,
			"published_at": 1665587413,
			"array_themes": [
				"331"
			],
			"array_hazards": [],
			"array_countries_regions": [],
			"url": "https:\/\/www.preventionweb.net\/blog\/acting-early-disasters-hit-how-business-help-scale-anticipatory-action",
			"image_id": 49079,
			"field_publication_date": "2022-10-11",
			"sub_type": "Blog",
			"summary": "To ensure access to early action for all, more needs to be done to scale up the approach, in particular by involving the private sector. "
		},
    ...
  ],
  "first_page_url": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/blog-theme-infra?page=1",
  "from": 1,
  "last_page": 1,
  "last_page_url": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/blog-theme-infra?page=1",
  "next_page_url": null,
  "path": "https:\/\/program.unisdr.org\/sso-unisdr\/api\/integration\/pw\/blog-theme-infra",
  "per_page": 200,
  "prev_page_url": null,
  "to": 113,
  "total": 113,
  "status": 200,
  "success": 1
}
```

| Field        	| Description                                                                      	 	 	| Type/Value       	|
|--------------	|----------------------------------------------------------------------------------	 	 	|------------------	|
| nid          	| ID, primary key                                                                     	 	 	| int           	|
| title        	| Title of the publication                                                         	 	 	| text             	|
| langcode     	| 2 characters language code                                                       	 	 	|                  	|
| changed      	| Unix timestamp                                                                   	 	 	| int              	|
| created      	| Unix timestamp                                                                   	 	 	| int              	|
| published_at 	| Unix timestamp                                                                   	 	 	| int              	|
| image_id     	| Reference to image source http://www.preventionweb.net/media/[image_id]/download?startDownload=true 	| int              	|
| field_release_date |                                                                                                	| date              	|
| type     	|                                                                                                	| text              	|
| sub_type     	|                                                                                                	| text              	|
| summary     	|                                                                                                	| text              	|


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
