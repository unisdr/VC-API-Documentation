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
	"first_page_url": "http:\/\/localhost:8000\/api\/integration\/pw\/publications-europe?page=1",
	"from": 1,
	"last_page": 13,
	"last_page_url": "http:\/\/localhost:8000\/api\/integration\/pw\/publications-europe?page=13",
	"next_page_url": "http:\/\/localhost:8000\/api\/integration\/pw\/publications-europe?page=2",
	"path": "http:\/\/localhost:8000\/api\/integration\/pw\/publications-europe",
	"per_page": 200,
	"prev_page_url": null,
	"to": 200,
	"total": 2411,
	"status": 200,
	"success": 1
}
```
