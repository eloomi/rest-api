# Shows all users
Lists all users in the platform that are not deleted.

**URL**: `/v3/users`

**Method**: `GET`

**Parameters**

| Name | In | Type | Required | Details |
| --- | --- | --- | --- | --- |
| per_page | Query | Integer (Default: `25`) | No | Paginates the result by value provided |
| mode | Query | String (Options: `all`, `pending`, `active`, `inactive`) (Default: `all`) | No | Filters result on user-status |

## Success Response
**Code**: `200 OK`

**Content-Type**: `application/json`

**Content**
```json
 {
     "status": "OK",
     "status_code": 200,
     "message": null,
     "extended_message": "Showing all users.",
     "data": [
         {
             "id": 40,
             "first_name": "5642",
             "last_name": "mini",
             "employee_id": null,
             "email": "5642@eloomi.com",
             "username": "5642",
             "activated_at": null,
             "gender": null,
             "birthday": null,
             "department_id": [
                 9,
                 341
             ],
             "user_permission": "user",
             "start_of_employment_at": null,
             "end_of_employment_at": null,
             "personal_email": null,
             "title": "",
             "phone": "",
             "mobile_phone": null,
             "language": "sv",
             "access_groups": [
                 {
                     "id": 3,
                     "name": "user"
                 },
                 {
                     "id": 5,
                     "name": "All access"
                 }
             ],
             "country": "",
             "location": "",
             "legal": "",
             "level": 0,
             "initials": "",
             "sub_company": null,
             "skill_level": null,
             "salary_id": null,
             "team_id": [
                 6,
                 12,
                 13
             ],
             "direct_manager_ids": null,
             "custom_attributes": {
                 "test_attribute": null
             }
         },
         {
             "id": 37,
             "first_name": "ApprovalTest",
             "last_name": "ApprovalTest",
             "employee_id": null,
             "email": "ApprovalTest@eloomi.com",
             "username": "ApprovalTest",
             "activated_at": null,
             "gender": null,
             "birthday": null,
             "department_id": [
                 9,
                 28,
                 343
             ],
             "user_permission": "user",
             "start_of_employment_at": null,
             "end_of_employment_at": "2018-05-01 09:04:34",
             "personal_email": null,
             "title": "",
             "phone": "",
             "mobile_phone": null,
             "language": "en",
             "access_groups": [
                 {
                     "id": 3,
                     "name": "user"
                 }
             ],
             "country": "",
             "location": "",
             "legal": "",
             "level": 0,
             "initials": "",
             "sub_company": null,
             "skill_level": null,
             "salary_id": null,
             "team_id": [
                 6
             ],
             "direct_manager_ids": [
                 1
             ],
             "custom_attributes": {
                 "test_attribute": null
             }
         }
      ]
 }
 ```