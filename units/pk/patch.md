# Updates a specific unit (department)
Updates the specified unit and returns the unit with the new data

**URL**: `/v3/units/:pk`

**Method**: `PATCH`

**Parameters**

| Name | In | Type | Required | Details |
| --- | --- | --- | --- | --- |
| name | Body | String | No | Unit Property field |
| code| Body | String  | No | Unit identifier |
| parent_id | Body | Integer| No | `:pk` of the parent department. Used to build hierarchies. |
| parent_code | Body | String  | No | `code` of the parent department. Used to build hierarchies. |
| leader_email | Body | String[]  | No | Array of `emails` of users that should be department managers |
| leader_employee_id | Body | Mixed[] | No | Array of `employee_ids` of users that should be department managers |
| leaders_employee_id | Body | Mixed[] | No | Array of `employee_ids` of users that should be department managers |
| leaders_employee_ids | Body | Mixed[] | No | Array of `employee_ids` of users that should be department managers |
| leaders | Body | Integer[] | No | Array of `:pk` of users that should be department managers |
| leader_ids | Body | Integer[] | No | Array of `:pk` of users that should be department managers |
| user_emails | Body | String\|String[] | No | Array of `emails` or comma-separated list of emails of users that should be assigned to this unit |
| user_ids | Body | Integer[] | No | Array of `:pk` of users that should be assigned to this unit |
| users | Body | Integer[] | No | Array of `:pk` of users that should be assigned to this unit |
| remove_user_ids | Body | Integer[] | No | Array of `:pk` of users that should be removed from this unit |
| add_user_ids | Body | Integer[] | No | Array of `:pk` of users that should be assigned to this unit |
| access_groups | Body | Integer[] | No | Array of `id's` of the access groups that should be added to this unit |

## Request example
```bash
curl --request PATCH \
  --url 'https://api.eloomi.com/v3/units/:pk' \
  --header 'Content-Type: application/json' \
  --header 'ClientId: <your_client_id>' \
  --header 'Authorization: Bearer <your_bearer_token>' \
  --data '{
            "code": "api_test_code",
            "parent_id": 353
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
    "extended_message": "Unit was updated.",
    "data": {
        "id": 354,
        "name": "API Test Department",
        "code": "api_test_code",
        "parent_id": 353,
        "users": [],
        "leaders": [],
        "access_groups": []
    }
}
```

## Error Responses
This failure response occurs when providing a non-existing `:pk` for the request

**Code**: `204 No Content`

**Content-Type**: `application/json`

```json
{
    "status": "Bad Request",
    "status_code": 400,
    "message": "Could not update the unit, try again.",
    "extended_message": "Unit not found"
}
```