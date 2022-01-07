# Content Type / Content / Rosources

## Images

See documentation for more details https://github.com/unisdr/VC-API-Documentation/blob/master/unwomen.md#images


## Publications

This method will retrieve all documents and publications records tagged Europe region or country under Europe.

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token https://github.com/unisdr/VC-API-Documentation/blob/master/indico.md#authentication.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* page integer (optional), page number
* per_page integer (optional), number of records per page (200 is the default and maximum value)

### URL: /sso-unisdr/api/integration/pw/publications-europe

### JSON Response

```shell
{
	"current_page": 1,
	"data": [
		{
			"nid": 65768,
			"type": "publication",
			"title": "Water security for climate resilience report: A synthesis of research from the Oxford University REACH programme",
			"langcode": "en",
			"changed": 1628089074,
			"created": 1628081067,
			"published_at": 1628089074,
			"array_organization_id": [
				"1784",
				"6723",
				"7990"
			],
			"array_organization_name": [
				"Oxford University",
				"REACH",
				"UK Aid"
			],
			"array_themes": [
				"311",
				"340"
			],
			"array_themes_name": [
				"Climate Change",
				"Water"
			],
			"array_hazards": [],
			"array_hazards_name": [],
			"array_countries_regions": [
				"74",
				"78"
			],
			"array_countries_regions_name": [
				"Afghanistan",
				"Andorra"
			],
			"url": "https:\/\/www.preventionweb.net\/publication\/water-security-climate-resilience-report-synthesis-research-oxford-university-reach",
			"image_id": null,
			"field_title_original": null,
			"field_publication_type": "Documents and publications",
			"field_year_of_publication": 2021,
			"ent_id": 79277,
			"body_trimmed": "This report presents a synthesis of published and ongoing research by REACH which explores the relationship between water security, climate and climate adaptation decisions, drawing on findings from REACH research conducted in Sub-Saharan Africa and South Asia.&nbsp;Globally, water institutions are working ..."
		},
    		...
	],
	"first_page_url": "http:\/\/[SERVER]\/api\/integration\/pw\/publications-europe?page=1",
	"from": 1,
	"last_page": 13,
	"last_page_url": "http:\/\/[SERVER]\/api\/integration\/pw\/publications-europe?page=13",
	"next_page_url": "http:\/\/[SERVER]\/api\/integration\/pw\/publications-europe?page=2",
	"path": "http:\/\/[SERVER]\/api\/integration\/pw\/publications-europe",
	"per_page": 200,
	"prev_page_url": null,
	"to": 200,
	"total": 2411,
	"status": 200,
	"success": 1
}
```

| Field        	| Description                                                                      	| Type/Value       	|
|--------------	|----------------------------------------------------------------------------------	|------------------	|
| nid          	| ID, primary key                                                                     	| int           	|
| title        	| Title of the publication                                                         	| text             	|
| langcode     	| 2 characters language code                                                       	|                  	|
| changed      	| Unix timestamp                                                                   	| int              	|
| created      	| Unix timestamp                                                                   	|                  	|
| published_at 	| Unix timestamp                                                                   	|                  	|
| image_id     	| Reference to image source http://www.preventionweb.net/media/[image_id]/download 	| int              	|
| ent_id       	| Reference to legacy old ID                                                       	| int              	|

# Taxonomy

## PreventionWeb Countries and Regions

See documentation for more details https://github.com/unisdr/VC-API-Documentation/blob/master/arise-v2.md#preventionweb-countries-and-regions



## PreventionWeb Countries

See documentation for more details https://github.com/unisdr/VC-API-Documentation/blob/master/arise-v2.md#preventionweb-countries




## PreventionWeb Regions

See documentation for more details https://github.com/unisdr/VC-API-Documentation/blob/master/arise-v2.md#url-sso-unisdrapiintegrationtaxonomyregion



## PreventionWeb Themes

See documentation for more details https://github.com/unisdr/VC-API-Documentation/blob/master/arise-v2.md#preventionweb-themes


## PreventionWeb Hazards

See documentation for more details https://github.com/unisdr/VC-API-Documentation/blob/master/arise-v2.md#preventionweb-hazards

