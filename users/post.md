# Creates a user
Creates the specified user and returns the user

**URL**: `/v3/users`

**Method**: `POST`

**Parameters**

| Name | In | Type | Required | Details |
| --- | --- | --- | --- | --- |
| first_name | Body | String | No |  |
| last_name | Body | String  | No | |
| employee_id | Body | String  | No | Employee ID property field. **OBS: Not the same as `:pk`** |
| start_of_employment_at | Body | String  | No | (Format: "yyyy-mm-dd hh:mm:ss") |
| end_of_employment_at | Body | String  | No | (Format: "yyyy-mm-dd hh:mm:ss")	 |
| email | Body | String  | Yes |  |
| username | Body | String  | No | Alternative for email so the user can log in with username and not email. |
| personal_email | Body | String  | No | Secondary email |
| activate | Body | Boolean  | No | Set the value to 1 or true, to activate the user. Set the value to 0 or false, to deactivate the user.	 |
| gender | Body | String  | No | (Format: "M"/"F") |
| birthday | Body | String  | No | (Format: "yyyy-mm-dd") |
| language_code | Body | String  | No | (Format: "en"/"da") |
| language_iso | Body | String  | No | Any valid language ISO supported by eloomi (Format: "US"/"DK") |
| title | Body | String  | No |  |
| phone | Body | String  | No |  |
| generic_role | Body | String  | No | User Property field, grants no functionality |
| initials | Body | String  | No | User Property field, grants no functionality |
| legal | Body | String  | No | User Property field, grants no functionality |
| level | Body | String  | No | User Property field, grants no functionality |
| country | Body | String  | No | User Property field, grants no functionality |
| location | Body | String  | No | User Property field, grants no functionality |
| department_code | Body | String[]  | No | Array of `code's` for the departments that the user should join (should not be used with department_id) |
| department_id | Body | Integer[]  | No | Array of `id's` for the departments the user should join (should not be used with department_code) |
| user_permission | Body | String  | No | The permissions of the user (Format: `user`/`company adm.`) - Default: `user` |
| direct_manager_ids | Body | Integer[] | No | Array of `id's` of the direct managers that the user should have. **OBS: This syncs direct managers.** |
| add_direct_manager_ids | Body | Integer[] | No | Array of `id's` of the direct managers that the user should have. **OBS: This appends direct managers.** |
| direct_manager_employee_ids | Body | Mixed[] | No | Array of `employee_id's` of the direct managers that the user should have. **OBS: This syncs direct managers.** |
| add_direct_manager_employee_ids | Body | Mixed[] | No | Array of `employee_id's` of the direct managers that the user should have. **OBS: This appends direct managers.** |

## Request example
```bash
curl --request POST \
  --url 'https://api.eloomi.com/v3/users' \
  --header 'Content-Type: application/json' \
  --header 'ClientId: <your_client_id>' \
  --header 'Authorization: Bearer <your_bearer_token>' \
  --data '{
          	"first_name": "API Testing",
          	"email": "api_test@eloomi.com"
          }'
```

## Success Response
**Code**: `200 OK`

**Content-Type**: `application/json`

```json
{
    "status": "OK",
    "status_code": 200,
    "message": null,
    "extended_message": "The user was created.",
    "data": {
        "id": 168,
        "first_name": "API Testing",
        "last_name": "",
        "employee_id": null,
        "email": "api_test@eloomi.com",
        "username": null,
        "activated_at": null,
        "gender": null,
        "birthday": null,
        "department_id": null,
        "user_permission": "user",
        "start_of_employment_at": null,
        "end_of_employment_at": null,
        "personal_email": null,
        "title": null,
        "phone": null,
        "mobile_phone": null,
        "language": "en",
        "access_groups": [
            {
                "id": 3,
                "name": "user"
            }
        ],
        "country": null,
        "location": null,
        "legal": null,
        "level": null,
        "initials": null,
        "sub_company": null,
        "skill_level": null,
        "salary_id": null,
        "team_id": null,
        "direct_manager_ids": null,
        "custom_attributes": {
            "test_attribute": null
        }
    }
}
```

## Failure Response
This failure response occurs when an email is not provided

**Code**: `400 Bad Request`

**Content-Type**: `application/json`
```json 
{
    "status": "Bad Request",
    "status_code": 400,
    "message": "Something went wrong during the user creation. Please try again.",
    "extended_message": "Undefined index: email"
}
```

---

This failure response occurs when an email already exists

**Code**: `400 Bad Request`

**Content-Type**: `application/json`
```json 
{
    "status": "Bad Request",
    "status_code": 400,
    "message": "Something went wrong during the user creation. Please try again.",
    "extended_message": "User with the email [api_test@eloomi.com] already exists."
}
```
