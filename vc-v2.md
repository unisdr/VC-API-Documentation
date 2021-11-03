# Content Type / Content / Rosources

## Organizations

Published organizations in PreventionWeb.

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Query String Parameter:

* page integer (optional), page number (default value is 1)
* per_page integer (optional), number of records per page (200 is the default and maximum value)
* modified_since date format yyyy-mm-dd (optional), this condition will filter result equal or beyond given date correct format is yyyy-mm-dd

### URL: /sso-unisdr/api/integration/pw/organizations

* /sso-unisdr/api/integration/pw/organizations?page=2
* /sso-unisdr/api/integration/pw/organizations?modified_since=2021-10-21

### JSON Response

```shell
{
  "current_page": 1,
  "data": [
    {
      "uuid": "71a98cb5-6856-4667-b069-490aa0c4f068",
      "nid": 67701,
      "title": "The Crisis Lookout Coalition",
      "acronym": null,
      "langcode": "en",
      "changed": 1635853114,
      "created": 1635853081,
      "published_at": 1635853081,
      "url": "https:\/\/www.preventionweb.net\/organization\/crisis-lookout-coalition",
      "country_id": 288,
      "organization_type_id": "governments",
      "org_id": null,
      "mission": "<p>The Crisis Lookout Coalition is working towards a radical shift in how the world responds to risk and reacts to disasters.<\/p>\r\n\r\n ... and protect lives.<\/p>"
    },
    {
      "uuid": "3af7e28e-e144-472b-90bf-1d6fe92eee5e",
      "nid": 67651,
      "title": " Regional Environmental Change (Springer)",
      "acronym": null,
      "langcode": "en",
      "changed": 1635512658,
      "created": 1635512631,
      "published_at": 1635512631,
      "url": "https:\/\/www.preventionweb.net\/organization\/regional-environmental-change-springer",
      "country_id": null,
      "organization_type_id": "academicscientific",
      "org_id": null,
      "mission": "<p>Regional Environmental Change aims to publish research on interactions between human and natural systems at ... multidisciplinary perspective.<\/p>"
    },
    {
      "uuid": "9f5330db-2232-4b1d-b842-67be620ce97b",
      "nid": 503,
      "title": "United States Agency for International Development",
      "acronym": "USAID",
      "langcode": "en",
      "changed": 1634889407,
      "created": 1188500727,
      "published_at": 1188500727,
      "url": "https:\/\/www.preventionweb.net\/organization\/united-states-agency-international-development",
      "country_id": 289,
      "organization_type_id": "governments",
      "org_id": 612,
      "mission": "<p>An independent federal government agency that receives overall foreign policy guidance from the Secretary ... democracy, conflict prevention and humanitarian assistance.<\/p>"
    }
    ...
  ],
  "first_page_url": "https:\/\/program.unisdr.org\/sso-unisdr-development\/api\/integration\/pw\/organizations?page=1",
  "from": 1,
  "last_page": 1,
  "last_page_url": "https:\/\/program.unisdr.org\/sso-unisdr-development\/api\/integration\/pw\/organizations?page=1",
  "next_page_url": null,
  "path": "https:\/\/program.unisdr.org\/sso-unisdr-development\/api\/integration\/pw\/organizations",
  "per_page": 200,
  "prev_page_url": null,
  "to": 14,
  "total": 14,
  "status": 200,
  "success": 1
}
```
