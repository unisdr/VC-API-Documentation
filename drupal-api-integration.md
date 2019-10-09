# Drupal 8 API Integtegration Documentation

Production URL: http://program.unisdr.org/sso-unisdr/

Staging URL: https://program.unisdr.org/sso-unisdr-development/

## Retrieve official Sendai Framework and National Platform focal point

Authentication (Basic Auth?):

* tbd

Header Parameters:

* tbd

URL: /sso-unisdr/api/drupal/get/undrr_focalpoints

```shell
GET /sso-unisdr/api/drupal/get/undrr_focalpoints
```

JSON Response

```shell
{
   "status":200,
   "success":true,
   "total":189,
   "data":[
      {
         "ctry_id":61,
         "country":"Finland",
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
         "country":"Montenegro",
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
