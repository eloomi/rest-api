# eloomi REST API v3 documentation
The eloomi REST API contains all the needed information and details to get started!

## Authentication
Authenticating with the API is done with bearer tokens, and requires a Client ID and Client Secret, which can be provided by reaching out to us, and the process to authenticate is as follow.
Initiate a POST-Request to 
```
https://api.eloomi.com/oauth/token
```
with the following headers:
``` 
grant_type: client_credentials
client_id: 200
client_secret: JG4m3eKWGMPKLYJL7DV8dquDjKgXYsGlZO2VL5i4
scope: *
```
The response to this request will look as the following:
```json
{
    "token_type": "Bearer",
    "expires_in": 31535999,
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIm..........b8aICjumbWHvJs6tr1WZ74Y"
}
```
The value of "access_token" is to be used for any further requests made to the API, as a Bearer Token header.

## Rate Limiting
In the Rest API, Rate Limiting is enabled and you're limited to 600 requests pr. rolling 60 seconds.

In the response of any request, a few headers will be added to tell what your current limit is, and how many requests you have remaining.

```
X-RateLimit-Limit : 600
X-RateLimit-Remaining : 599
```
If you exhaust your ratelimit, an additional header will be provided to tell when your ratelimit is reset.


## Failure Responses
**Invalid Bearer Token**

**Status**: 401 Unauthorized
```json
{
    "error": "Unauthenticated."
}
```

**Invalid `client_id` or `client_secret`**

**Status**: 400 Bad Request 
```json
{
    "error": "invalid_client",
    "message": "Client authentication failed"
}
```

**Invalid `scope`**

**Status**: 400 Bad Request 
```json
{
    "error": "invalid_scope",
    "message": "The requested scope is invalid, unknown, or malformed",
    "hint": "Check the `user` scope"
}
```

#Endpoints 

## [Users](users/README.md)
Valid endpoints for the users API.
- [List users](users/get.md) : `GET /v3/users`
- [Create user](users/post.md) : `POST /v3/users`
- [Get user](users/pk/get.md) : `GET /v3/users/:pk`
- [Update user](users/pk/patch.md) : `PATCH /v3/users/:pk`
- Delete user : `DELETE /v3/users/:pk`

**Custom User-endpoints:**
- Get user by EmployeeID : `GET /v3/users-employee_id/:employee_id` 
- Update user by EmployeeID : `PATCH /v3/users-employee_id/:employee_id` 
- Delete user by EmployeeID : `DELETE /v3/users-employee_id/:employee_id` 




## Goals
This will list the endpoints valid for managing goals.


## Units (Departments)
This will list the endpoints valid for managing units (departments).


## Teams
This will list the endpoints valid for managing teams.


## Groups (Access Groups)
This will list the endpoints valid for managing access groups.


## Coaches
This will list the endpoints valid for managing coaches.


## Courses
This will list the endpoints valid for managing courses.


## Orders (CourseShop only)
This will list the endpoints valid for managing orders.


## Customers (CourseShop only)
This will list the endpoints valid for managing customers.


## Paths (Performance Appraisal)
This will list the endpoints valid for managing paths.
