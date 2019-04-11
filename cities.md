# Cities API Documentation

Client Credentials Flow OAuth2 API

## Step 1, request access token

Form Post Parameters:

* grant_type string, value should be ‘client_credentials’
* client_id  integer,  client ID given by UNISDR
* client_secret  string, secret provided by UNISDR
* scope string (optional), value should be ‘*’ or null 

```shell
POST /sso-unisdr/oauth/token
```

Response Body

```shell
[ACCESS TOKEN]
```


## Retrieve cities records.

API call have hit rate of 100 per minute. Unique api call are cached in two minutes.

Query String Parameter:

* q string (optional), perform simple search on organization name and acronym (minimum 3 and maximum 30 characters)

Header Parameters:

* Accept string, value ‘application/json’
* Authorization  string, value 'Bearer [ACCESS TOKEN received from step 1]'

```shell
GET /sso-unisdr/api/cities/get/all

GET /sso-unisdr/api/cities/get/all?q=Geneva
```

JSON Response

```shell
{  
   "status":200,
   "success":true,
   "total":2,
   "data":[  
      {  
         "cty_id":87,
         "cty_title":"Geneva",
         "cty_latitude":"46.208358",
         "cty_longitude":"6.142701",
         "cty_location":"Geneva, Switzerland",
         "cty_ctry_iso2":"CH",
         "cty_ctry_id":167,
         "cty_is_capital":0,
         "cty_ishidden":0,
         "cty_dateadded":"2011-03-04 15:58:37",
         "cty_datemodified":"2011-03-04 16:50:23",
         "ctry_id":167,
         "ctry_iso3_code":"CHE",
         "ctry_title":"Switzerland",
         "isdr_regions_id":"4",
         "isdr_regions_title":"Europe",
         "geo_region_id":3,
         "geo_region":"Europe"
      }, ....
   ]
}
```

### Retrieve specific city record.

```shell
GET /sso-unisdr/api/cities/get/id/{id}
```


### Retrieve cities of a country.

```shell
GET /sso-unisdr/api/cities/get/country/id/{id}
```


### Retrieve cities under a specific geographical region.

```shell
GET /sso-unisdr/api/cities/get/geo_region/id/{id}
```


#### Retrieve cities under a specific UNISDR region.

```shell
GET /sso-unisdr/api/cities/get/isdr_region/id/{id}
```



## Add new city

Post Parameters:

* cty_title string				(required), city name
* cty_ctry_id							(required), country id


```shell
POST /sso-unisdr/api/cities/add
```


Return in JSON format

```shell
{  
   "status":200,
   "success":true,
   "message":"Record saved.",
   "cty_id":4771
}
```

## Edit city information

Post Parameters:

* cty_title string				(required), city name
* cty_ctry_id							(required), country id
* cty_latitude numeric		(optional), null or 10.23423423
* cty_longitude numeric 	(optional), null or 11.2322343
* cty_location string			(optional)
* cty_is_capital integer	(optional), allowed values 0 or 1


```shell
POST /sso-unisdr/api/cities/edit/{id}
```

Return in JSON format

```shell
{  
   "status":200,
   "success":true,
   "message":"Record saved.",
}
```




## Retrieve PreventionWeb tagged events content


```shell
GET /sso-unisdr/api/mcr/tagged/pw_events/get/all
```


Return in JSON format

```shell
{  
   "current_page":1,
   "data":[  
      {  
         "ent_id":58039,
         "ent_title":"Capacity Development for Making Cities Resilient to Disasters: Applying the Resilience Scorecard for Cities. Ulaanbaatar, Mongolia.",
         "ent_datemodified":"2018-04-30 07:35:18",
         "trn_ismajor_event":0,
         "trn_desc":"<h3><strong>Background <\/strong><\/h3>\r\n\r\n<p>Cities are hubs of ideas, commerce, culture, science, productivity, social development and much more. At their best, cities have enabled people to advance socially and economically. Yet nowt heat hald of the world&rsquo;s population lives in cities, making sutainable and resilient cities -amidst a chaning climate, rapidly depleting resources, and unplanned urbanization &ndash; is one of the our greates challenges and opportunities.<\/p>\r\n\r\n<p>Current and future challenges of mainstreaming climate change adaptation and disaster risk reduction in development planning demand new approaches, mechanisms, sets of skills and competencies that need to be identified and strengthened in order to form the basis of increasing public demand and political commitment to local actions and budget allocations.<\/p>\r\n\r\n<p>In this regard, building resilience and adapting to climate change is crucial for cities. Efforts to build resilience in cities can benefit from integrating disaster risk reduction and climate change adaptation with existing efforts in disaster risk reduction and other similar planning processes.<\/p>\r\n\r\n<p>&nbsp;<\/p>\r\n\r\n<h3><strong>Workshop Objectives and Expected Outcomes<\/strong><\/h3>\r\n\r\n<p>Overall, the training course will provide an opportunity to:<\/p>\r\n\r\n<ul>\r\n\t<li>Learn about the Making Cities Resilient Global Campaign and how its tools, materials and approaches may be used to build local resilience to disasters.<\/li>\r\n\t<li>Capacity development of government officials of Ulaanbaatar with a focus on applying the Disaster Resilience Scorecard<\/li>\r\n<\/ul>\r\n\r\n<p><strong>Expected Outcomes <\/strong><\/p>\r\n\r\n<ul>\r\n\t<li>Draft Scorecard Assessment<\/li>\r\n<\/ul>",
         "trn_event_url":"",
         "trn_webcast_url":"",
         "trn_twitter_hashtag":"",
         "trn_photovideo_embed":"",
         "trn_video_embed":"",
         "trn_type_id":3,
         "lnk_trn_date_start":"2018-04-30",
         "lnk_trn_date_end":"2018-05-01",
         "lnk_trn_type":"1",
         "lnk_trn_isonline":"0",
         "lnk_trn_ctry_id":"115",
         "lnk_trn_city":"Ulaanbaatar",
         "lnk_trn_venue":"",
         "lnk_trn_tentative_loc":"0",
         "lnk_trn_lang_id":"0",
         "lnk_trn_lang_other":null,
         "lnk_trn_islivetranslation":"0",
         "lnk_trn_livetran_info":null,
         "type_title":"Training",
         "ent_lang_id":1,
         "lng_title":"English"
      },
      {  
         "ent_id":57885,
         "ent_title":"Consultation for MCR Campaign Tools in Korea - MCR \ucea0\ud398\uc778 \uac1c\uc815\ub0b4\uc6a9 \uad8c\uc5ed\ubcc4 \uc21c\ud68c \uc124\uba85\ud68c",
         "ent_datemodified":"2018-04-18 11:02:42",
         "trn_ismajor_event":0,
         "trn_desc":"<p>&nbsp;<\/p>\r\n\r\n<p>[ENGLISH]<\/p>\r\n\r\n<h3><strong>Background <\/strong><\/h3>\r\n\r\n<p>&nbsp;<\/p>\r\n\r\n<p>Cities are hubs of ideas, commerce, culture, science, productivity, social development and much more. At their best, cities have enabled people to advance socially and economically. Yet nowt heat hald of the world&rsquo;s population lives in cities, making sutainable and resilient cities -amidst a chaning climate, rapidly depleting resources, and unplanned urbanization &ndash; is one of the our greates challenges and opportunities.<\/p>\r\n\r\n<p>Current and future challenges of mainstreaming climate change adaptation and disaster risk reduction in development planning demand new approaches, mechanisms, sets of skills and competencies that need to be identified and strengthened in order to form the basis of increasing public demand and political commitment to local actions and budget allocations.<\/p>\r\n\r\n<p>In this regard, building resilience and adapting to climate change is crucial for cities. Efforts to build resilience in cities can benefit from integrating disaster risk reduction and climate change adaptation with existing efforts in disaster risk reduction and other similar planning processes.<\/p>\r\n\r\n<p>&nbsp;<\/p>\r\n\r\n<h3><strong>Workshop Objectives and Expected Outcomes<\/strong><\/h3>\r\n\r\n<p>&nbsp;<\/p>\r\n\r\n<p>Overall, the training course will provide an opportunity to:<\/p>\r\n\r\n<ul>\r\n\t<li>Learn about the Making Cities Resilient Global Campaign and how its tools, materials and approaches may be used to build local resilience to disasters.<\/li>\r\n\t<li>Capacity development of government officials with a focus on Handbook for Local Government Leaders,&nbsp;Disaster Resilience Scorecard and Quick Risk Estimation (QRE) tools.<\/li>\r\n<\/ul>\r\n\r\n<p>&nbsp;<\/p>\r\n\r\n<p>[KOREAN]<\/p>\r\n\r\n<h3><strong>\ubc30\uacbd<\/strong><\/h3>\r\n\r\n<p>&nbsp;<\/p>\r\n\r\n<p>UNISDR\uc5d0\uc11c \ucd94\uc9c4\ud558\ub294 MCR \ucea0\ud398\uc778 \uad00\ub828 \ub0b4\uc6a9\uc774 \uc13c\ub2e4\uc774 \uac15\ub839*\uc5d0 \ub9de\ucdb0 \uac1c\uc815\ub428\uc5d0 \ub530\ub77c \ud55c\uae00 \ubc84\uc804\uc758 \ud578\ub4dc\ubd81 \uac1c\uc815\ud310, \uc2a4\ucf54\uc5b4\uce74\ub4dc, \uc57d\uc2dd \uc704\ud5d8\ub3c4 \ud3c9\uac00 \ub3c4\uad6c\uc758 \ud65c\uc6a9\ubc95 \ubc0f \ud575\uc2ec \ub0b4\uc6a9 \uc804\ub2ec\uc744 \uc704\ud55c \uad8c\uc5ed\ubcc4 \uc21c\ud68c \uc124\uba85\ud68c \uac1c\ucd5c<\/p>\r\n\r\n<p>*\uc13c\ub2e4\uc774 \uac15\ub839 2015-2030: \ud6a8\uace0\ud589\ub3d9\uac15\ub825 2005-2015 \uc885\ub8cc\uc5d0 \ub530\ub77c \ud5a5\ud6c4 15\ub144\uac04 \uc801\uc6a9 \ub420 \uc138\uacc4 \uc7ac\ub09c\uc704\ud5d8\uacbd\uac10\uc758 \uc804\ub7b5\uc801 \uc9c0\uce68<\/p>\r\n\r\n<p>&nbsp;<\/p>\r\n\r\n<h3><strong>\uc7ac\ub09c\uc5d0 \uac15\ud55c \ub3c4\uc2dc \ub9cc\ub4e4\uae30 \ucea0\ud398\uc778 (Making Cities Resilient Campaign)<\/strong><\/h3>\r\n\r\n<p>&nbsp;<\/p>\r\n\r\n<ul>\r\n\t<li>\r\n\t<p>\uac1c\ub150: \ub3c4\uc2dc \uc2a4\uc2a4\ub85c \uae30\ud6c4\ubcc0\ud654\uc640 \uc7ac\ub09c\uc5d0 \uac15\ud55c \ub3c4\uc2dc \ub9cc\ub4e4\uae30\ub97c \ucd09\uad6c\ud558\ub294 UN\uc6b4\ub3d9<\/p>\r\n\t<\/li>\r\n\t<li>\r\n\t<p>\ub300\uc0c1\/\ud604\ud669: \uc9c0\ubc29\uc790\uce58\ub2e8\uccb4\/\uc804\uc138\uacc4 128\uac1c\uad6d 3,851\uac1c \ub3c4\uc2dc \uac00\uc785 (2018.02.27 \ud604\uc7ac)<\/p>\r\n\r\n\t<ul>\r\n\t\t<li>\r\n\t\t<p>\uad6d\ub0b4\ub294 169\uac1c \uc9c0\uc790\uccb4 \uac00\uc785, \ud65c\ub3d9\uc911<\/p>\r\n\t\t<\/li>\r\n\t<\/ul>\r\n\t<\/li>\r\n\t<li>\r\n\t<p>\ucc38\uc5ec\ubc29\ubc95: \ub3c4\uc2dc\ubcc4\ub85c \ucea0\ud398\uc778 \ucc38\uc5ec\uc5d0 \uc11c\uba85\ud558\uace0 \uc7ac\ub09c\uc704\ud5d8\uacbd\uac10\uc744 \uc704\ud55c \ud575\uc2ec\uc0ac\ud56d&nbsp;\uc2e4\ucc9c<\/p>\r\n\r\n\t<ul>\r\n\t\t<li>\r\n\t\t<p>\ud575\uc2ec\uc0ac\ud56d: \ubcf5\uc6d0\ub825\uc744 \uc704\ud55c \uc7ac\uc815\ub825 \ud655\ubcf4, \uae30\ubc18\uc2dc\uc124\uc758 \ubcf5\uc6d0\ub825 \uac15\ud654, \ub354 \ub098\uc740 \uc7ac\uac74 \ub4f1<\/p>\r\n\t\t<\/li>\r\n\t<\/ul>\r\n\t<\/li>\r\n<\/ul>\r\n\r\n<p>&nbsp;<\/p>",
         "trn_event_url":"",
         "trn_webcast_url":"",
         "trn_twitter_hashtag":"",
         "trn_photovideo_embed":"",
         "trn_video_embed":"",
         "trn_type_id":1,
         "lnk_trn_date_start":"2018-04-03,2018-04-04,2018-04-19,2018-04-20",
         "lnk_trn_date_end":"2018-04-03,2018-04-04,2018-04-19,2018-04-20",
         "lnk_trn_type":"1",
         "lnk_trn_isonline":"0",
         "lnk_trn_ctry_id":"139",
         "lnk_trn_city":"Incheon,Cheonan,Gwangju,Busan",
         "lnk_trn_venue":"GETI,",
         "lnk_trn_tentative_loc":"0",
         "lnk_trn_lang_id":"0",
         "lnk_trn_lang_other":"Korean",
         "lnk_trn_islivetranslation":"0",
         "lnk_trn_livetran_info":"",
         "type_title":"Meeting",
         "ent_lang_id":1,
         "lng_title":"English"
      },
	  ...
   ],
   "first_page_url":"\/sso-unisdr\/api\/mcr\/tagged\/pw_events\/get\/all?page=1",
   "from":1,
   "last_page":1,
   "last_page_url":"\/sso-unisdr\/api\/mcr\/tagged\/pw_events\/get\/all?page=1",
   "next_page_url":null,
   "path":"\/sso-unisdr\/api\/mcr\/tagged\/pw_events\/get\/all",
   "per_page":200,
   "prev_page_url":null,
   "to":40,
   "total":40,
   "status":200,
   "success":1
}
```

| Field                        | Description                                   | Type/Value                                                                      |
|------------------------------|-----------------------------------------------|---------------------------------------------------------------------------------|
| ent_id                       |                                               | int                                                                             |
| ent_title *                  | Title of entry                                | plain text                                                                      |
| ent_datemodified             | Date modified                                 | date (yyyy-mm-dd hh:mm:ss)                                                      |
| ent_lang_id                  | Language ID of description                    | int                                                                             |
| lng_title                    | Language of description                       | plain text                                                                      |
| trn_desc                     |                                               | plain text, multiple line, data can be in HTML format                           |
| trn_event_url                |                                               |                                                                                 |
| trn_webcast_url              |                                               |                                                                                 |
| trn_twitter_hashtag          |                                               |                                                                                 |
| trn_photovideo_embed         |                                               |                                                                                 |
| trn_video_embed              |                                               |                                                                                 |
| trn_type_id                  | type ID                                       |                                                                                 |
| type_title                   | type title                                    |                                                                                 |
| lnk_trn_date_start []        | Start date of the event                       | date (yyyy-mm-dd)                                                               |
| lnk_trn_date_end []          | End date of the event                         | date (yyyy-mm-dd)                                                               |
| lnk_trn_type []              | Date option                                   | int; value either 1 or 4; 1 = Regular start and end date and 4 = Tentative date |
| lnk_trn_isonline []          | Online only event (no country, city or venue) | int, value either 1 or 0; 1 = true and 0 = false                                |
| lnk_trn_ctry_id []           | Country ID                                    | int, match with the country feed                                                |
| lnk_trn_city []              | City/Town/Village                             |                                                                                 |
| lnk_trn_venue []             | Venue and Room                                |                                                                                 |
| lnk_trn_tentative_loc []     |                                               | int, value either 1 or 0; 1 = true and 0 = false                                |
| lnk_trn_lang_id []           |                                               | int                                                                             |
| lnk_trn_lang_other []        |                                               | plain text                                                                      |
| lnk_trn_islivetranslation [] |                                               | int, value either 1 or 0; 1 = true and 0 = false                                |
| lnk_trn_livetran_info []     |                                               |                                                                                 |



## Retrieve UNISDR tagged news content

```shell
GET /sso-unisdr/api/mcr/tagged/isdr_news/get/all
```

Return in JSON format

```shell
{
   "current_page":1,
   "data":[
      {
         "ent_id":18672,
         "ent_title":"Making Cities Resilient on the agenda at the 20th Session of the Congress of Local and Regional Authorities of the Council of Europe",
         "ent_datemodified":"2011-03-30 08:26:11",
         "isdr_nws_summary":"On 22nd until 24th March the 20th Session of the Congress of Local and Regional Authorities of the Council of Europe was held in Strasbourg  to discuss issues including City Safety and the ISDR Making cities resilient 'my city is getting ready' world disaster reduction Campaign.",
         "isdr_nws_content":"On 22nd until 24th March the 20th Session of the Congress of Local and Regional Authorities of the Council of Europe was held in Strasbourg  to discuss issues including City Safety and the ISDR Making cities resilient 'my city is getting ready' world disaster reduction Campaign. \r\n\r\nThe Congress acknowledged the need to protect cities from disasters caused by natural hazards. \u2018Resilience is a word which should become part of our every day vocabulary\u2019, said Mr. Fr\u00e9con, President of the Congress. \r\n\r\nThe contribution of Ms. Helena Molin-Valdes, UNISDR Deputy Director, can be found here :  http:\/\/www.coe.int\/t\/congress\/Sessions\/20\/Videos_en.asp \r\n\r\nAdditional information on the 20th Session of the Congress of Local and Regional Authorities can be retrieved here http:\/\/www.coe.int\/t\/congress\/Sessions\/20\/default_en.asp",
         "isdr_nws_date_rel":"2011-03-30",
         "isdr_type_title":"News briefs",
         "lng_title":"English",
         "eupld_filename_image":"18293_fijilamicampaignsigningwithwomen080.jpg",
         "eupld_filename_image_label":"",
         "isdr_nws_lang_id":1,
         "isdr_nws_url":"http:\/\/www.unisdr.org\/news\/v.php?id=18672",
         "isdr_nws_order":0,
         "isdr_type":1,
         "isdr_nws_urltitle":"read more",
         "isdr_nws_photo_credit":null,
         "isdr_nws_photo_caption":null,
         "isdr_nws_author":null
      }
   ],
   "first_page_url":"\/sso-unisdr\/api\/mcr\/tagged\/pw_events\/get\/all?page=1",
   "from":1,
   "last_page":1,
   "last_page_url":"\/sso-unisdr\/api\/mcr\/tagged\/pw_events\/get\/all?page=1",
   "next_page_url":null,
   "path":"\/sso-unisdr\/api\/mcr\/tagged\/pw_events\/get\/all",
   "per_page":200,
   "prev_page_url":null,
   "to":40,
   "total":40,
   "status":200,
   "success":1
}
```

Field definition

| Field                      | Description     | Type/Value                                                         |
|----------------------------|-----------------|--------------------------------------------------------------------|
| ent_id                     |                 | int                                                                |
| ent_title *                | Title of entry  | plain text                                                         |
| isdr_nws_date_rel *        | Release date    | date (yyyy-mm-dd)                                                  |
| isdr_type_title            |                 | plain text                                                         |
| isdr_nws_summary           | Summary         | plain text, multiple line, data can be in HTML format              |
| isdr_nws_content           | Content/body    | plain text, multiple line, data can be in HTML format              |
| eupld_filename_image       | Image thumbnail | Add the full path to the filename https://www.unisdr.org/files/    |
| eupld_filename_image_label | Image caption   |                                                                    |
| isdr_nws_lang_id           | Language ID     |  value equivalent  6 = AR; 5 = ZH; 1 = EN; 2 = FR; 8 = RU; 4 = ES; |



## Retrieve attachments/links of PreventionWeb entry

```shell
GET /sso-unisdr/api/pw/entry/attachments/get/id/{id}
```



## Retrieve cities records with PreventionWeb HFA LGSAT report

```shell
GET /sso-unisdr/api/cities/pw/policy_plans/get/all
```
