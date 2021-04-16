# API Documentation for PreventionWeb Content Migration to Drupal

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/


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
