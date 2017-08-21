# Users

## List All Users
> Sample JSON structured response:

```javascript
{
  "users": [
      {
          "id": 12,
          "userName": "Tolu",
          "fullname": "Tolu Afobs",
          "roleId": 2,
          "email": "tolu@gmail.com"
      },
      {
          "id": 11,
          "userName": "biodun",
          "fullname": "biodun",
          "roleId": 2,
          "email": "biodun@gmail.com"
      },
      {
          "id": 8,
          "userName": "Rob",
          "fullname": "Robert Ludlum",
          "roleId": 2,
          "email": "robert@robert.com"
      },
      {
          "id": 7,
          "userName": "Johnie",
          "fullname": "John Grisham",
          "roleId": 2,
          "email": "john@grisham.com"
      },
      {
          "id": 6,
          "userName": "Dorian",
          "fullname": "Dorian Gray",
          "roleId": 2,
          "email": "dorian@gray.com"
      },
      {
          "id": 5,
          "userName": "Max",
          "fullname": "Gruocho",
          "roleId": 2,
          "email": "max@max.com"
      }
  ],
  "paginationMetaData": {
      "totalCount": 9,
      "pages": 2,
      "page": 1,
      "pageSize": 6
  }
}
```

### Request
- Endpoint: GET: `/api/v1/users`
- Requires: Authentication

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
limit | 6 | Sets the limit.
offset | 0 | Sets the offset.

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Create User

> Request:

```javascript
{
  "username": "doro",
  "email": "doro@bucci.com",
  "roleId": "3",
  "password": "dorobucci",
  "confirmPassword": "dorobucci",
}
```

> Sample JSON structured response:

```javascript
{
   "status": "successfull",
    "userId": 1,
    "userName": "tolu",
    "roleType": "Fellow",
    "roleId": 3,
    "email": "tolu@gmail.com",
    "createdAt": "Apr 4 2018",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjEsInJvbGVJZCI6MSwiaWF0IjoxNTAyMTAwMzA5LCJleHAiOjE1MDIxODY3MDl9.vzMK6Mr7cLr7rk5mXF5KeRXlJn913XBJXQjaOGJEiXo",
}
```

### Request
- Endpoint: POST: `/api/v1/users`
- Body: `(application/json)`


### Response
- Status: `201: Created`
- Body: `(application/json)`

## Get User

> Sample JSON structured response:

```javascript
{
  "userName": "Mikail",
  "userEmail": "mikahil.stanislaski@gmail.com",
  "userRole": " "Fellow"
}
```

### Request
- Endpoint: GET: `/api/v1/users/:id`

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Edit User

> Request:

```javascript
{
  "email": "mike@gmail.com",
}
```

> Sample JSON structured response:

```javascript
{
  "status": "successful"
}
```

### Request
- Endpoint: PUT: `/api/v1/users/:id`
- Body: `(application/json)`

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Delete User

> Sample JSON structured response:

```javascript
{
    "status": "successful"
  "message": "User deleted successfully"
}
```

### Request
- Endpoint: DELETE: `/api/v1/users/:id`
- Requires: Authentication

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Login User

> Request:

```javascript
{
  "userName": "tolu",
  "password": "afolabi"
}
```

> Sample JSON structured response:

```javascript
{
    "status": "successfull",
    "userId": 1,
    "userName": "tolu",
    "roleType": "Fellow",
    "roleId": 3,
    "email": "tolu@gmail.com",
    "createdAt": "Apr 4 2018",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjEsInJvbGVJZCI6MSwiaWF0IjoxNTAyMTAwMzA5LCJleHAiOjE1MDIxODY3MDl9.vzMK6Mr7cLr7rk5mXF5KeRXlJn913XBJXQjaOGJEiXo",    
}

### Request
- Endpoint: GET: `/api/v1/users/:id/documents`
- Requires: Authentication

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Search Users

> Sample JSON structured response:

```javascript
{
  "users": [
      {
          "id": 12,
          "username": "Tolu",
          "isactive": "True",
          "roleId": 2,
          "createdAt": "Jun 4 2017",
          "email": "tolu@gmail.com"
      },
      {
          "id": 12,
          "username": "James",
          "isactive": "True",
          "roleId": 2,
          "createdAt": "Jun 4 2017",
          "email": "james@gmail.com"
      },
      {
         "id": 12,
          "username": "Mattew",
          "isactive": "True",
          "roleId": 2,
          "createdAt": "Jun 4 2017",
          "email": "mattew@gmail.com"
      },
  ],
  "paginationMetaData": {
      "pageCount": 2,
      "page": 1,
      "pageSize": 6
  }
}
```

### Request
- Endpoint: GET: `/api/v1/search/users/`
- Requires: Authentication

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
searchKey | "" | Search query.

### Response
- Status: `200: OK`
- Body: `(application/json)`