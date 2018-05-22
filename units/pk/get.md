# Gets a specific unit (department)
Returns a specific units from the API.

**URL**: `/v3/units/:pk`

**Method**: `GET`

**Parameters**: None

## Request example
```bash
curl --request GET \
  --url 'https://api.eloomi.com/v3/units/:pk' \
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
    "extended_message": "Showing the unit.",
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
## Failure Response
This failure response occurs when providing a non-existing `:pk` for the request

**Code**: `204 No Content`

**Content-Type**: `application/json`
