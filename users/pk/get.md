# Gets a specific user
Returns a specific user from the API.

**URL**: `/v3/users/:pk`

**Method**: `GET`

**Parameters**: None

## Request example
```bash
curl --request GET \
  --url 'https://api.eloomi.com/v3/users/:pk' \
  --header 'Content-Type: application/json' \
  --header 'ClientId: <your_client_id>' \
  --header 'Authorization: Bearer <your_bearer_token>'
```

## Success Response
**Code**: `200 OK`

**Content-Type**: `application/json`

```json
{
    "status": "OK",
    "status_code": 200,
    "message": null,
    "extended_message": "Showing user details.",
    "data": {
        "id": 1,
        "first_name": "eloomi",
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
