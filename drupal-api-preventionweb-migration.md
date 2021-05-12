# API Documentation for PreventionWeb Content Migration to Drupal

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/


## Generic querystring parameters

* page		integer, default 1
* per_page 	integer, default 200, max value allowed 1000, number of items per page


## Generic authentication and header

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"





## Users and subscriptions migration

### Todos:

* Email cleanup on-going using online tool (Olivier)
* Expose RSS endpoint for mailchimp integration (Chris)


### Resources:

* Content mapping: https://docs.google.com/spreadsheets/d/1cLJAFyYSs8LZUrDKtRgGOLombwA4wKBB8tfSWPvI2Tc/edit#gid=397479902


### URL: /sso-unisdr/api/preventionweb/migration/users

```shell
GET /sso-unisdr/api/preventionweb/migration/users
```

### JSON Response

```shell
[
    {
      "con_id": 36408,
      "con_fname": "Leo",
      "con_lname": "Gipo",
      "con_dateadded": "2009-10-07 09:49:45",
      "con_datemodified": "2009-10-07 09:58:23",
      "con_email": "email@marga.tech",
      "con_org": "ITC",
      "con_position": "Gamer",
      "field_first_name": "Leo",
      "field_last_name": "Gipo",
      "field_organization": "ITC",
      "field_position": "Gamer",
      "field_salutation": null,
      "field_telephone": "+0",
      "field_other_phone": "+0",
      "field_fax": null,
      "srv_opt": "2,8,5*1,5*3,10,13",
      "field_domain_access": "www_preventionweb_net",
      "subscription": [
        "Children resources - Monthly",
        "Community - Weekly",
        "News and blogs - Weekly",
        "Publications, policies and plans - Weekly"
      ]
    },
    ...
]
```

## National Platform

### Business Rules:

* All published national platform on PW 

### Resources:

* Current URL: https://www.preventionweb.net/english/hyogo/national/list/


### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### URL: /sso-unisdr/api/preventionweb/migration/national_platform

```shell
GET /sso-unisdr/api/preventionweb/migration/national_platform
```

### JSON Response

```shell
[
    {
      "np_id": 75,
      "field_title": "Armenia National Platform",
      "field_country": {
        "ctry_id": 8,
        "ctry_iso3_code": "ARM"
      },
      "field_region": {
        "cont_id": 3
      },
      "field_organization": {
        "org_id": 25249,
        "org_title_long": "Ministry of Emergency Situations of the Republic of Armenia",
        "org_title_acronym": ""
      },
      "domain": "www_preventionweb_net",
      "field_body": "<p><strong>History<\/strong><\/p>\r\n\r\n<p>As a result of joint efforts by the Ministry of Emergency Situations of Armenia, UN agencies (UNDRR, UNDP) and other DRR interested partners, the Government of Armenia adopted in December 2010 a decision on the formation of &quot;ARNAP&quot; (DRR National Platform) Foundation. Being a non-governmental organization, the Platform provides opportunities for state, non-governmental, private and international institutions to participate in decision-making and consultation processes. At the same time, it provides opportunities for organizing and controlling day-to-day operational activities, implementing long-term projects; it also provides necessary flexibility to respond to new challenges.<\/p>\r\n\r\n<p><strong>Structure<\/strong><\/p>\r\n\r\n<p>The main players of the National Platform are governmental authorities of Armenia, Ministry of Emergency Situations, and international and donor organizations working in the field of DRR, UN, Armenian Red Cross society, Save the Children, OxYGen Foundation, Caritas Armenia, World Vision Armenia as well as scientific institutions, civil societies and experts.<\/p><p>Establishment and development of innovative community-based youth resource centres<\/p>\r\n\r\n<p style=\"margin-left:35.7pt;\">&nbsp;<\/p>",
      "current_url": [
        {
          "id": "1818000081",
          "url": "https:\/\/www.preventionweb.net\/english\/hyogo\/national\/list\/v.php?id=8"
        }
      ],
      "field_website_url": ""
]
```


## Publications: Policy and Plans migration from PW Policy and Plans

### Business Rules:

* All published PW Policy and Plans marked for migration https://unitednations.sharepoint.com/:x:/r/sites/UNDRRDrupalPlatform/_layouts/15/Doc.aspx?sourcedoc=%7B7E9BDB40-DCFF-4B69-B8D0-90D50A69976E%7D&file=migration%20rules.xlsx&action=default&mobileredirect=true (Policies and plans TAB)


### URL: /sso-unisdr/api/preventionweb/migration/policy_plans

```shell
GET /sso-unisdr/api/preventionweb/migration/policy_plans
```

### JSON Response

```shell
[
    {
      "ent_id": 7351,
      "ent_sec_id": 9,
      "ent_dateadded": "2008-11-19 13:31:29",
      "ent_datemodified": "2008-11-19 19:16:22",
      "ent_datepublished": "2008-11-19 16:12:08",
      "pol_type": 1,
      "pol_subtype": 2,
      "field_user_comments": "",
      "field_editors_comments": "",
      "author_name": "LeoJ ETAG",
      "field_title": "Disaster risk reduction national coordinating mechanisms in Jordan (2008)",
      "field_body": "<p>This presentation was given at the Workshop on National Platforms at the International Disaster and Risk Conference (IDRC) in Davos, Switzerland, in August of 2008.  This NP presentation includes information regarding: Context of Disaster Risk Reduction (DRR) in Jordan, Legal Framework for DRR and DRR National Plan, DRR in Sectoral Policies, National Preventive Disaster Risk Reduction Mechanisms, National Crisis Management  Mechanisms, Institutional Actors and Stakeholders, Institutional DRR Actors and Stakeholders, DRR Institutional Relation to Climate Change, Regional Coordination of DRR and South-South Collaboration, and more.<\/p>",
      "field_year_of_publication": 2008,
      "field_authors": "",
      "field_policy_type": "National policy and plans",
      "field_country": [
        {
          "ctry_id": 88,
          "ctry_iso3_code": "JOR"
        }
      ],
      "field_organization": [
        {
          "org_id": 3487,
          "org_title_long": "Jordan - government",
          "org_title_acronym": ""
        }
      ],
      "field_region": [
        {
          "cont_id": 4
        }
      ],
      "field_hazards": [],
      "field_themes": [
        {
          "scat_id": 104
        }
      ],
      "field_related_links": [],
      "field_links": [
        {
          "id": 6226,
          "label": "View full presentation",
          "lng_id": 1,
          "url": "https:\/\/www.preventionweb.net\/files\/7351_JordanNPPresentation.ppt"
        }
      ],
      "domain": "www_preventionweb_net",
      "current_url": [
        {
          "id": "9073511",
          "ent_id": 7351,
          "url": "https:\/\/www.preventionweb.net\/english\/professional\/policies\/v.php?id=7351"
        }
      ]
    },
    ...
]
```




## Resources: Academic Programs

### Business Rules:

* All published academic programmes but some fields are aggregated to body field https://unitednations.sharepoint.com/:x:/r/sites/UNDRRDrupalPlatform/_layouts/15/Doc.aspx?sourcedoc=%7B7E9BDB40-DCFF-4B69-B8D0-90D50A69976E%7D&file=migration%20rules.xlsx&action=default&mobileredirect=true (Academic Programme TAB)

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


### URL: /sso-unisdr/api/preventionweb/migration/acad_programs

```shell
GET /sso-unisdr/api/preventionweb/migration/acad_programs
```

### JSON Response

```shell
[
    {
      "ent_id": 749,
      "ent_sec_id": 13,
      "ent_dateadded": "2007-10-04 09:52:26",
      "ent_datemodified": "2007-10-17 17:40:47",
      "ent_datepublished": "0000-00-00 00:00:00",
      "field_user_comments": "",
      "field_editors_comments": null,
      "author_name": "Leoj ETAG",
      "field_title": "Disaster Management and Sustainable Development",
      "field_resource_type": "Academic programme",
      "acad_type_id": 1,
      "field_academic_programme_type": "University programme",
      "acad_level_id": 2,
      "field_academic_programme_level": "Masters",
      "field_academic_programme_duration": "Up to 1 year.",
      "field_website_url": "http:\/\/northumbria.ac.uk\/?view=CourseDetail&code=DTFDMS6",
      "acad_freq_id": 1,
      "field_body": "<h2>Location<\/h2><p>Newcastle<\/p><h2>Degree<\/h2><p>MSc<\/p><h2>Description<\/h2><p>The program aims to introduce the students with issues of personal security and security planning and development issues. To enhance the learning experience students are provided with a field-based experience on matters such as microbiological water testing and remediation of earthquake-damaged structures. The program focuses on emergency planning procedures and of the role of the key agencies which work together in the event of national or international disasters such as floods, earthquakes, terrorist attacks and major accidents.<\/p><h2>Themes<\/h2><p>Disaster management, Sustainable development, Emergency management, Disaster risk reduction, Climate change risk.<\/p><h2>Target audience<\/h2><p>The program attract both aspiring Managers in the field of Disaster and professionals having good experience of working on emergency, disaster and risk reduction issues & who want to enhance hone enhance their knowledge level or hone their skills.<\/p><h2>Admission requirement<\/h2><p>A second class honours degree in an appropriate subject (i.e. geography, environmental management\/studies, economics, and sociology) or appropriate professional experience and\/or qualifications.<\/p><h2>Frequency<\/h2><p>Annual<\/p><h2>Language<\/h2><p>English<\/p><h2>Application procedure<\/h2><p>Students can apply online or call the help desk +44 191 227 4453 to obtain application form or to know more about the course.<\/p><h2>Tuition and cost<\/h2><p>3070.00 £ per year for home students. For further details please see <a href=\"http:\/\/northumbria.ac.uk\/brochure\/studfees\/?view=Standard\">programme brochure<\/a>.<\/p><h2>Deadline<\/h2><p>Please see university homepage.<\/p><h2>Contact<\/h2><p>School of Applied Sciences, Northumbria University<br \/>\nEllison Building, Newcastle City Campus<br \/>\nTel: (0191) 227 4453<br \/>\nFax: (0191) 227 4561<br \/>\nE-mail: et.admissions@northumbria.ac.uk<\/p>",
      "field_country": [
        {
          "ctry_id": 183,
          "ctry_iso3_code": "GBR"
        }
      ],
      "field_organization": [
        {
          "org_id": 1411,
          "org_title_long": "Disaster and Development Network",
          "org_title_acronym": "DDN"
        }
      ],
      "field_region": [
        {
          "cont_id": 3
        }
      ],
      "field_hazards": [],
      "field_themes": [
        {
          "scat_id": 33
        },
        {
          "scat_id": 36
        }
      ],
      "field_related_links": [],
      "field_links": [],
      "domain": "www_preventionweb_net",
      "current_url": [
        {
          "id": "13007491",
          "ent_id": 749,
          "url": "https:\/\/www.preventionweb.net\/academic\/view\/749"
        }
      ]
    },
    ...
]
```


## Vacancies (Jobs) content type


### Business Rules:

* All published vacancies except source UNDRR


### URL: /sso-unisdr/api/preventionweb/migration/vacancies

```shell
GET /sso-unisdr/api/preventionweb/migration/vacancies
```

### JSON Response

```shell
[
   {
      "ent_id":592,
      "field_title":"Disaster management delegate",
      "ent_dateadded":"2007-09-04 16:41:39",
      "ent_datemodified":"2007-09-19 12:30:56",
      "field_user_comments": "...",
      "field_editors_comments": "",
      "author_name": "Leo Etag",
      "ent_contact_name": "Leo Etag",
      "field_email": "email@email.com",
      "field_body":"<p><u>Background:<\/u><\/p>\n\n<p>lorem impsum<\/p>",
      "job_post_url":"https:\/\/doamin.com",
      "field_city_aditional_loc":"Tarija, Bolivia (TBC)",
      "field_closing_date":"2007-09-28",
      "domain": "www_preventionweb_net",
      "current_url": [
        {
          "id": "1543641",
          "ent_id": 592,
          "url": "https:\/\/www.preventionweb.net\/jobs\/view\/592"
        }
      ],
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
            "id":12345,
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


## Organizations

All published organizations. Resultset is cached for 3 minutes.

### Business Rules:

* All published organizations.


### URL: /sso-unisdr/api/preventionweb/migration/organizations

```shell
GET /sso-unisdr/api/preventionweb/migration/organizations
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
      "field_body": "<p>The UNDRR Regional Unit for the Americas and the Caribbean strives to provide support to actors throughout the region, including North America, Latin America and the Caribbean, in fostering a culture of disaster prevention and contributing to build disaster resilient nations and communities.<\/p>",
      "field_drr_activities": "<h4>Policies and Programmes in DRR<\/h4>\n\n<p>Implementation of the UNCCD and its ten-year Strategy is a demanding task that requires a broad range of actions and knowledge. Furthermore, desertification\/land degradation and drought are inherently linked with numerous other issues and related approaches. Recognising these inter-linkages tends to generate significant benefits, from local to global level.<br \/>\nAmong the key topics in effective fostering the implementation of the UNCCD and its ten-year Strategy are the following:<\/p>\n\n<p><strong>Science<\/strong><br \/>\nScientific collaboration around agreed themes and support to impact monitoring.<\/p>\n\n<p><strong>Reporting review and assessment<\/strong><br \/>\nReporting under the UNCCD, including the performance review and assessment of implementation system (PRAIS) as well as best practices.<\/p>\n\n<p><strong>Awareness Raising<\/strong><br \/>\nActive influencing of relevant international, national and local processes and actors to address desertification\/land degradation and drought.<\/p>\n\n<p><strong>Thematic priorities<\/strong><br \/>\nIdentifying and taking action on inter-linkages between desertification, land degradation and drought and selected key themes: biodiversity, climate change, food security, forests, gender and water.<\/p>\n\n<p><strong>Synergies among the Rio Conventions<\/strong><br \/>\nJoint activities by the secretariats of the three &ldquo;sister Conventions&rdquo; on biodiversity, climate change and desertification, land degradation and drought.<\/p>\n\n<p><strong>Capacity building<\/strong><br \/>\nOnline tools and information on capacity building.<\/p>\n\n<div class=\"separator-line thin\"><\/div>\n\n<h4>National Counterpart<\/h4>\n\n<p>The Hyogo Office focuses on key elements of self-help, cooperation, and education through activities such as:<\/p>\n\n<p>• Research projects;<br \/>\n• Training and capacity-building;<br \/>\n• A series of international workshops;<br \/>\n• Advisory services;<br \/>\n• Research projects with specific focus on implementation and field experiences;<br \/>\n• Dissemination of best practices through workshops, publications, reports and internet homepage;<br \/>\n• Training and capacity-building in different communities;<br \/>\n• Advisory services to the vulnerable communities before and after the disasters, and networking of communities.<\/p>\n\n<div class=\"separator-line thin\"><\/div>\n\n<h4>Disaster Reduction Focal Point(s)<\/h4>\n\n<p>Mr. Sergio A. Zelaya-Bonilla, Special Adviser to the Executive Secretary, UNCCD Secretariat, Phone: +49-228 815-2825, Fax: +49-228 815-2898\/99<\/p>\n\n<p>Ms. Annette Victoria Gütgemann, External Relations, Policy and Advocacy Unit, UNCCD Secretariat, E-Mail aguetgemann@unccd.int, Phone: +49-228 815 2809, Fax: +49-228 815 2898\/99<\/p>\n\n<div class=\"separator-line thin\"><\/div>\n\n<h4>Websites<\/h4>\n\n<p>http:\/\/www.unccd.int<br \/>\nhttp:\/\/www.unccd.int\/en\/about-the-convention\/The-Secretariat\/The-Executive-Secretary\/Pages\/default.aspx<\/p>",
      "org_type_id":1,
      "org_type_title":"UN & International Organizations",
      "current_url": [
        {
          "id": "1717100003",
          "org_id": 3,
          "url": "https:\/\/www.preventionweb.net\/organizations\/3\/view"
        }
      ]
   },
   ...
]
```




## Blogs

All published blogs. Resultset is cached for 3 minutes.

### Resources:

* Content mapping: https://docs.google.com/spreadsheets/d/1cLJAFyYSs8LZUrDKtRgGOLombwA4wKBB8tfSWPvI2Tc/edit#gid=561059434

### URL: /sso-unisdr/api/preventionweb/migration/blogs

```shell
GET /sso-unisdr/api/preventionweb/migration/blogs
```

### JSON Response

```shell
[
    {
      "ent_id": 44959,
      "ent_sec_id": 589,
      "ent_dateadded": "0000-00-00 00:00:00",
      "ent_datemodified": "2017-05-03 17:49:08",
      "ent_datepublished": "2015-06-25 00:00:00",
      "field_user_comments": "",
      "field_editors_comments": "",
      "author_name": "",
      "ent_contact_name": "",
      "field_email": "",
      "field_title": "How can the world better prepare for natural disasters?",
      "field_body": "<p>It is no longer business as usual. From major global businesses to SMEs to small local producers, economic losses from disasters are a growing threat to business continuity and sustainability. The news last week that the share price of a small Irish insurance company dropped 12% on the Dublin Stock Exchange did not grab any major headlines. However, the fact that its financial losses for 2014 were triggered in part by record claims for winter storm damage is an indication of how businesses across the world are feeling the impact of disaster risk, amplified by climate change.<\/p>\r\n\r\n<p>The accumulation of such small announcements is just as significant as a major disaster event like the floods in northern Thailand in 2011 that did serious damage to the car industry as global supply chains, dependent on manufacturing plants located on flood plains, were severely disrupted. GDP in Thailand fell by 9% in the last three months of 2011 compared with the same quarter in 2010. GDP also fell in Japan in 2011 after the Great East Japan Earthquake and Tsunami, which generated direct losses of over $200 billion.<\/p>\r\n\r\n<p><em>Margareta Wahlström was the UN Special Representative of the Secretary-General for Disaster Risk Reduction from 2008 until 2016. She has extensive experience in both disaster relief operations and disaster risk management, with the United Nations system and the International Federation of Red Cross and Red Crescent Societies. Her broad experience spans conflict and non-conflict emergencies, and addressing long-term issues of sustainable development. She was also the head of UNISDR, the United Nations Office for Disaster Risk Reduction, the focal point in the United Nations system for the coordination of disaster risk reduction.<\/em><\/p>",
      "field_publication_date": "2015-06-25 00:00:00",
      "field_blog_type": "Blog",
      "field_image_id": "",
      "domain": "www_preventionweb_net",
      "field_authors": "Margareta Wahlström, Deputy Emergency Relief Coordinator, Swedish Red Cross",
      "field_country": [],
      "field_organization": [],
      "field_region": [],
      "field_hazards": [],
      "field_themes": [
        {
          "scat_id": 42
        },
        {
          "scat_id": 653
        }
      ],
      "field_related_links": [
        {
          "id": 27000,
          "label": "‘Sustainability Starts in Sendai,’ Secretary-General Says of Japan Summit on Disaster Risk Reduction, at Launch of Assessment Report",
          "url": "http:\/\/www.un.org\/press\/en\/2015\/sgsm16563.doc.htm"
        },
        {
          "id": 27001,
          "label": "The R!SE Initiative",
          "url": "http:\/\/www.pwc.com\/gx\/en\/governance-risk-compliance-consulting-services\/resilience\/publications\/rise.jhtml"
        }
      ],
      "field_links": [],
      "current_url": [
        {
          "id": "589449591",
          "ent_id": 44959,
          "url": "https:\/\/www.preventionweb.net\/experts\/oped\/view\/44959"
        }
      ]
    },
    ...
]
```


## Images

All primary image (thubnail or large) used by PW published entries except with source UNDRR. Resultset is cached for 3 minutes. No pagination set cause had to do post processing clearning each row.


### URL: /sso-unisdr/api/preventionweb/migration/images

```shell
GET /sso-unisdr/api/preventionweb/migration/images
```

### JSON Response

See: https://github.com/unisdr/VC-API-Documentation/blob/master/drupal-api-migration.md#json-response-6




## Event & Training

All PW published entries except with source UNDRR. Resultset is cached for 3 minutes. 


### URL: /sso-unisdr/api/preventionweb/migration/event_training

```shell
GET /sso-unisdr/api/preventionweb/migration/event_training
```

### JSON Response

See: https://github.com/unisdr/VC-API-Documentation/blob/master/drupal-api-migration.md#json-response-15


## News

All PW published news including tagged "pw:mizutorioped". Resultset is cached for 3 minutes.

### Migration from PW News

* News (URL: /sso-unisdr/api/preventionweb/migration/news)

```shell
GET /sso-unisdr/api/preventionweb/migration/news
```

### JSON Response

See: https://github.com/unisdr/VC-API-Documentation/blob/master/drupal-api-migration.md#json-response-12



## Publications: Documents and publications

All PW published entries except with source UNDRR mapped to information type "Documents and publications". Resultset is cached for 3 minutes.


### Migration from different content sources

* Documents and publications (URL: /sso-unisdr/api/preventionweb/migration/publications)
* Policy and plans (URL: /sso-unisdr/api/preventionweb/migration/publications_policy_import)
* Educational materials (URL: /sso-unisdr/api/preventionweb/migration/publications_edumat_import)
* Maps (URL: /sso-unisdr/api/preventionweb/migration/publications_maps_import)

```shell
GET /sso-unisdr/api/preventionweb/migration/publications
GET /sso-unisdr/api/preventionweb/migration/publications_policy_import
GET /sso-unisdr/api/preventionweb/migration/publications_edumat_import
GET /sso-unisdr/api/preventionweb/migration/publications_maps_import
```

### JSON Response

See: https://github.com/unisdr/VC-API-Documentation/blob/master/drupal-api-migration.md#json-response-15


## Collections

Migration source were from excel file.

### Resources:

* Content mapping: https://docs.google.com/spreadsheets/d/1cLJAFyYSs8LZUrDKtRgGOLombwA4wKBB8tfSWPvI2Tc/edit#gid=0

### Migration to specific collection type

* Resource Guides (URL: /sso-unisdr/api/preventionweb/migration/tags_migration_resource_guides)
* Disasters (URL: /sso-unisdr/api/preventionweb/migration/tags_migration_disasters)
* Words into Action (URL: /sso-unisdr/api/preventionweb/migration/tags_migration_words_into_action)
* Community Collection (URL: /sso-unisdr/api/preventionweb/migration/tags_migration_community_collections)

```shell
GET /sso-unisdr/api/preventionweb/migration/tags_migration_resource_guides
GET /sso-unisdr/api/preventionweb/migration/tags_migration_disasters
GET /sso-unisdr/api/preventionweb/migration/tags_migration_words_into_action
GET /sso-unisdr/api/preventionweb/migration/tags_migration_community_collections
```

### JSON Response

```shell
[
   {
      "id": "8f7282ca47ec176ac78f28329ad2ac76",
      "field_domain_access": "www_preventionweb_net",
      "field_collection_type": "Resource guides",
      "keep": "Yes",
      "field_title": "Asia-Pacific DRR Country Status Reports ",
      "open_tags": "pw:asiapacificreport",
      "field_type": "Topic guide",
      "field_body": "<p>The Disaster Risk Reduction Country Status Reports provide a snapshot of DRR progress and the   status of the implementation of the Sendai Framework for Disaster Risk   Reduction at the national level.<\/p>",
      "field_image": "https:\/\/www.undrr.org\/image\/asia-pacific-drr-country-status-reports",
      "current_url": [
        {
          "id": "19191000011",
          "url": "https:\/\/www.preventionweb.net\/collections\/asiapacific-profiles"
        }
      ],
      "field_related_entries": [
        "36379",
        "48991",
        "58098",
        "59753",
        "61585",
        "62176",
        "64116",
        "66304"
      ]
    },
    ...
]
```

## Syndication taxonomy: Country profile migration

The entries in field_related_entries must be assigned with "Syndication taxonomy: Country profile". This migration must be executed after completing the content migration. Dependent to Jira ticket https://umane.everis.com/jiraito/browse/WEBSITEMIG-1154, for the creation of new taxonomy in Drupal.

```shell
GET /sso-unisdr/api/preventionweb/migration/tags_migration_syndication_taxonomy
```

### JSON Response

```shell
[
    {
      "field_collection_type": "Syndication",
      "open_tags": "pw:countryprofile",
      "comment": "add to Syndication taxonomy \"Country profile\"",
      "field_related_entries": [
        "10552",
        "11145"
    }
]
```

## Resources: On Demand Training

Migration source from excel file.

```shell
GET /sso-unisdr/api/preventionweb/migration/resources_ondemandtraining
```

### JSON Response

```shell
[
    {
      "field_title": "Earthquake Seismology",
      "field_programme_url": "https:\/\/www.edx.org\/course\/earthquake-seismology-2",
      "organization": "Federica",
      "field_body": "<p>The course introduces the basic<br \/>\ntheories and experimental work focused on earthquake generation and seismic<br \/>\nwave propagation. It centers on methods and technologies used to image the<br \/>\nearthquake as well as real-time simulations and mapping.<\/p>",
      "field_academic_programme_duratio": "12 weeks",
      "tags_theme": "GIS & Mapping; Science and Technology",
      "tags_hazard": "Earthquake",
      "org_ids": "1442",
      "language": "English",
      "tags_theme": "GIS & Mapping; Science and Technology",
      "tags_hazard": "Earthquake",
      "field_theme": [
        {
          "scat_id": 105
        },
        {
          "scat_id": 761
        }
      ],
      "field_hazard": [
        {
          "scat_id": 60
        }
      ],
      "field_organization": [
        {
          "org_id": "1442"
        }
      ]
    },
    ...
]
```

## Entries Attachments

All attachments related to PW migration, including already migrated records during the base platform phase. (sec ids: 1, 2, 5, 8, 9, 10, 13, 83, 589). As agreed with Everis, same endpoint as base platform migration.
 
* Academic Programmes
* Documents & Publications
* DRR Voices Blog
* Educational materials
* Events Calendar (training and non-training)
* Jobs
* Maps
* News
* Policy, Plans & Statements


```shell
GET /sso-unisdr/api/drupal/migration/get_attachments
```

### JSON Response

See: https://github.com/unisdr/VC-API-Documentation/blob/master/drupal-api-migration.md#json-response-4


## Entries Related Links

All related links related to PW content migration, including already migrated records during the base platform phase. As agreed with Everis, same endpoint as base platform migration. See content types included above.

```shell
GET /sso-unisdr/api/drupal/migration/get_related_links
```

### JSON Response

See: https://github.com/unisdr/VC-API-Documentation/blob/master/drupal-api-migration.md#json-response-5



## Integration: Retrieve VC organitions with commitments

This will retrieve all the organizations that is linked to a voluntary commitment.

```shell
GET /sso-unisdr/api/integration/sfvc/get_organizations
```

### JSON Response

```shell
[
    {
      "id": "17161",
      "name": "Nigerian Women Agro Allied Farmers Association"
    },
    {
      "id": "10180",
      "name": "Agency for Humanitarian and Development Assistance for Afghanistan"
    },
    ...
]
```



## Publications: Educational materials

Migrate the content to Publications content type and document publications information type.

### URL: /sso-unisdr/api/preventionweb/migration/educational_materials

```shell
GET /sso-unisdr/api/preventionweb/migration/educational_materials
```

### JSON Response

```shell
[
    {
      "ent_status": 3,
      "ent_id": 3418,
      "ent_sec_id": 10,
      "field_title": "El popocatepetl",
      "ent_dateadded": "2008-08-22 17:04:14",
      "ent_datemodified": "2008-12-17 11:29:33",
      "ent_datepublished": "2008-12-17 11:29:33",
      "field_user_comments": "",
      "field_editors_comments": "[MP] added org 10Sept08\r\n[MCH]revised the link and published (17Dec08)",
      "field_body": "",
      "author_name": "Jane Doe",
      "ent_contact_name": "",
      "field_email": "",
      "field_target_audience": "",
      "field_authors": "",
      "field_isbn": "",
      "field_title_original": "",
      "field_number_page": "",
      "field_year_of_publication": 2008,
      "edu_language": "4",
      "edu_audience_group_id": 2,
      "edu_audience_subgroup_id": 0,
      "field_image_id": "",
      "domain": "www_preventionweb_net",
      "field_country": [
        {
          "ctry_id": 112,
          "ctry_iso3_code": "MEX"
        }
      ],
      "field_organization": [
        {
          "org_id": 3915,
          "org_title_long": "Kokone",
          "org_title_acronym": ""
        }
      ],
      "field_region": [
        {
          "cont_id": 2
        }
      ],
      "field_hazards": [
        {
          "scat_id": 72
        }
      ],
      "field_themes": [
        {
          "scat_id": 34
        },
        {
          "scat_id": 37
        }
      ],
      "field_related_links": [],
      "field_links": [],
      "current_url": [
        {
          "id": "10034181",
          "ent_id": 3418,
          "url": "https:\/\/www.preventionweb.net\/educational\/view\/3418"
        }
      ]
    },
    ...
]
```
