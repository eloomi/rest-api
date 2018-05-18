# Creates a unit (department)
Creates the specified unit and returns it.
Note that Units (Departments) are not unique by default, as multiple departments can have the same name and code.

**OBS:** If you need to single out a unit (department) to ensure only one exists, look at the `unique` parameter below!

**OBS:** Partial creation/update is enabled for Units (Departments), which means that supplying a related value for leaders or users will not result in an error, the value will just be ignored.

**URL**: `/v3/units`

**Method**: `POST`

**Parameters**

| Name | In | Type | Required | Details |
| --- | --- | --- | --- | --- |
| unique | Query | String | No| Defines which column is to be used for uniqueness |
| name | Body | String | Yes | Unit Property field |
| code| Body | String  | No | Unit identifier |
| parent_id | Body | Integer| No | `:pk` of the parent department. Used to build hierarchies. |
| parent_code | Body | String  | No | `code` of the parent department. Used to build hierarchies. |
| leader_email | Body | String[]  | No | Array of `emails` of users that should be department managers |
| leader_employee_id | Body | Mixed[] | No | Array of `employee_ids` of users that should be department managers |
| leaders_employee_id | Body | Mixe[] | No | Array of `employee_ids` of users that should be department managers |
| leaders_employee_ids | Body | Mixed[] | No | Array of `employee_ids` of users that should be department managers |
| leaders | Body | Integer[] | No | Array of `:pk` of users that should be department managers |
| leader_ids | Body | Integer[] | No | Array of `:pk` of users that should be department managers |
| user_emails | Body | String\|String[] | No | Array of `emails` or comma-separated list of emails of users that should be assigned to this unit |
| user_ids | Body | Integer[] | No | Array of `:pk` of users that should be assigned to this unit |
| users | Body | Integer[] | No | Array of `:pk` of users that should be assigned to this unit |
| remove_user_ids | Body | Integer[] | No | Array of `:pk` of users that should be removed from this unit |
| add_user_ids | Body | Integer[] | No | Array of `:pk` of users that should be assigned to this unit |

## Request example
```bash
curl --request POST \
  --url 'https://api.eloomi.com/v3/units?unique=name' \
  --header 'Content-Type: application/json' \
  --header 'ClientId: <your_client_id>' \
  --header 'Authorization: Bearer <your_bearer_token>' \
  --data '{
            "name": "API Test Department",
            "leaders": [1, 5],
            "users": [2,3]
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
    "extended_message": "New unit created.",
    "data": {
        "id": 352,
        "name": "API Test Department",
        "code": "api test department",
        "parent_id": null,
        "users": [],
        "leaders": [],
        "access_groups": []
    }
}
```

## Error Responses
This failure response occurs when a name is not supplied

**Code**: `400 Bad Request`

**Content-Type**: `application/json`
```json 
{
    "status": "Bad Request",
    "status_code": 400,
    "message": "Could not create the unit, try again.",
    "extended_message": "Unit name parameter is missed."
}
```

---

This failure response occurs when a unit defined by the `unique` parameter already exists

**Code**: `400 Bad Request`

**Content-Type**: `application/json`
```json 
{
    "status": "Bad Request",
    "status_code": 400,
    "message": "The unit already exists with the specified unique identifier [name:API Test Department]",
    "extended_message": "Unit already exists"
}
```
