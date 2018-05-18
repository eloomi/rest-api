# Deletes a specific user
Returns a specific user from the API.

**URL**: `/v3/users/:pk`

**Method**: `DELETE`

**Parameters**: None

## Request example
```bash
curl --request DELETE \
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
    "message": "The user was deleted.",
    "extended_message": ""
}
```

## Failure Response
This failure response occurs when trying to delete an already deleted user.

**Code**: `204 No Content`

**Content-Type**: `application/json`
```json
{
    "status": "No Content",
    "status_code": 204,
    "message": "No user found with that id",
    "extended_message": ""
}
```

---

This failure response occurs when something during deletion goes wrong.

**Code**: `400 Bad Request`

**Content-Type**: `application/json`
```json
{
    "status": "Bad Request",
    "status_code": 400,
    "message": "Could not delete the user, try again.",
    "extended_message": ""
}
```
