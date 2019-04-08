# Global Platform 2019 API Documentation

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


## Retrieve programme records.

API call have hit rate of 100 per minute. Unique api call are cached in two minutes.

Query String Parameter:

* page integer (optional), page number
* per_page integer (optional), number of records per page (200 is the default and maximum value)
* q string (optional), perform simple search on the title/name of the programme (minimum 3 and maximum 30 characters)
* modified_since date format yyyy-mm-dd (optional), this condition will filter result equal or beyond given date correct format is yyyy-mm-dd

Header Parameters:

* Accept string, value ‘application/json’
* Authorization  string, value 'Bearer [ACCESS TOKEN received from step 1]'

```shell
GET /sso-unisdr/api/globalplatform/2019/program/get/all

GET /sso-unisdr/api/globalplatform/2019/program/get/all?page=2

GET /sso-unisdr/api/globalplatform/2019/program/get/all?q=Geneva

GET /sso-unisdr/api/globalplatform/2019/program/get/all?modified_since=2018-02-14
```

JSON Response

```shell
{  
   "current_page":1,
   "data":[  
      {  
         "gpe_id":916,
         "gpe_title":"Global Risk Assessment Framework",
         "gpe_event_id":"WS-10",
         "gpe_date":"2019-05-16",
         "gpe_time_from":"16:30:00",
         "gpe_time_to":"18:00:00",
         "gpe_room":"CICG - Room 4",
         "gpe_organizer":"UNISDR",
         "gpe_partner_orgs":"",
         "gpe_chair":"",
         "gpe_focal_point":"Marc (gordon6@un.org); Adam (adam.fysh@un.org)",
         "gpe_description":"<p>The Global Risk Assessment Framework (GRAF) aims to improve the understanding and management of current and future risks, at all scales, to better manage uncertainties and mobilize people, innovation and finance by: a) fostering interdisciplinary systems thinking with shared metrics and understanding and, b) enabling the identification of anomalies and precursor signals, as well as the correlations and dependencies of risks and actors to enable decision makers to act. Through actionable insights, tools and demonstrations at relevant scales to decision makers on a timely basis, the GRAF can build collective intelligence to steer societies towards an enhanced understanding and management of risk in all its dimensions, thereby realizing the goals and outcomes of the 2030 Agenda, the Sendai Framework, the Paris Agreement and the New Urban Agenda.<\/p>",
         "gpe_expected_results":"",
         "gpe_facilitator":"",
         "gpe_panelists":"",
         "gpe_agenda":"",
         "gpe_agenda_use_attachment":0,
         "gpe_agenda_filename":"",
         "gpe_datemodified":"2019-03-28 11:37:18",
         "gpe_year":2019,
         "gpe_lang_id":1,
         "floor_language":"English",
         "gpe_cart":"Yes",
         "gpe_isl_interpretation":"No",
         "gpe_accessible":"Yes",
         "gpe_livebroadcast":"No",
         "gpe_interpretation":"Yes",
         "gpe_interpretation_lng_id":"6,5,1,2,8,4",
         "gpe_remoteparticipation":"No",
         "gpe_participation":"Public",
         "type_id":2,
         "type_title":"Working Sessions"
      },
	  ...
   ],
   "first_page_url":"\/api\/globalplatform\/2019\/program\/get\/all?page=1",
   "from":1,
   "last_page":1,
   "last_page_url":"\/api\/globalplatform\/2019\/program\/get\/all?page=1",
   "next_page_url":null,
   "path":"\/api\/globalplatform\/2019\/program\/get\/all",
   "per_page":200,
   "prev_page_url":null,
   "to":28,
   "total":28,
   "status":200,
   "success":1
}
```




| Field                     	| Description                                                  	| Type/Value                                                                                                                      	|
|---------------------------	|--------------------------------------------------------------	|---------------------------------------------------------------------------------------------------------------------------------	|
| gpe_id                    	| ID                                                           	| int                                                                                                                             	|
| gpe_title                 	| Name or title of the programme                               	| plain text                                                                                                                      	|
| gpe_event_id              	| Programme reference code                                     	|                                                                                                                                 	|
| gpe_date                  	| Date of the session or programme                             	| date (yyyy-mm-dd)                                                                                                               	|
| gpe_time_from             	| Start time of the session                                    	| time (hh:ss), do not display to milliseconds                                                                                    	|
| gpe_time_to               	| End time of the session                                      	| time (hh:ss), do not display to milliseconds                                                                                    	|
| gpe_room                  	| Location of the session                                      	| plain text                                                                                                                      	|
| gpe_organizer             	| Organizers of the session                                    	| plain text, multiple line                                                                                                       	|
| gpe_partner_orgs          	| Partner organizations. Appears after the the main organizer. 	| plain text, multiple line                                                                                                       	|
| gpe_focal_point           	| Session focal point or contacts                              	| plain text, multiple line                                                                                                       	|
| gpe_description           	| Description of the session                                   	| plain text, multiple line, data can be in HTML format                                                                           	|
| gpe_expected_results      	|                                                              	| plain text, multiple line, data can be in HTML format                                                                           	|
| gpe_facilitator           	|                                                              	| plain text, multiple line, data can be in HTML format                                                                           	|
| gpe_panelists             	|                                                              	| plain text, multiple line, data can be in HTML format                                                                           	|
| gpe_agenda                	|                                                              	| plain text, multiple line, data can be in HTML format                                                                           	|
| gpe_agenda_use_attachment 	|                                                              	| int, value is either 1 or 0                                                                                                     	|
| gpe_agenda_filename       	| File name of the attachment                                  	| Add the full path to the filename https://www.unisdr.org/files/globalplatform/                                                  	|
| gpe_datemodified          	| Modification date of the entry                               	| date (yyyy-mm-dd hh:mm:ss)                                                                                                      	|
| gpe_lang_id               	| Primary floor language ID                                    	| int                                                                                                                             	|
| floor_language            	| Primary floor language                                       	| plain text                                                                                                                      	|
| gpe_cart                  	|                                                              	| plain text, value is either Yes or No                                                                                           	|
| gpe_isl_interpretation    	|                                                              	| plain text, value is either Yes or No                                                                                           	|
| gpe_accessible            	|                                                              	| plain text, value is either Yes or No                                                                                           	|
| gpe_livebroadcast         	|                                                              	| plain text, value is either Yes or No                                                                                           	|
| gpe_interpretation        	|                                                              	| plain text, value is either Yes or No                                                                                           	|
| gpe_interpretation_lng_id 	|                                                              	| value should be converted to respective equivalent  6 = AR; 5 = ZH; 1 = EN; 2 = FR; 8 = RU; 4 = ES;   sample value: 6,5,1,2,8,4 	|
| gpe_remoteparticipation   	|                                                              	| plain text, value is either Yes or No                                                                                           	|
| gpe_participation         	|                                                              	| plain text, value is either Yes or No                                                                                           	|
| type_id                   	|                                                              	| int                                                                                                                             	|
| type_title                	| Programme category or session type                           	| plain text                                                                                                                      	|





## Retrieve related background documents/presentations/lisks/videos of a programme

API call have hit rate of 100 per minute. Unique api call are cached in a minute.

URL Parameter:

* gpe_id integer (required), entry id of the programme

Header Parameters:

* Accept string, value ‘application/json’
* Authorization  string, value 'Bearer [ACCESS TOKEN received from step 1]'

```shell
GET /sso-unisdr/api/globalplatform/2019/program/get/id/[GPE_ID]
```

JSON Response

```shell
{  
   "status":200,
   "success":true,
   "data":{  
      "background_papers":[  
         {  
            "id":1045,
            "title":"Blank presentation",
            "filename":"entry_bg_paper~blank.pdf",
            "filesize":"138.91 Kb",
            "icon":"file-pdf-o",
            "extension":"PDF"
         }
      ],
      "related_links":[  
         {  
            "id":192,
            "title":"Test URL",
            "url":"https:\/\/unisdr.org",
            "icon":"external-link"
         }
      ],
      "presentations":[  
         {  
            "id":943,
            "title":"Presentation 2 ",
            "speaker":"Joel Margate",
            "filename":"entry_presentation~blank.pdf",
            "filesize":"138.91 Kb",
            "icon":"file-pdf-o",
            "extension":"PDF"
         }
      ],
      "videos":[  
         {  
            "id":902,
            "title":"Sample Embed",
            "code":"<iframe width=\"560\" height=\"315\" src=\"https:\/\/www.youtube.com\/embed\/2dMYR-YIOpU\" frameborder=\"0\" allow=\"accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture\" allowfullscreen><\/iframe>"
         }
      ],
      "outcomes":[  

      ]
   }
}
```



| Field                     	| Description                                                  	| Type/Value                                                                                                                      	|
|---------------------------	|--------------------------------------------------------------	|---------------------------------------------------------------------------------------------------------------------------------	|
| filename                    	| Document filename| string, add the full path to the filename https://www.unisdr.org/files/globalplatform/                                                                                                                             	|
