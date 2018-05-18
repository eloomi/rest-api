# Shows all units (departments)
Lists all units (departments) in eloomi

**URL**: `/v3/untis`

**Method**: `GET`

**Parameters**: None

## Request example
**Return a list of all units in the platform**
```bash
curl --request GET \
  --url 'https://api.eloomi.com/v3/units' \
  --header 'Content-Type: application/json' \
  --header 'ClientId: <your_client_id>' \
  --header 'Authorization: Bearer <your_bearer_token>'
```

## Success Response
**Code**: `200 OK`

**Content-Type**: `application/json`

**Content**
```json
{
    "status": "OK",
    "status_code": 200,
    "message": null,
    "extended_message": "Showing all units.",
    "data": [
        {
            "id": 6,
            "name": "Company",
            "code": null,
            "parent_id": null,
            "users": [
                7
            ],
            "leaders": [],
            "access_groups": []
        },
        {
            "id": 7,
            "name": "Copenhagen",
            "code": null,
            "parent_id": 6,
            "users": [
                88,
                89
            ],
            "leaders": [],
            "access_groups": []
        },
        {
            "id": 8,
            "name": "Singapore",
            "code": null,
            "parent_id": 6,
            "users": [],
            "leaders": [],
            "access_groups": []
        },
        {
            "id": 9,
            "name": "Dubai",
            "code": null,
            "parent_id": 6,
            "users": [
                11,
                12,
                37,
                40
            ],
            "leaders": [],
            "access_groups": []
        }
    ]
}
```