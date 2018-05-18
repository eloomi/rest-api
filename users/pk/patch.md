# Updates a specific user
Updates the specified user and returns the user with the new data

**URL**: `/v3/users/:pk`

**Method**: `PATCH`

**Parameters**

| Name | In | Type | Required | Details |
| --- | --- | --- | --- | --- |
| first_name | Body | String | No |  |
| last_name | Body | String  | No | |
| employee_id | Body | String  | No |  |
| start_of_employment_at | Body | String  | No | (Format: "yyyy-mm-dd hh:mm:ss") |
| end_of_employment_at | Body | String  | No | (Format: "yyyy-mm-dd hh:mm:ss")	 |
| email | Body | String  | No |  |
| personal_email | Body | String  | No | Secondary email |
| activate | Body | Boolean  | No | Set the value to 1 or true, to activate the user. Set the value to 0 or false, to deactivate the user.	 |
| gender | Body | String  | No | (Format: "M"/"F") |
| birthday | Body | String  | No | (Format: "yyyy-mm-dd") |
| language_code | Body | String  | No | (Format: "en"/"da") |
| title | Body | String  | No |  |
| phone | Body | String  | No |  |
| department_code | Body | String[]  | No | Array of `code's` for the departments that the user should join (should not be used with department_id) |
| department_id | Body | Integer[]  | No | Array of `id's` for the departments the user should join (should not be used with department_code) |
| user_permission | Body | String  | No | The permissions of the user (Format: `user`/`company adm.`) - Default: `user` |
| direct_manager_ids | Body | Integer[] | No | Array of `id's` of the direct managers that the user should have |
| direct_manager_employee_ids | Body | Mixed[] | No | Array of `employee_id's` of the direct managers that the user should have |


## Request example
```json
{
  "first_name": "API Testing"
}
```

## Success Response
**Code**: `200 OK`

**Content-Type**: `application/json`

```json
{
    "status": "OK",
    "status_code": 200,
    "message": null,
    "extended_message": "The user was updated.",
    "data": {
        "id": 1,
        "first_name": "API Testing",
        "last_name": "Admin",
        "employee_id": null,
        "email": "admin@eloomi.com",
        "username": null,
        "activated_at": null,
        "gender": "M",
        "birthday": "2017-01-01",
        "department_id": [],
        "user_permission": "user",
        "start_of_employment_at": "2017-07-01 09:30:11",
        "end_of_employment_at": null,
        "personal_email": null,
        "title": "Superadmin",
        "phone": "",
        "mobile_phone": null,
        "language": "en",
        "access_groups": [
            {
                "id": 2,
                "name": "admin"
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
        "team_id": [],
        "direct_manager_ids": null,
        "custom_attributes": {
            "test_attribute": null
        }
    }
}
```
## Failure Response
This failure response occurs when providing a non-existing `:pk` for the request

**Code**: `204 No Content`

**Content-Type**: `application/json`
