# Content Type / Content / Rosources


## API Base URL

https://program.unisdr.org/sso-unisdr



## Policies and Plans

This method will retrieve all policies and plans documents exposing all meta data.

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token https://github.com/unisdr/VC-API-Documentation/blob/master/indico.md#authentication.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* page integer (optional), page number
* per_page integer (optional), number of records per page (200 is the default and maximum value)

### URL: /sso-unisdr/api/integration/pw/publications-policies-plans

### JSON Response

```shell
{
	"current_page": 1,
	"data": [
		{
			"nid": 71861,
			"type": "publication",
			"title": "Italy: Climate Adaptation Strategy",
			"langcode": "en",
			"changed": 1654155290,
			"created": 1653312330,
			"published_at": 1653312810,
			"field_policy_type_target_id": 819,
			"array_organization_id": [
				"2716"
			],
			"array_organization_name": [
				"Grantham Research Institute on Climate Change and the Environment"
			],
			"array_themes": [
				"311"
			],
			"array_themes_name": [
				"Climate Change"
			],
			"array_hazards": [],
			"array_hazards_name": [],
			"array_countries_regions": [
				"170"
			],
			"array_countries_regions_name": [
				"Italy"
			],
			"url": "https:\/\/www.preventionweb.net\/publication\/italy-climate-adaptation-strategy",
			"image_id": 80415,
			"field_publication_type": "Policies and plans",
			"field_year_of_publication": 2015,
			"summary": "The Climate Adaptation Strategy establishes specific objectives to be reached by end of December 2016 and it is to be updated within 5 years. The NAS provides an extensive knowledge on past, present and future climate change.",
			"body": "<section>\r\n<p>The Climate Adaptation Strategy establishes specific objectives to be reached by end of December 2016 and it is to be updated within 5 years.&nbsp;The National Adaptation Strategy provides an extensive knowledge on past, present and future climate change and on impacts\/vulnerabilities to climate change of different sectors, including: water resources; desertification, soil degradation and drought; hydrogeological risks; biodiversity and ecosystems; health; forestry; agriculture, aquaculture, marine fishery; energy; coastal zones; tourism; urban settlements; and critical infrastructures.<\/p>\r\n\r\n<p>The Strategy also provides a national vision on how to address future impacts of climate change in various socio-economic sectors and natural systems and it in particular aims to:<\/p>\r\n<\/section>\r\n\r\n<ul>\r\n\t<li>improve current knowledge on climate change and its impacts;<\/li>\r\n\t<li>identify vulnerabilities and adaptation options for relevant natural and socio-economic systems, and describe opportunities that may be associated to climate change;<\/li>\r\n\t<li>promote participation of stakeholders in defining strategies and sectoral adaptation plans to make later implementation more effective;<\/li>\r\n\t<li>increase awareness about climate change risks and adaptation through a range of communication activities;<\/li>\r\n\t<li>specify methods to be used to identify the best options for adaptation actions, also highlighting the co-benefits.<\/li>\r\n<\/ul>\r\n\r\n<p>&nbsp;<\/p>\r\n",
			"array_attachments": [
				{
					"name": "Strategia Nazionale di Adattamento ai Cambiamenti Climatici",
					"langcode": "en",
					"target": "link",
					"url": "https:\/\/www.mite.gov.it\/sites\/default\/files\/archivio\/allegati\/clima\/documento_SNAC.pdf",
					"array_file": []
				},
				{
					"name": "National Policy on Disaster Management 2009 India",
					"langcode": "en",
					"target": "file",
					"url": "https:\/\/www.preventionweb.net\/sites\/default\/files\/2022-01\/National Policy on Disaster Management 2009 India.pdf",
					"array_file": {
						"filemime": "application\/pdf",
						"filesize": 1448747,
						"created": 1642666425,
						"changed": 1642666433
					}
				}
			],
			"array_links": [
				{
					"order": 0,
					"title": "Mitigating the impact of climate change and flooding in Italy",
					"url": "https:\/\/www.preventionweb.net\/news\/mitigating-impact-climate-change-and-flooding-italy"
				},
				{
					"order": 1,
					"title": "G20 Climate Risk Atlas: Italy",
					"url": "https:\/\/www.preventionweb.net\/publication\/g20-climate-risk-atlas-italy"
				},
				...
			]
		},
	...
	],
	"first_page_url": "http:\/\/[SERVER]\/api\/integration\/pw\/publications-policies-plans?page=1",
	"from": 1,
	"last_page": 13,
	"last_page_url": "http:\/\/[SERVER]\/api\/integration\/pw\/publications-policies-plans?page=13",
	"next_page_url": "http:\/\/[SERVER]\/api\/integration\/pw\/publications-policies-plans?page=2",
	"path": "http:\/\/[SERVER]\/api\/integration\/pw\/publications-policies-plans",
	"per_page": 200,
	"prev_page_url": null,
	"to": 200,
	"total": 2411,
	"status": 200,
	"success": 1
}


```
| Field                       	| Description                                                                      	| Type/Value  	|
|-----------------------------	|----------------------------------------------------------------------------------	|-------------	|
| nid                         	| ID, primary key                                                                  	| int         	|
| title                       	| Title of the publication                                                         	| text        	|
| langcode                    	| 2 characters language code                                                       	|             	|
| field_policy_type_target_id 	| Policy type ID                                                                   	| int         	|
| changed                     	| Unix timestamp                                                                   	| int         	|
| created                     	| Unix timestamp                                                                   	|             	|
| published_at                	| Unix timestamp                                                                   	|             	|
| image_id                    	| Reference to image source http://www.preventionweb.net/media/[image_id]/download 	| int         	|
| summary                     	| Summary of the document                                                          	| text        	|
| body                        	| Full content of the document in HTML format                                      	| text (html) 	|
| array_attachments[]         	|                                                                                  	| array       	|
| - name                      	| Label or short description                                                       	|             	|
| - langcode                  	|                                                                                  	|             	|
| - target                    	| Identifier if the attachment is a file or link.                                  	|             	|
| - url                       	|                                                                                  	|             	|
| - array_file[]               	| Empty array if the target is not equal to file                                   	| array       	|
| ** filemime                 	| Mime type of the file e.g. application/pdf                                       	| text        	|
| ** filesize                 	|                                                                                  	| int         	|
| ** created                  	| Unix timestamp                                                                   	| int         	|
| ** changed                  	| Unit timestamp                                                                   	| int         	|
| array_links[]         	|                                                                                  	| array       	|
| - order                      	| Sorting order                                                                 	| int         	|
| - title                      	| Label or short description                                                       	|             	|
| - url                      	| URL of the related link                                                            	|             	|


# Taxonomy


## PreventionWeb Policy Type


### URL: /sso-unisdr/api/integration/taxonomy/policy_type

### JSON Response

```shell
[
	{
		"uuid": "f4d46007-9d71-4a94-a6f1-292a8020e79c",
		"tid": 946,
		"name": "Intergovernmental declarations"
	},
	{
		"uuid": "18b64d8f-763b-4569-b56d-a59497f3e4b6",
		"tid": 821,
		"name": "Local policy and plans"
	},
	...
]
```

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

