# API Documentation for PreventionWeb Content Migration to Drupal

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/

## Generic querystring parameters

* page		integer, default 1
* per_page 	integer, default 200, max value allowed 1000, number of items per page


## Users and subscriptions migration

### Todos:

* Email cleanup on-going using online tool (Olivier)
* Expose RSS endpoint for mailchimp integration (Chris)

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### URL: /sso-unisdr/api/preventionweb/migration/users

```shell
GET /sso-unisdr/api/preventionweb/migration/users
```

### JSON Response

```shell
[
    {
      "con_id": 36317,
      "con_fname": "David",
      "con_lname": "Watson",
      "con_dateadded": "2010-11-24 23:27:09",
      "con_datemodified": "2010-11-24 23:27:09",
      "con_email": "david.watson@incom.com.au",
      "con_org": "Incom Risk Management",
      "con_position": null,
      "srv_opt": "",
      "subscription": []
    },
    {
      "con_id": 36408,
      "con_fname": "Cees",
      "con_lname": "Van Westen",
      "con_dateadded": "2009-10-07 09:49:45",
      "con_datemodified": "2009-10-07 09:58:23",
      "con_email": "westen@itc.nl",
      "con_org": "ITC",
      "con_position": "Associate Professor",
      "srv_opt": "2,8,5*1,5*3,10,13",
      "subscription": [
        "Children resources - Monthly",
        "Community - Weekly",
        "News and blogs - Weekly",
        "Publications, policies and plans - Weekly"
      ]
    },
```

## National Platform

### Business Rules:

* All published national platform on PW 

### Resources:

* Current URL: https://www.preventionweb.net/english/hyogo/national/list/
* 

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

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


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


### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


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


### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.


### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"


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