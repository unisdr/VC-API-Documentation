# Drupal 8 API Integration Documentation

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/

## Official Sendai Framework and National Platform focal point

This endpoint will retrieve the Official Sendai Framework and National Platform focal point managed through our intranet.

### Resources
* Wireframe URL: https://ijjqd4.axshare.com/#g=1&p=region__americas___carribean_-_countries

### Authentication:

It will be better if we can use oAuth2 client credentials otherwise basic auth?

* tbd

### Header Parameters:

* tbd

### URL: /sso-unisdr/api/drupal/get/undrr_focalpoints

```shell
GET /sso-unisdr/api/drupal/get/undrr_focalpoints
```

### JSON Response

```shell
{
   "status":200,
   "success":true,
   "total":189,
   "data":[
      {
         "ctry_id":61,
         "ctry_title":"Finland",
         "ctry_iso3_code":"FIN",
         "fp_type":"Sendai FW (official)",
         "org_id":2442,
         "org_title_acronym":"",
         "org_title_long":"Ministry of the Interior (Finland)",
         "org_url":"http:\/\/www.intermin.fi\/intermin\/home.nsf\/pages\/index_eng",
         "phone1":"",
         "pw_country_url":"https:\/\/www.preventionweb.net\/english\/countries\/europe\/fin"
      },
      {
         "ctry_id":266,
         "ctry_title":"Montenegro",
         "ctry_iso3_code":"MNE",
         "fp_type":"NP (official)",
         "org_id":12222,
         "org_title_acronym":"",
         "org_title_long":"Ministry of Interior - Directorate for Emergency Situations",
         "org_url":"http:\/\/www.mup.gov.me",
         "phone1":"",
         "pw_country_url":"https:\/\/www.preventionweb.net\/english\/countries\/europe\/mne"
      },
	  .....
   ]
}
```

### Field definition

| Field             	| Description                    	| Type/Value                                                      	|
|-------------------	|--------------------------------	|-----------------------------------------------------------------	|
| ctry_id           	| Country ID                     	| int                                                             	|
| ctry_title        	| Country name                   	| plain text                                                      	|
| ctry_iso3_code    	| ISO3 code                      	| plain text                                                      	|
| fp_type           	| Focal point type               	| plain text; possible values: Sendai FW (official), NP (official) 	|
| org_id            	| Organization ID                	| int                                                             	|
| org_title_long    	| Organization name              	| plain text                                                      	|
| org_title_acronym 	| Organization acronym           	| plain text                                                      	|
| org_url           	| Organization website URL       	| plain text                                                      	|
| phone1            	| Organization phone 1           	| plain text                                                      	|
| pw_country_url    	| PreventionWeb country page URL 	| plain text                                                      	|


## Regions and Countries

### Resources
* Wireframe URL: xxx

## Organizations

### Resources
* Wireframe URL: xxx
