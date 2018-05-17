# eloomi Rest API v3 documentation
The eloomi Rest API contains all the needed information and details to get started!

## Authentication
Authenticating with the API is done with bearer tokens, and requires a Client ID and Client Secret, which can be provided by reaching out to us, and the process to authenticate is as follow.
Initiate a POST-Request to `https://api.eloomi.com/oauth/token` with the following headers:
`
grant_type: client_credentials
client_id: 200
client_secret: JG4m3eKWGMPKLYJL7DV8dquDjKgXYsGlZO2VL5i4
scope: *
`
The response to this request will look as the following:
```json
{
    "token_type": "Bearer",
    "expires_in": 31535999,
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIm..........b8aICjumbWHvJs6tr1WZ74Y"
}
```
The value of "access_token" is to be used for any further requests made to the API, as a Bearer Token header.

## Users
This will list the endpoints valid for managing users.
- List users : `GET /v3/users`
- Get user : `GET /v3/users/:id`
- Create user : `POST /v3/users`
- Update user : `PATCH /v3/users/:id`


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
