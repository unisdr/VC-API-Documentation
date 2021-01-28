
# Taxonomy

## [PreventionWeb Regions](https://github.com/unisdr/VC-API-Documentation/blob/master/arise.md#preventionweb-regions)

## [Regions and Countries](https://github.com/unisdr/VC-API-Documentation/blob/master/arise.md#regions-and-countries)

## [Language (taxonomy)](https://github.com/unisdr/VC-API-Documentation/blob/master/arise.md#language-taxonomy)

## [Hazards (taxonomy)](https://github.com/unisdr/VC-API-Documentation/blob/master/arise.md#hazards-taxonomy)

## [Themes (taxonomy)](https://github.com/unisdr/VC-API-Documentation/blob/master/arise.md#themes-taxonomy)

## [Publication type (taxonomy)](https://github.com/unisdr/VC-API-Documentation/blob/master/drupal-api-migration.md#publication-type-taxonomy)


# Content Type

## Documents and publications

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query string parameters:

| Name           	| Description                    	| Type/Value                 	| Default 	|
|----------------	|--------------------------------	|----------------------------	|---------	|
| page           	| current page                   	| int                        	| 1       	|
| per_page       	| number of records per page     	| int, max value allowed 400 	| 200     	|
| modified_since 	| filter result by last modified 	| date, yyyy-mm-dd           	|         	|
| q              	| filter result by entry title   	| string                     	|         	|

### URL: /sso-unisdr/api/preventionweb/content-syndication/publications

```shell
GET /sso-unisdr/api/preventionweb/content-syndication/publications
GET /sso-unisdr/api/preventionweb/content-syndication/publications?page=3
GET /sso-unisdr/api/preventionweb/content-syndication/publications?per_page=300
GET /sso-unisdr/api/preventionweb/content-syndication/publications?q=climate
GET /sso-unisdr/api/preventionweb/content-syndication/publications?modified_since=2021-01-10
```

### JSON Response

```shell
{
  "current_page": 2,
  "data": [
    {
      "ent_id": 66548,
      "ent_sec_id": 8,
      "field_title": "Fire risk reduction on the margins of an urbanizing world",
      "ent_dateadded": "2019-07-10 17:49:05",
      "ent_datemodified": "2019-07-19 20:28:54",
      "field_isbn": "",
      "field_body": "<p>It is estimated more than 150,000 people die from fires or burn-related injuries every year. Over 95% of fire deaths and burn injuries are in low- and middle-income countries. Meanwhile, urban growth is said to be one of the 21st century&rsquo;s most transformative trends, posing massive sustainability challenges in terms of housing, infrastructure and basic services, amongst others.&nbsp;Low-income countries have seen a 300% increase in the overall area of built-up spaces and a 176% increase in population in the past 40 years.&nbsp;<\/p>\r\n\r\n<p>This paper&nbsp;focuses on the risks posed to residents within informal settlements and refugee camps, two spaces that are a testament to the fact that risk reflects structural patterns of oppression and marginalisation. The authors introduce these two forms of space before exploring three case studies that emphasise the importance of international, national and local factors in shaping fire risk in informal settlements in New Delhi, India; Cape Town, South Africa; and in refugee camps across Lebanon.&nbsp;<\/p>\r\n\r\n<p>Urban fires, particularly those in informal and low-income settlements, have been shown to be a significant extensive risk, created by a complex interaction of political, economic, socio-cultural, and physical or technical factors. Yet urban fires are still relatively invisible and neglected in disaster management policy and practice.&nbsp;This neglect is due in large part to the lack of accurate, consistent and comprehensive data on fire incidence and causal factors; partly to the lack of formal fire management capabilities and resources; and partly because tackling fire in a comprehensive manner would require a political response from all levels of government, led by community needs and interests. Both communities and fire services must play integral roles in mitigating fire risk.&nbsp;<\/p>\r\n\r\n<p><em>This paper is a contribution to the 2019 edition of the Global Assessment Report on Disaster Risk Reduction (GAR 2019).<\/em><\/p>\r\n\r\n<h3>To cite this paper:&nbsp;<\/h3>\r\n\r\n<p>Rush, D. et al. Fire risk reduction on the margins of an urbanizing world. Contributing Paper to GAR 2019<\/p>",
      "field_year_of_publication": 2019,
      "field_authors": "Rush, David et al.",
      "field_title_original": "",
      "field_number_page": "25 p.",
      "pub_type_id": "6",
      "field_image_id": "66548",
      "current_url": [
        {
          "id": "8665481",
          "ent_id": 66548,
          "url": "https:\/\/www.preventionweb.net\/preventionwebs\/view\/66548"
        }
      ],
      "field_country": [
        {
          "ctry_id": 79,
          "ctry_iso3_code": "IND"
        },
        {
          "ctry_id": 96,
          "ctry_iso3_code": "LBN"
        },
        {
          "ctry_id": 160,
          "ctry_iso3_code": "ZAF"
        }
      ],
      "field_organization": [
        {
          "org_id": 1171,
          "org_title_long": "United Nations Office for Disaster Risk Reduction",
          "org_title_acronym": "UNDRR"
        }
      ],
      "field_region": [],
      "field_hazards": [
        {
          "scat_id": 73
        }
      ],
      "field_themes": [
        {
          "scat_id": 44
        },
        {
          "scat_id": 47
        },
        {
          "scat_id": 108
        },
        {
          "scat_id": 662
        }
      ],
      "field_related_links": [
        {
          "id": 70336,
          "label": "Risk perception and knowledge in fire risk reduction in a Dong minority rural village in China: A health-EDRM education intervention study",
          "url": "https:\/\/www.preventionweb.net\/go\/61499"
        },
        {
          "id": 70337,
          "label": "A framework for fire safety in informal settlements",
          "url": "https:\/\/www.preventionweb.net\/go\/61190"
        },
        {
          "id": 70338,
          "label": "The science of firescapes: Achieving fire-resilient communities",
          "url": "https:\/\/www.preventionweb.net\/go\/48804"
        },
        {
          "id": 70339,
          "label": "Climate change will increase fire risk",
          "url": "https:\/\/www.preventionweb.net\/go\/53961"
        },
        {
          "id": 71288,
          "label": "Urban fire risk control: House design, upgrading and replanning",
          "url": "http:\/\/www.preventionweb.net\/go\/63241"
        },
        {
          "id": 71289,
          "label": "More about informal settlements",
          "url": "https:\/\/www.preventionweb.net\/collections\/informal-settlements"
        }
      ],
      "field_links": [
        {
          "id": 92933,
          "label": "View document",
          "lng_id": 1,
          "url": "https:\/\/www.preventionweb.net\/files\/66548_f421finaldavidrushfireriskreduction.pdf"
        },
        {
          "id": 92936,
          "label": "Global assessment report on disaster risk reduction 2019",
          "lng_id": 1,
          "url": "https:\/\/gar.unisdr.org"
        }
      ]
    }, ...
  ],
  "first_page_url": "https:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/publications?page=1",
  "from": 201,
  "last_page": 59,
  "last_page_url": "https:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/publications?page=59",
  "next_page_url": "https:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/publications?page=3",
  "path": "http:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/publications",
  "per_page": 200,
  "prev_page_url": "https:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/publications?page=1",
  "to": 400,
  "total": 11769,
  "status": 200,
  "success": 1
}
```

## News

### [Authentication:](#authentication)

### [Header Parameters:](#header-parameters)

### [Query string parameters:](#query-string-parameters)

### URL: /sso-unisdr/api/preventionweb/content-syndication/news

```shell
GET /sso-unisdr/api/preventionweb/content-syndication/news
GET /sso-unisdr/api/preventionweb/content-syndication/news?page=3
GET /sso-unisdr/api/preventionweb/content-syndication/news?per_page=300
GET /sso-unisdr/api/preventionweb/content-syndication/news?q=climate
GET /sso-unisdr/api/preventionweb/content-syndication/news?modified_since=2021-01-10
```


### JSON Response

```shell
"current_page": 2,
  "data": [
    {
      "ent_id": 67364,
      "ent_sec_id": 2,
      "field_title": "USA: How to better explain hurricane threats? Barry showed 'good' and 'bad' of storm risk assessment",
      "field_short_title": "USA: Communicating storm risk to the public",
      "ent_dateadded": "2019-08-27 12:23:43",
      "ent_datemodified": "2019-08-27 17:19:38",
      "field_release_date": "2019-08-25",
      "field_body": "<p><em>By Mark Schleifstein<\/em><\/p>\r\n\r\n<p>[...]<\/p>\r\n\r\n<p>[Hurricane] Barry presented a textbook example, [meteorologist Frank]&nbsp;Marks said, of the improvements made in hurricane forecasting over the past 20 years. Predicting where the eye of a storm will go and when it will arrive has improved dramatically. Forecasts of intensity have not improved nearly as much.<\/p>\r\n\r\n<p style=\"margin-left:auto;\">The improved accuracy, meanwhile, comes with a new problem: The public &mdash; and sometimes local emergency officials &mdash; often don&rsquo;t understand&nbsp;where a storm&rsquo;s worst effects will occur, how widespread the effects will be, or how long a storm will remain dangerous after its eye has moved inland, Marks said.<\/p>\r\n\r\n<p style=\"margin-left:auto;\">[...]<\/p>\r\n\r\n<p style=\"margin-left:auto;\">&ldquo;I think Barry kind of showed the good and the bad,&rdquo; Marks said in a recent telephone interview. &ldquo;With that system, the models were actually picking it up almost a week ahead of time and saying there was going to be something dropping out of Georgia into the Gulf that would become pretty consequential, a hurricane. That was pretty amazing.&rdquo;<\/p>\r\n\r\n<p style=\"margin-left:auto;\">The bad, Marks said, was the difficulty in getting people to understand how Barry&rsquo;s slow intensification made it hard to say when and where the worst rainfall would take place. Other challenges: The storm&rsquo;s potential to intensify and organize&nbsp;led to a scary storm surge forecast for an unprecedentedly high Mississippi River in New Orleans, and its failure to spin up then caused that threat to disappear.<\/p>\r\n\r\n<div>\r\n<p>[...]<\/p>\r\n<\/div>\r\n\r\n<p style=\"margin-left:auto;\">Marks is most interested in a new effort to improve the way forecasters use social and behavioral science to communicate risk to the public.&nbsp;<\/p>\r\n\r\n<p style=\"margin-left:auto;\">[...]<\/p>",
      "nws_summary": "Storm forecasts have improved significantly in accuracy, but communicating the complex nature of risk to the public and emergency managers is still a challenge.",
      "ent_lang_id": 1,
      "field_image_id": "",
      "current_url": [
        {
          "id": "2673641",
          "ent_id": 67364,
          "url": "https:\/\/www.preventionweb.net\/publications\/view\/67364"
        }
      ],
      "field_country": [
        {
          "ctry_id": 185,
          "ctry_iso3_code": "USA"
        }
      ],
      "field_organization": [
        {
          "org_id": 7512,
          "org_title_long": "Times-Picayune, the - New Orleans Net, LLC",
          "org_title_acronym": "NOLA.com"
        }
      ],
      "field_region": [
        {
          "cont_id": 1
        }
      ],
      "field_hazards": [
        {
          "scat_id": 58
        }
      ],
      "field_themes": [
        {
          "scat_id": 35
        },
        {
          "scat_id": 40
        },
        {
          "scat_id": 41
        },
        {
          "scat_id": 44
        }
      ],
      "field_related_links": [
       {
          "id": 70336,
          "label": "Risk perception and knowledge in fire risk reduction in a Dong minority rural village in China: A health-EDRM education intervention study",
          "url": "https:\/\/www.preventionweb.net\/go\/61499"
        }
      ],
      "field_links": [
        {
          "id": 92933,
          "label": "View document",
          "lng_id": 1,
          "url": "https:\/\/www.preventionweb.net\/files\/66548_f421finaldavidrushfireriskreduction.pdf"
        }
      ]
    }, ...
  ],
  "first_page_url": "https:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/news?page=1",
  "from": 201,
  "last_page": 59,
  "last_page_url": "https:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/news?page=59",
  "next_page_url": "https:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/news?page=3",
  "path": "http:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/news",
  "per_page": 200,
  "prev_page_url": "https:\/\/[DOMAIN/PATH]\/api\/preventionweb\/content-syndication\/news?page=1",
  "to": 400,
  "total": 11769,
  "status": 200,
  "success": 1
}
```

# Content Promotion

## Collection

### [Authentication:](#authentication)

### [Header Parameters:](#header-parameters)

### [Query string parameters:](#query-string-parameters)

### URL: /sso-unisdr/api/preventionweb/content-syndication/collections/{COLLECTION URL NAME}
```shell
GET /sso-unisdr/api/preventionweb/content-syndication/collections/cop23
```

### JSON Response

```shell
```



# [Authentication](https://github.com/unisdr/VC-API-Documentation#step-1-request-access-token)

# Service Discovery

Shows allowed endpoints.

### [Authentication:](#authentication)

### [Header Parameters:](#header-parameters)

### URL: /sso-unisdr/api/services/discovery

