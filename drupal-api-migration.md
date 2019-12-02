# Drupal 8 API for Content Migration Documentation

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/


## Entries Attachments

### URL: /sso-unisdr/public/api/drupal/migration/get_attachments

```shell
GET /sso-unisdr/public/api/drupal/migration/get_attachments
```


### JSON Response

```shell
[
   {
      "id":1,
      "label":"View full document",
      "lng_id":1,
      "url":"https:\/\/www.preventionweb.net\/files\/554_8040.pdf"
   },
   ...
]
```

### Field definition

| Field      | Description   | Type/Value        |
|------------|---------------|-------------------|
| id         | ID            | int (primary key) |
| label      | Label         | plain text        |
| lng_id     | Language ID   | int               |
| label      | URL           | plain text        |


## Entries Related Links

### URL: /sso-unisdr/public/api/drupal/migration/get_related_links

```shell
GET /sso-unisdr/public/api/drupal/migration/get_related_links
```


### JSON Response

```shell
[
   {
      "id":1,
      "label":"View full document",
      "url":"https:\/\/www.preventionweb.net\/"
   },
   ...
]
```

### Field definition

| Field      | Description   | Type/Value        |
|------------|---------------|-------------------|
| id         | ID            | int (primary key) |
| label      | Label         | plain text        |
| label      | URL           | plain text        |




## Collection - Open Tags (taxonomy)

### URL: /sso-unisdr/public/api/drupal/migration/open_tags

```shell
GET /sso-unisdr/public/api/drupal/migration/open_tags
```


### JSON Response

```shell
[
   {
      "tag_id":1,
      "tag_name":"campaign2010-2011"
   },
   {
      "tag_id":2,
      "tag_name":"canarias2014"
   },
   ...
]
```

### Field definition

| Field      | Description | Type/Value |
|------------|-------------|------------|
| tag_id     | ID          | int        |
| tag_name   | Tag name    | plain text |



## Hazards (taxonomy)

### URL: /sso-unisdr/public/api/drupal/migration/taxonomy_hazards

```shell
GET /sso-unisdr/public/api/drupal/migration/taxonomy_hazards
```


### JSON Response

```shell
[
   {
      "scat_id":67,
      "scat_title":"Avalanche"
   },
   {
      "scat_id":56,
      "scat_title":"Cold Wave"
   },
   ...
]
```

### Field definition

| Field      | Description | Type/Value |
|------------|-------------|------------|
| scat_id    | ID          | int        |
| scat_title | Hazard name | plain text |


## Themes (taxonomy)


### URL: /sso-unisdr/public/api/drupal/migration/taxonomy_themes

```shell
GET /sso-unisdr/public/api/drupal/migration/taxonomy_themes
```


### JSON Response

```shell
[
   {
      "scat_id":41,
      "scat_title":"Advocacy & Media"
   },
   {
      "scat_id":31,
      "scat_title":"Capacity Development"
   },
   ...
]
```





## Language (taxonomy)

### URL: /sso-unisdr/drupal/migration/taxonomy_languages

```shell
GET /sso-unisdr/drupal/migration/taxonomy_languages
```
### JSON Response

```shell
[
   {
      "lng_id":6,
      "lng_title":"Arabic"
   },
   {
      "lng_id":5,
      "lng_title":"Chinese"
   },
   {
      "lng_id":1,
      "lng_title":"English"
   },
   {
      "lng_id":2,
      "lng_title":"French"
   },
   {
      "lng_id":8,
      "lng_title":"Russian"
   },
   {
      "lng_id":4,
      "lng_title":"Spanish"
   }
]
```

### Field definition

| Field     | Description | Type/Value |
|-----------|-------------|------------|
| lng_id    | ID          | int        |
| lng_title | Language    | plain text |



## Image/thumbnail used by entry

### References

* Destination pages
   * https://ijjqd4.axshare.com/#g=1&p=publication_detail

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/images

```shell
GET /sso-unisdr/api/drupal/migration/images
```

### JSON Response

```shell
[
   {
      "ent_id":26893,
      "credit":"",
      "caption":"Photo by wemissedthebus CC BY 2.0 2.0 http:\/\/www.flickr.com\/photos\/24936303@N08\/7026263283",
      "url":"https:\/\/www.preventionweb.net\/files\/26893_largeImage.jpg"
   },
   {
      "ent_id":26904,
      "credit":"UNISDR Panama Office",
      "caption":"The multistakeholder process in action in the Latin American region",
      "url":"https:\/\/www.preventionweb.net\/files\/26904_largeImage.jpg"
   },
   ...
]
```


## Organizations

Only published organizations and referenced as a source in UNDRR content entry. Resultset is cached for 60 minutes.

### TODO
* field_org_DRR_activities follow content mapping but will not be exposed until PW migration because this will not be used
* Note: nothing was mapped to field_body, check with Everis

### References

* Destination pages
   * no destination page to corporate website, only use as organization source
* Content type mapping https://docs.google.com/spreadsheets/d/1kYxhne-dvREr5XWQS75APAFeQhnpW2bK/edit#gid=987855230

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/organizations

```shell
GET /sso-unisdr/api/drupal/migration/organizations
```

### JSON Response

```shell
[
   {
      "org_id":3,
      "org_dateadded":"2007-08-30 19:05:27",
      "org_datemodified":"2019-07-23 11:33:39",
      "field_title":"United Nations Office for Disaster Risk Reduction \u2013 Regional Office for the Americas and the Caribbean",
      "field_country":131,
      "field_org_acronym":"UNDRR AM",
      "field_org_skype":"",
      "field_org_linkedin":"",
      "field_org_facebook":"",
      "field_org_twitter":"",
      "org_url":"http:\/\/eird.org\/americas\/index.html",
      "org_type_id":1,
      "org_type_title":"UN & International Organizations"
   },
   ...
]
```


## UN Resolutions and Reports content type

The resultset only includes "Disaster Risk Reduction Mandate".

### References

* Destination pages
   * Nick will develop a landing page
* Content mapping https://docs.google.com/spreadsheets/d/1kYxhne-dvREr5XWQS75APAFeQhnpW2bK/edit#gid=270554096


### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/resolutions

```shell
GET /sso-unisdr/api/drupal/migration/resolutions
```

### JSON Response

```shell
[
   {
      "ent_id":19034,
      "ent_dateadded":"2011-04-19 13:31:32",
      "field_title":"Thematic debate of the 65th session of the General Assembly on disaster risk reduction: President's summary",
      "field_user_comments":null,
      "field_editors_comments":null,
      "res_code":"A\/66\/PV.-",
      "res_date":"2011-02-09",
      "type": "Report of the UN Secretary-General",
      "author_name": "Leoj Ito",
      "field_links":[
         {
            "label":"Download in English",
            "url":"https:\/\/www.preventionweb.net\/files\/resolutions\/110225DRR.pdf",
            "lng_id":1
         }
      ],
      "field_open_tags":[

      ]
   },
   ...
]
```

## Terminology content type

### References

* Destination pages
   * https://ijjqd4.axshare.com/#g=1&p=terminology
   * https://ijjqd4.axshare.com/#g=1&p=terminology_detail


### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/terminology

```shell
GET /sso-unisdr/api/drupal/migration/terminology
```

### JSON Response

```shell
[
   {
      "ent_id":468,
      "current_url":["https://www.preventionweb.net/terminology/view/468"],
      "ent_dateadded":"2007-08-30 15:25:34",
      "field_title":"Building code",
      "field_user_comments":"",
      "field_editors_comments":"",
      "author_name": "Leoj Ito",
      "field_body":"<p>A set of ordinances or regulations and associated standards intended to regulate aspects of the design, construction, materials, alteration and occupancy of structures which are necessary to ensure human safety and welfare, including resistance to collapse and damage.<\/p>\n\n<p>Annotation: Building codes can include both technical and functional standards. They should incorporate the lessons of international experience and should be tailored to national and local circumstances. A systematic regime of enforcement is a critical supporting requirement for the effective implementation of building codes.<\/p>",
      "field_hazards":[

      ],
      "field_themes":[
         {
            "scat_id":104
         },
         {
            "scat_id":654
         }
      ],
      "field_related_links":[

      ],
      "field_links":[

      ]
   },
   ...
]
```

## Vacancies (Jobs) content type

### References

* Destination pages
   * https://ijjqd4.axshare.com/#g=1&p=vacancy_detail
   * Nick is checking the list page
* Content type mapping https://docs.google.com/spreadsheets/d/1kYxhne-dvREr5XWQS75APAFeQhnpW2bK/edit#gid=1765529697

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/vacancies

```shell
GET /sso-unisdr/api/drupal/migration/vacancies
```

### JSON Response

```shell
[
   {
      "ent_id":592,
      "current_url":["https://www.preventionweb.net/jobs/view/592", "https://www.unisdr.org/who-we-are/vacancies/592"],
      "field_title":"Disaster management delegate",
      "ent_dateadded":"2007-09-04 16:41:39",
      "ent_datemodified":"2007-09-19 12:30:56",
      "field_user_comments":"Online applications only",
      "field_editors_comments":null,
      "field_body":"<p><u>Background:<\/u><\/p>\n\n<p>Under DIPECHO funding, the delegate will assist the local national societies (Paraguay, Bolivia, Argentina) to develop and strengthen their disaster management and response capacity in the Gran Chaco region by: assisting the national societies with the planning and development of their disaster preparedness programme; strengthening the capacity of the national societies at the regional level; assisting in the development and implementation of a comprehensive approach of the regional and transboundary risk and disaster problematic of the Gran Chaco region; and, ensuring overall guidance and support to the implementation of the regional multi-hazard risk reduction and preparedness of the Gran Chaco region.<\/p>\n\n<p><u>Key tasks and responsibilties:<\/u><\/p>\n\n<p>Assist the national societies through the process of dissemination and knowledge sharing in order to have the targeted local actors and organizations increased their knowledge and perception of the problematic situation<\/p>\n\n<p>Assist the national societies with the integration of the local project results in their corresponding national plan for risk reduction and RCRC disaster response plan.<\/p>\n\n<p>Assist the national societies in relevant integration with National Civil Protection\/Defense national strategies.<\/p>\n\n<p>Assist the national societies at the local level of the Red Cross and other local organizations in the region to apply VCA, Contingency Planning, and other instruments included in the Local Risk Reduction and Disaster Preparedness toolkit produced in the Federation DIPECHO IV Single Form Proposal.<\/p>\n\n<p>Assist the national societies in drafting local (municipal or departmental) contingency plans using Red Cross planning instruments.<\/p>\n\n<p>Assist the national societies to ensure that there local committees for disaster preparedness (civil protection) are operational, with the participation of local Red Cross.<\/p>\n\n<p>Assist the national societies in developing, testing and adopting systems and procedures for early warning and evacuation in communities with high exposure to flooding.<\/p>\n\n<p>Assist the national societies to work with community-level schools to produce and adopt Scholar Security Plans.<\/p>\n\n<p>Assist the national societies to include, distribute and apply traditional and indigenous knowledge, relevant to disaster preparedness, amonst selected communities.<\/p>\n\n<p>Disseminate the understanding and application of the best practices of volunteer management in community level Red Cross disaster preparedness activities.<\/p>\n\n<p>Produce regular, accurate and timely field reports for the Federation and for specific donors.<\/p>\n\n<p><u>Duties applicable to all staff:<\/u><\/p>\n\n<p>Actively work towards the achievement of the Secretariat's goals.<br \/>\nAbide by and work in accordance with the Red Cross Red Crescent principles.<br \/>\nPerform any other work related duties and responsibilities that may be assigned by the line manager.<\/p>\n\n<p><u>Education:<\/u><\/p>\n\n<p>Basic Delegates Training Course<br \/>\nProfessional qualifications in development studies or related area (preferred)<br \/>\nTraining in Security and safety in humanitarian operations (preferred)<br \/>\nUniversity degree (preferred)<\/p>\n\n<p><u>Experience:<br \/>\n<\/u><br \/>\nManaging and supporting staff - 3 years.<br \/>\nWorking in RCRC operations - 3 years.<br \/>\nDisaster management, preparedness and response in developing countries.<br \/>\nAdvocacy (programme profiling) and donor relations (narrative and financial reporting).<br \/>\nPlanning and managing a budget.<br \/>\nConducting vulnerability and capacity assesments, to include risk mapping.<br \/>\nPlanning and implementing human resource development and training programmes.<br \/>\nFacilitating institutional development and organisational change.<\/p>\n\n<p><u>Skills:<\/u><\/p>\n\n<p>Skills in training, developing and supporting staff<br \/>\nSelf-supporting in computers (MS-Windows, database, etc).<br \/>\nValid international driving license, manual transmission<\/p>\n\n<p><u>Languages:<\/u><\/p>\n\n<p>Advanced level of Spanish.<br \/>\nAdvanced level of English.<br \/>\nIntermediate level of Portugues (preferred).<\/p>\n\n<p><u>Competencies:<\/u><\/p>\n\n<p>National Society relations<br \/>\nResults focus and accountability<br \/>\nTeamwork<br \/>\nCommunications<br \/>\nProfessional standards<br \/>\nLeadership<br \/>\nManagerial Effectiveness<\/p>",
      "job_post_url":"https:\/\/jobnet.ifrc.org\/public\/hrd-cl-vac-view.asp?jobinfo_uid_c=498&vaclng=en",
      "field_city_aditional_loc":"Tarija, Bolivia (TBC)",
      "field_closing_date":"2007-09-28",
      "author_name": "Leoj Ito",
      "ent_contact_name": "Leoj Ito",
      "field_email": "leoj@undrr.org",
      "field_country":[
         {
            "ctry_id":129,
            "ctry_iso3_code":"PAK"
         }
      ],
      "field_organization":[
         {
            "org_id":82
         },
         {
            "org_id":406
         }
      ],
      "field_region":[
         {
            "cont_id":2
         }
      ],
      "field_hazards":[
         {
            "scat_id":58
         },
         {
            "scat_id":59
         },
         {
            "scat_id":60
         },
         {
            "scat_id":62
         },
         {
            "scat_id":65
         },
         {
            "scat_id":67
         },
         {
            "scat_id":73
         }
      ],
      "field_themes":[
         {
            "scat_id":31
         },
         {
            "scat_id":35
         }
      ],
      "field_related_links":[
         {
            "label":"More information and application details",
            "url":"https:\/\/jobnet.ifrc.org\/public\/hrd-cl-vac-view.asp?jobinfo_uid_c=498&vaclng=en"
         }
      ],
      "field_links":[
         {
            "label":"View application form",
            "url":"https:\/\/www.preventionweb.net\/files\/1280_1284adpcapplicationform.doc",
			"lng_id":1
         }
      ],
      "field_open_tags":[

      ]
   },
   ...
]
```

### Field definition

todo






## UNDRR News type (taxonomy)

### URL: /sso-unisdr/api/drupal/migration/news_type

```shell
GET /sso-unisdr/api/drupal/migration/news_type
```

### JSON Response

```shell
{ 
   "1":"Updates",
   "2":"Press Releases",
   "3":"Statements and messages",
   "4":"Features",
   "5":"Research briefs",
   "6":"Op Eds"
}
```


## UNDRR News and PW News

### References

* Destination pages
   * https://ijjqd4.axshare.com/#g=1&p=news_list
   * https://ijjqd4.axshare.com/#g=1&p=new_detail
* Content type mapping https://docs.google.com/spreadsheets/d/1kYxhne-dvREr5XWQS75APAFeQhnpW2bK/edit#gid=2983063

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/news

```shell
GET /sso-unisdr/api/drupal/migration/news
```

### JSON Response

```shell
[
   {
      "ent_id":5524,
      "current_url":[],
      "field_title":"IPCC workshop on extreme events management accepted",
      "field_short_title":"",
      "ent_dateadded":"2008-11-11 12:09:13",
      "ent_datemodified":"2008-12-17 18:37:50",
      "field_user_comments":"climate change",
      "field_editors_comments":"",
      "field_body":"<p>The 29th session of the IPCC meeting (Geneva, 1-4 September 2008) agreed to hold a scoping workshop on the IPCC Special Report on Managing Extreme Events to Advance Adaptation proposed by Norway and the ISDR system with support from Luxembourg. The workshop will be held in early 2009 and recommend to the IPCC's 30th session whether it should undertake the proposed report.<\/p>",
      "nws_summary":"The 29th session of the IPCC meeting (Geneva, 1-4 September 2008) agreed to hold a scoping workshop on the IPCC Special Report on Managing Extreme Events to Advance Adaptation proposed by Norway and the ISDR system with support from Luxembourg...",
      "field_release_date":"2008-09-04",
      "field_news_type":1,
      "isdr_nws_photo_caption":"",
      "isdr_nws_photo_credit_url":"",
      "isdr_nws_photo_credit":"",
      "nws_url":"",
      "nws_lang_id":1,
      "domain":"www_undrr_org, www_preventionweb_net",
      "field_country":[

      ],
      "field_organization":[
         {
            "org_id":1171
         }
      ],
      "field_region":[

      ],
      "field_hazards":[

      ],
      "field_themes":[
         {
            "scat_id":33
         }
      ],
      "field_related_links":[

      ],
      "field_links":[
         {
            "label":"Proposal of Norway and ISDR System to IPCC",
            "url":"https:\/\/www.preventionweb.net\/files\/5524_IPCCNorwayISDRsystemProposal.pdf",
            "lng_id":1
         }
      ],
      "field_open_tags":[

      ]
   },
   ...
]
```

## Publication type (taxonomy)

### URL: /sso-unisdr/api/drupal/migration/publication_type

```shell
GET /sso-unisdr/api/drupal/migration/publication_type
```

### JSON Response

```shell
{
   "1":"Tool Kits",
   "2":"Fact Sheets",
   "3":"UNDRR Documents",
   "4":"Reports",
   "5":"WiA",
   "6":"Working papers",
   "7":"Other"
}
```


## Documents and publications

### Important

* Publication type (pub_type_id) 1,4,5,6 include to PreventionWeb domain.

### References

* Destination pages
   * https://ijjqd4.axshare.com/#g=1&p=publication_list
   * https://ijjqd4.axshare.com/#g=1&p=publication_detail
* Content type mapping https://docs.google.com/spreadsheets/d/1kYxhne-dvREr5XWQS75APAFeQhnpW2bK/edit#gid=270554096

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/publications

```shell
GET /sso-unisdr/api/drupal/migration/publications
```

### JSON Response

```shell
[
   {
      "ent_id":547,
      "current_url":[],
      "field_title":"Gender perspective: working together for disaster risk reduction",
      "ent_dateadded":"2007-09-03 16:08:26",
      "ent_datemodified":"2019-10-16 14:35:49",
      "field_user_comments":"[SWH] updated style and added attachment 10 Dec 07",
      "field_editors_comments":"",
      "field_body":"<p><em>Good practices and lessons learned<\/em>:<br \/><br \/>\n<br \/><br \/>\nThis publication is part of ongoing efforts facilitated by the UNISDR secretariat to build a global partnership for mainstreaming gender issues into the disaster risk reduction process. Such efforts have become urgent because disaster risk reduction has long remained a largely male dominated affair, yet it is clear that the full and balanced participation of women and men, and girls and boys make disaster risk reduction more effective. The present good practices have been compiled to draw the attention of practitioners, policy\/decision makers and stakeholders, be they men or women, to the fact that gender-inclusive disaster risk reduction is feasible immediately, even in rural community settings where gender insensitivity is generally pervasive. This publication presents a collection of 15 practices that advance gendered resilience building--a key principle that informs the implementation of the Hyogo Framework for Action.<\/p>",
      "field_authors":"",
      "author_name":"Leoj Ito",
      "field_isbn":"",
      "field_title_original":"",
      "field_number_page":"54 p.",
      "field_year_of_publication":2007,
      "pub_type_id":"5",
      "domain":"www_undrr_org",
      "field_country":[
         {
            "ctry_id":24,
            "ctry_iso3_code":"BRA"
         },
         {
            "ctry_id":76,
            "ctry_iso3_code":"HND"
         },
         {
            "ctry_id":79,
            "ctry_iso3_code":"IND"
         },
         {
            "ctry_id":80,
            "ctry_iso3_code":"IDN"
         },
         {
            "ctry_id":86,
            "ctry_iso3_code":"JAM"
         },
         {
            "ctry_id":112,
            "ctry_iso3_code":"MEX"
         },
         {
            "ctry_id":129,
            "ctry_iso3_code":"PAK"
         },
         {
            "ctry_id":134,
            "ctry_iso3_code":"PER"
         },
         {
            "ctry_id":135,
            "ctry_iso3_code":"PHL"
         },
         {
            "ctry_id":162,
            "ctry_iso3_code":"LKA"
         },
         {
            "ctry_id":177,
            "ctry_iso3_code":"TUR"
         }
      ],
      "field_organization":[
         {
            "org_id":1171
         }
      ],
      "field_region":[

      ],
      "field_hazards":[

      ],
      "field_themes":[
         {
            "scat_id":38
         },
         {
            "scat_id":762
         }
      ],
      "field_related_links":[

      ],
      "field_links":[
         {
            "label":"View full document",
            "url":"https:\/\/www.preventionweb.net\/files\/547_gendergoodpractices.pdf",
			"lng_id":1
         }
      ],
      "field_open_tags":[

      ]
   },
   ...
]
```

## Event & Training

### Important

* Entries tagged with campaign internal tag will be available on MCR domain.

### References

* Content type mapping https://docs.google.com/spreadsheets/d/1kYxhne-dvREr5XWQS75APAFeQhnpW2bK/edit#gid=1294149393

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/event_training

```shell
GET /sso-unisdr/api/drupal/migration/event_training
```

### JSON Response

```shell
[
   {
      "ent_id":43624,
      "current_url":[],
      "field_title":"Resilience Action Planning: Implementing the Sendai Framework at the Local Level - Online course",
      "ent_dateadded":"2015-04-09 09:16:42",
      "ent_datemodified":"2018-10-08 20:55:09",
      "field_user_comments":"",
      "field_editors_comments":"PW editor 1 - changed the organizations,removed some tags, added contacts",
      "author_name":"Tessa Scholma",
      "field_body":"<h3><strong>About the Course<\/strong><\/h3>\n\n<p>Over the past 20 years disasters have affected 4.4 billion people, caused USD 2 trillion of damage and killed 1.3 million people. Disasters have affected people living in developing countries and, in particular, the most vulnerable communities within these countries.<\/p>\n\n<p>Particularly in the context of increased urbanization, urban risk continues to rise. The vulnerability of cities to disasters is growing especially as poor people settle in high-risk urban areas. Unfortunately, the planning and development of cities has given little consideration to the consequences of hazards such as earthquakes, hydro-meteorological risks and others. The implication of this reality is the need for countries to focus on creating a safer world for urban dwellers and developing a series of innovative approaches to build resilience.<\/p>\n\n<p>On the basis of these needs, UNITAR, in partnership with UNISDR&rsquo;s Global Education and Training Institute (ONEA-GETI), has developed the e-learning course Urban Risk Reduction: Developing and Implementing Resilience Action Plans for Cities.<\/p>\n\n<h3><strong>Course Objectives<\/strong><\/h3>\n\n<p>This e-Learning course aims to strengthen the capacities of government officials, especially those at the local level, and disaster management professionals to design and implement plans and programmes that reduce disaster risk and enhance resilience.<\/p>\n\n<h3><strong>Content:<\/strong><\/h3>\n\n<ul class=\"bullet\">\n\n<li>Module 1: Disaster Risk Reduction Concepts and Introduction to Current Trends&nbsp;<\/li>\n\n<li>Module 2: Implementing the Sendai Framework for Disaster Risk Reduction (2015-2030)<\/li>\n\n<li>Module 3: Introduction to Making Cities Resilient Global Campaign and tools<\/li>\n\n<li>Module 4: DRR Assesment and Analysis Tools<\/li>\n\n<li>Module 5: Mainstreaming Disaster Risk Reduction into Sectoral Programmes for Socio-Economic Development<\/li>\n\n<li>Module 6: Developing, Implementing, Monitoring Resilient Action Plans,&nbsp;Safe and Resilient Action Plans<\/li>\n\n<\/ul>\n\n<h3><strong>Methodology<\/strong><\/h3>\n\n<p>This 6-module course includes interactive lessons that introduce the participant to the conceptual foundations of disaster risk reduction and urban resilience. the learning materials are presented through various media, such as text, graphs, images and video material, which contribute to better retention and enhance the learning process. Participants engage in a set of asssessment quizzes, discussion forums, and practical activities to facilitate interaction and experience sharing.<\/p>\n\n<div style=\"margin-left:0px !important;\">\n\n<div aria-labelledby=\"headingFive\" id=\"collapseFive\" role=\"tabpanel\">\n\n<div>\n\n<p>Besides the interactive lessons, participants engage in a set of practical exercises, where they can apply the knowledge gained to a real-life situation. Collaborative activities and discussion forums are other core elements of the course, organized to create collective knowledge and to facilitate interaction and experience sharing. The course also includes formative exercises as well as quizzes. A moderator guides participants through all the learning activities.&nbsp;<\/p>\n\n<h3><strong>Participant Profile<\/strong><\/h3>\n\n<\/div>\n\n<\/div>\n\n<\/div>\n\n<p>The course is open to city and local government officials, disaster management professionals, and representatives from academic and training institutions working on disaster risk reduction.<\/p>\n\n<h3><strong>Additional information<\/strong><\/h3>\n\n<p>A certificate of completion will be issued to participants who achieve a minimum total score of 70%. A certificate of participation will be issued to participants who complete all mandatory activities but achieve a final score inferior to 70%.<\/p>\n\n<p><strong>BONUS:<\/strong> Those students who perform excellent results will be rewarded by being included in the &ldquo;List of Experts&rdquo; of UNISDR. As an expert, you will have the opportunity of being consulted and invited to several workshops\/events.&nbsp;<\/p>\n\n<p><strong>Course Fee: <\/strong>100 USD (group discounts are available)<\/p>\n\n<p><strong>Contact: <\/strong>e-dcp@unitar.org<\/p>\n\n<p><strong>Please register by October 14<\/strong><\/p>",
      "ent_contact_name":"Leoj Ito",
      "field_email":"email@un.org",
      "trn_event_url":"https:\/\/www.unitar.org\/event\/full-catalog\/resilience-action-planning-implementing-sendai-framework-local-level-1",
      "field_start_date":"2018-10-08",
      "field_end_date":"2018-12-21",
      "field_online":1,
      "field_event_country":"",
      "field_event_city":"",
      "field_venue":"",
      "ent_lang_id":1,
      "field_twitter_hashtag":"",
      "trn_type_id":3,
      "trn_type":"Training",
      "translation":[
         {
            "entt_ent_id":43624,
            "entt_title":"Planes de Acci\u00f3n para Resiliencia - Implementar el Marco de Sendai al Nivel Local",
            "entt_desc":"<p>En los \u00faltimos 20 a\u00f1os, los desastres han afectado a 4.400 millones de personas, han causado da\u00f1os por valor de 2 billones de d\u00f3lares y han causado la muerte de 1,3 millones de personas. Los desastres han afectado a las personas que viven en los pa\u00edses en desarrollo y, en particular, a las comunidades m\u00e1s vulnerables de esos pa\u00edses. En particular en el contexto de la creciente urbanizaci\u00f3n, el riesgo urbano sigue aumentando. La vulnerabilidad de las ciudades a los desastres es cada vez mayor, especialmente a medida que los pobres se asientan en zonas urbanas de alto riesgo.<\/p>\r\n\r\n<p>Lamentablemente, en la planificaci\u00f3n y el desarrollo de las ciudades se ha prestado poca atenci\u00f3n a las consecuencias de peligros como los terremotos, los riesgos hidrometeorol\u00f3gicos y otros. La implicaci\u00f3n de esta realidad es la necesidad de que los pa\u00edses se centren en la creaci\u00f3n de un mundo m\u00e1s seguro para los habitantes de las ciudades y en el desarrollo de una serie de enfoques innovadores para aumentar la resiliencia.<\/p>\r\n\r\n<p>Este curso de aprendizaje electr\u00f3nico tiene por objeto fortalecer la capacidad de los funcionarios gubernamentales, especialmente los de nivel local, y de los profesionales de la gesti\u00f3n de desastres para dise\u00f1ar y aplicar planes y programas que reduzcan el riesgo de desastres. riesgo de desastres y aumentar la resiliencia.<\/p>\r\n\r\n<p><h3>Objetivos del evento<\/h3><\/p>\r\n\r\n<p>El curso de e-learning tiene por objectivo de reenforzar las capacidades de los funcionarios del gobierno, especielmente los que trabajan al nivel local, y a los profesionales de manejan los desastres para que conciban y implementen planes y programas que reducir\u00e1n el riego de desastre s y que mejorar\u00e1n la resilencia.<\/p>\r\n\r\n<p>Al final del curso, los participantes lograr\u00e1n:<\/p>\r\n\r\n<p>-Sensibilizar sobre el \"Making Cities Resilient (MRC) Campaign\";<\/p>\r\n\r\n<p>-Identificar las iniciativas y las mejores pr\u00e1cticas para integrar la reducci\u00f3n del riesgo y la adopci\u00f3n del cambio clim\u00e1tico en la planificaci\u00f3n urbana;<\/p>\r\n\r\n<p>-Evaluar la siatuaci\u00f3n de la gesti\u00f3n del riesgo en sus paises usando harramientas;<\/p>\r\n\r\n<p>-Desarrollar un plan de acci\u00f3n seguro y resiliente para sus ciudades\/paises;<\/p>\r\n\r\n<p>-Analizar el objetivo, las metas y el resultado del HFAb y del Marco de Sendai.<\/p>\r\n\r\n<p><h3>Contenido y estructura<\/h3><\/p>\r\n\r\n<p>Este curso se compone de los siguientes m\u00f3dulos:<p>\r\n\r\n<p>-M\u00f3dulo 1: Conceptos de reducci\u00f3n del riesgo de desastres e introducci\u00f3n a las tendencias actuales del riesgo urbano.<\/p>\r\n<p>-M\u00f3dulo 2: Aplicaci\u00f3n del Marco de Sendai para la Reducci\u00f3n del Riesgo de Desastres (2015-2030).<\/p>\r\n<p>-M\u00f3dulo 3: Introducci\u00f3n a las herramientas de la campa\u00f1a Making Cities Resilient (MCR).<\/p>\r\n<p>-M\u00f3dulo 4: Herramientas de evaluaci\u00f3n y an\u00e1lisis de la RRD.<\/p>\r\n<p>-M\u00f3dulo 5: Incorporaci\u00f3n de la RRD en los programas sectoriales de desarrollo socioecon\u00f3mico.<\/p>\r\n<p>-M\u00f3dulo 6: Desarrollar, implementar, monitorear y evaluar planes de acci\u00f3n seguros y resistentes.<\/p>\r\n\r\n<p><h3>Metodolog\u00eda<\/h3><\/p>\r\n\r\n<p>Este curso de 6 m\u00f3dulos incluye lecciones interactivas que introducen al participante en los fundamentos conceptuales de la reducci\u00f3n del riesgo de desastres y la resiliencia urbana.<\/p>\r\n\r\n<p>Los materiales de aprendizaje se presentan a trav\u00e9s de diversos medios, como textos, gr\u00e1ficos, im\u00e1genes y material de v\u00eddeo, que contribuyen a una mejor retenci\u00f3n y mejoran el proceso de aprendizaje. Los participantes participan en una serie de cuestionarios de evaluaci\u00f3n, foros de discusi\u00f3n, seminarios web con expertos de renombre y actividades pr\u00e1cticas para facilitar la interacci\u00f3n y el intercambio de experiencias.<\/p>\r\n\r\n<p><h3>Participantes<\/h3><\/p>\r\n\r\n<p>El curso est\u00e1 abierto a funcionarios de los gobiernos municipales y locales, profesionales de la gesti\u00f3n de desastres y representantes de instituciones acad\u00e9micas y de capacitaci\u00f3n que trabajan en la reducci\u00f3n del riesgo de desastres y el desarrollo sostenible.<\/p>\r\n\r\n<p><h3>Informaci\u00f3n adicional<\/h3><\/p>\r\n\r\n<p>Al final del curso, se entregar\u00e1 un certificado de finalizaci\u00f3n a los participantes que alcancen una puntuaci\u00f3n total m\u00ednima del 70%.<\/p>\r\n\r\n<p>BONO: los estudiantes que obtengan excelentes resultados ser\u00e1n recompensados con su inclusi\u00f3n en la \u201cLista de expertos\u201d de la UNISDR. Como experto, usted tendr\u00e1 la oportunidad de ser consultado e invitado a varios talleres\/eventos.<\/p>\r\n\r\n<p><strong>Por favor reg\u00edstrese antes del 14 de octubre<\/strong><\/p>",
            "entt_lang_id":4,
            "entt_dateadded":"2017-02-08 09:09:55"
         }
      ],
      "domain":"www_undrr_org",
      "field_country":[

      ],
      "field_organization":[
         {
            "org_id":1422
         },
         {
            "org_id":9351
         }
      ],
      "field_region":[

      ],
      "field_hazards":[

      ],
      "field_themes":[
         {
            "scat_id":33
         },
         {
            "scat_id":34
         },
         {
            "scat_id":44
         },
         {
            "scat_id":47
         },
         {
            "scat_id":108
         }
      ],
      "field_related_links":[
         {
            "label":"More about the Sendai Framework",
            "url":"https:\/\/www.preventionweb.net\/drr-framework\/sendai-framework"
         }
      ],
      "field_links":[
         {
            "label":"Registration",
            "url":"https:\/\/www.unitar.org\/event\/cart",
			"lng_id":1
         },
         {
            "label":"Inscripci\u00f3n",
            "url":"https:\/\/www.unitar.org\/event\/cart",
			"lng_id":2
         }
      ],
      "field_open_tags":[
         {
            "tag_id":1,
            "tag_name":"campaign2010-2011"
         }  
      ]
   },
   ...
]
```

### Field definition

| Field                  | Description                             | Type/Value                                                   |
|------------------------|-----------------------------------------|--------------------------------------------------------------|
| ent_id                 | Entry ID                                | int (primary key)                                            |
| current_url            | URLs of the entry                       | Array of text                                                |
| field_title            | Title of the entry                      | plain text                                                   |
| ent_dateadded          | Date added                              | full date; yyyy-mm-dd hh:mm:ss                               |
| ent_datemodified       | Date modified                           | full date; yyyy-mm-dd hh:mm:ss                               |
| field_user_comments    | User comments                           | plain text; multiline                                        |
| field_editors_comments | CMS editor comments                     | plain text; multiline                                        |
| author_name            | Name of the person created the record   | plain text                                                   |
| field_body             | Content body                            | html                                                         |
| ent_contact_name       |                                         | plain text                                                   |
| field_email            |                                         | plain text                                                   |
| trn_event_url          | Event URL                               | URL                                                          |
| field_start_date       | Event start date                        | date; yyyy-mm-dd                                             |
| field_end_date         | Event end date                          | date; yyyy-mm-dd                                             |
| field_online           | Is entry an online event                | int; possible value= 0 or 1; 0=false and 1=true              |
| field_event_country    | Country ID                              | int; see country integration API for country name equivalent |
| field_event_city       |                                         | plain text                                                   |
| field_venue            |                                         | plain text                                                   |
| ent_lang_id            | Language ID of the entry                | int                                                          |
| field_twitter_hashtag  |                                         | plain text                                                   |
| trn_type_id            |                                         | int; possible value 1 or 3; 1 = Event, 3 = training          |
| trn_type               |                                         | plain text; possible value Event or Training                 |
| translation            | Collection                              | Array                                                        |
| - entt_ent_id          | foreign key to entry_id                 | int                                                          |
| - entt_title           | Translation of title (field_title)      | plain text                                                   |
| - entt_desc            | Translation of the content (field_body) | html                                                         |
| - entt_lang_id         | Language ID of the translation          | int                                                          |
| - entt_dateadded       |                                         | full date; yyyy-mm-dd hh:mm:ss                               |
| domain                 |                                         | Array; possible values undrr, pw, mcr                        |
| field_country          | Country ID                              | int                                                          |
| field_organization     |                                         | Array                                                        |
| field_region           |                                         | Array                                                        |
| field_hazards          |                                         | Array                                                        |
| field_themes           |                                         | Array                                                        |
| field_related_links    |                                         | Array                                                        |
| field_links            |                                         | Array                                                        |
| - label                | Label/text display of the link          | plain text                                                   |
| - url                  | Target URL of the link                  | plain text                                                   |
| - lng_id               | Language ID                             | int; see Language taxonomy for quivalent                     |
| field_open_tags    	 |                                         | Array                                                        |

## Educational material 

### Important

* Only target audiece = childen will be imported.

### References

* Content type mapping https://docs.google.com/spreadsheets/d/1kYxhne-dvREr5XWQS75APAFeQhnpW2bK/edit#gid=270554096

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/drupal/migration/educational_materials

```shell
GET /sso-unisdr/api/drupal/migration/educational_materials
```

### JSON Response

```shell
[
   {
      "ent_id":3423,
      "current_url":[],
      "field_title":"ABC desastres",
      "ent_dateadded":"2008-08-22 16:42:54",
      "ent_datemodified":"2008-10-16 11:20:52",
      "field_user_comments":"",
      "field_editors_comments":"[MP] completed entry aligned themes 10Sept08\r\n[MCH]revised and published (16Oct08)",
      "author_name":"Marla Petal",
      "field_body":"<p>La idea consiste en que estudiantes (ni&ntilde;os y j&oacute;venes) y tambi&eacute;n sus docentes- encendiendo computadoras y apretando teclas- vayan apropi&aacute;ndose de saberes, aportando as&iacute; herramientas y cambios de actitudes, capaces de construir un camino diferente.<br \/><br \/>\n<br \/><br \/>\n<span class=\"style2\">En esta secci&oacute;n encontrar&aacute;s toda la informaci&oacute;n que  necesites sobre Riesgos y Desastres Naturales. Para consultar, para utilizar en  el colegio y para informarte. Sabr&aacute;s qu&eacute; hacer en una situaci&oacute;n de riesgo y c&oacute;mo  resolver problemas.<\/span><span class=\"style12\"><br \/><br \/>\n<\/span><\/p>",
      "ent_contact_name":"",
      "edu_audience_subgroup":"Pre-school & kindergarten (<6 years)",
      "field_authors":"",
      "field_isbn":"",
      "field_title_original":"",
      "field_number_page":"",
      "field_year_of_publication":2007,
      "domain":"www_undrr_org",
      "field_country":[

      ],
      "field_organization":[
         {
            "org_id":3
         }
      ],
      "field_region":[
         {
            "cont_id":3
         }
      ],
      "field_hazards":[

      ],
      "field_themes":[
         {
            "scat_id":36
         }
      ],
      "field_related_links":[
         {
            "label":"Visit publisher for more information",
            "url":"http:\/\/www.eird.org\/fulltext\/ABCDesastres\/index.htm"
         }
      ],
      "field_links":[

      ],
      "field_open_tags":[

      ]
   },
   ...
]
```

### Field definition

| Field                 | Description                | Type/Value                                                                                                                                                                                                                                                                                                         |
|-----------------------|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ent_id                | Entry ID                   | int (primary key)                                                                                                                                                                                                                                                                                                  |
| field_title_original  | Title in original language | plain text                                                                                                                                                                                                                                                                                                         |
| edu_audience_subgroup | Target audience            | plain text; possible value "Pre-school & kindergarten (<6 years), Primary school age (6-11 years), Secondary school age (12-18 years)" please note that Fanny documented the changes under "Field Summary" tab ROW 118 https://docs.google.com/spreadsheets/d/1kYxhne-dvREr5XWQS75APAFeQhnpW2bK/edit#gid=147073088 |


## Response Headers

* X-Total-Records integer
* X-IsCached 
