# Documents

## List All Documents
> Sample JSON structured response:

```javascript
{
  "documents": [
      {
          "id": 15,
          "userId": 1,
          "title": "Biodun's Dilemma",
          "access": "Private",
          "body": "So, what will I eat for breakfast now that there's an election going on????",
          "createdAt": "2017-07-22T06:53:06.520Z",
          "updatedAt": "2017-07-22T06:53:06.520Z",
      },
      {
           "id": 14,
          "userId": 1,
          "title": "Biodun's is Dilemma",
          "access": "Private",
          "body": "So, what will I eat for breakfast and now that there's an election going on????",
          "createdAt": "2017-07-22T06:53:06.520Z",
          "updatedAt": "2017-07-22T06:53:06.520Z",
      },
      {
           "id": 11,
          "userId": 1,
          "title": "Biodun's is my Dilemma",
          "access": "Public",
          "body": "So, what will I eat now that there's an election going on????",
          "createdAt": "2017-07-22T06:53:06.520Z",
          "updatedAt": "2017-07-22T06:53:06.520Z",
      },
  ],
  "paginationMetaData": {
      "totalCount": 7,
      "pages": 2,
      "currentPage": 1,
      "pageSize": 3
  }
}
```

### Request
- Endpoint: GET: `/api/v1/documents`

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
limit | 6 | Sets the limit.
offset | 0 | Sets the offset.

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Create Document

> Request:

```javascript
{
  "title": "Chester",
  "body": "I'm so high, I can hear heaven. Oh, but Heaven can't hear me",
  "access": "Public"
}
```

> Sample JSON structured response:

```javascript
{
  "status": "successful",
  "documentId": 4
}
```

### Request
- Endpoint: POST: `/api/v1/documents`
- Requires: Authentication
- Body: `(application/json)`


### Response
- Status: `201: Created`
- Body: `(application/json)`


## Get Document

> Sample JSON structured response:

```javascript
{
  "status": "successful",
  "documents": {
           "id": 11,
          "userId": 1,
          "title": "Biodun's is my Dilemma",
          "access": "Public",
          "body": "So, what will I eat now that there's an election going on????",
          "createdAt": "2017-07-22T06:53:06.520Z",
          "updatedAt": "2017-07-22T06:53:06.520Z",
  }
}
```

### Request
- Endpoint: GET: `/api/v1/documents/:id`

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Edit Document

> Request:

```javascript
{
  "body": "What's new?"
}
```

> Sample JSON structured response:

```javascript
{
  status: "successful"
}
```

### Request
- Endpoint: PUT: `/api/v1/documents/:id`
- Requires: Authentication
- Body: `(application/json)`

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Delete Document

> Sample JSON structured response:

```javascript
{
  "status": "successful"
  "message": "'Jungle Boy' has been deleted!"
}
```

### Request
- Endpoint: DELETE: `/api/v1/documents/:id`
- Requires: Authentication

### Response
- Status: `200: OK`
- Body: `(application/json)`


## Search Documents

### Request
- Endpoint: GET: `/api/v1/search/documents`
- Requires: Authentication

### Response
- Status: `200: OK`
- Body: `(application/json)`

> Sample JSON structured response:

```javascript
{
  "documents": [
      {
          "id": 15,
          "userId": 1,
          "title": "Biodun's Dilemma",
          "access": "Private",
          "body": "So, what will I eat for breakfast now that there's an election going on????",
          "createdAt": "2017-07-22T06:53:06.520Z",
          "updatedAt": "2017-07-22T06:53:06.520Z",
      },
      {
           "id": 14,
          "userId": 1,
          "title": "Biodun's is Dilemma",
          "access": "Private",
          "body": "So, what will I eat for breakfast and now that there's an election going on????",
          "createdAt": "2017-07-22T06:53:06.520Z",
          "updatedAt": "2017-07-22T06:53:06.520Z",
      },
      {
           "id": 11,
          "userId": 1,
          "title": "Biodun's is my Dilemma",
          "access": "Public",
          "body": "So, what will I eat now that there's an election going on????",
          "createdAt": "2017-07-22T06:53:06.520Z",
          "updatedAt": "2017-07-22T06:53:06.520Z",
      },
  ],
  "paginationMetaData": {
      "pages": 2,
      "currentPage": 1,
      "pageSize": 3
  }
}
```

### Request
- Endpoint: GET: `/api/v1/search/documents/`
- Requires: Authentication

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
searchKey | "" | Search query.

### Response
- Status: `200: OK`
- Body: `(application/json)`