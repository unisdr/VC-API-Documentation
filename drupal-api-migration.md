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

## Large image/thumbnail image use by entry

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
      "org_type_id":1
   },
   ...
]
```



## Vacancies (Jobs) content type

### IMPORTANT: Pending the approach to migrate author

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










## UNDRR Publications (for migration)

## UNDRR News and PW News

## Event / Training

## Terminology

## Documents and publications 

## Educational material 

## UN Resolutions and Reports
