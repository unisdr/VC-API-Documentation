# Drupal 8 API for Content Migration Documentation

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/



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
      "ent_id":525,
      "caption":"",
      "url":"https:\/\/www.preventionweb.net\/files\/525_525.jpg"
   },
   {
      "ent_id":531,
      "caption":"Lorem ipsum dolor sit amet",
      "url":"https:\/\/www.preventionweb.net\/files\/531_531.jpg"
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
            "url":"https:\/\/www.preventionweb.net\/files\/1280_1284adpcapplicationform.doc"
         }
      ]
   }
]
```

### Field definition

todo







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
      "ent_id":5526,
      "field_title":"Bali Roadmap on Climate Change recognizes importance of disaster risk reduction",
      "field_short_title":"",
      "ent_dateadded":"2008-11-11 12:19:09",
      "ent_datemodified":"2008-12-17 18:36:08",
      "field_user_comments":"climate change",
      "field_editors_comments":"",
      "field_body":"<p>Disaster Risk Reduction (DRR) was included in the Bali Action Plan as a tool for climate change adaptation. The Bali Action Plan was adopted by UN member states on 15 December at the UN Framework Convention on Climate Change (UNFCCC) Conference. It called for enhanced action on adaptation, including DRR strategies to lessen the impact of disasters on developing countries; risk management and risk reduction strategies including risk transfer mechanisms such as insurance; and more international cooperation on implementation, such as through vulnerability assessments. At a side event, the Working Group on Climate Change and Disaster Risk Reduction recommended that adaptation be a pillar of any eventual climate change agreement; that DRR and climate risk management be core elements of adaptation; that mechanisms for funding adaptation and disaster risk reduction be established; and that immediate action be taken to implement risk reduction measures from 2008-2012. Participants included representatives from UNEP, UNDP, UNISDR, WHO, WMO, WB, Red Cross, Oxfam, and CARE International.<\/p>",
      "isdr_nws_summary":"The main outcome document of the UNFCCC 13th Conference of the Parties, the Bali Action Plan, sets the path toward a new international climate change agreement. UNISDR is supporting countries in implementing the Bali Action Plan.",
      "field_release_date":"2007-12-17",
      "field_news_type":1,
      "isdr_nws_photo_caption":"",
      "isdr_nws_photo_credit_url":"",
      "isdr_nws_photo_credit":"",
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
            "label":"The Bali Action Plan",
            "url":"https:\/\/www.preventionweb.net\/files\/5526_BaliActionplan.pdf"
         },
         {
            "label":"The Bali Action Plan and disaster risk reduction",
            "url":"https:\/\/www.preventionweb.net\/files\/5526_BaliActionPlanandDRR.pdf"
         },
         {
            "label":"UNISDR draft strategy to support the Bali Action Plan",
            "url":"https:\/\/www.preventionweb.net\/files\/5526_ISDRstrategysupportBaliActionPlanprocess.pdf"
         }
      ],
      ...
   }
]
```

## Event 

## Training

## Documents and publications 

## Educational material 




## Response Headers

* X-Total-Records integer
* X-IsCached 
