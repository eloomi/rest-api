# Users
Valid endpoints for the users API.
- [List users](users/get.md) : `GET /v3/users`
- Create user : `POST /v3/users`
- [Get user](users/pk/get.md) : `GET /v3/users/:pk`
- [Update user](users/pk/patch.md) : `PATCH /v3/users/:pk`
- Delete user : `DELETE /v3/users/:pk`

**Custom User-endpoints:**
- Get user by EmployeeID : `GET /v3/users-employee_id/:employee_id` 
- Update user by EmployeeID : `PATCH /v3/users-employee_id/:employee_id` 
- Delete user by EmployeeID : `DELETE /v3/users-employee_id/:employee_id` 
