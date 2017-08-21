---
title: DocGenie API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript

toc_footers:
  - <span> &copy2017, Developed by Mazi Ugochukwu in Andela </span>

includes:
  - users
  - documents
  - roles

search: true
---

# DocGenie API Documentation

## Introduction
Docmanger API contains several end points that allows users to create, edit, retrieve and delete documents. It also sets access privileges so only authorized users can perform certain operations.

## Development
The application was developed with [NodeJs](http://nodejs.org/) and [Express](http://expressjs.com/) is used for routing. The [Postgres](http://postgresql.com/) database was used with sequelize as the ORM.

## Installation
Follow the steps below to setup a local development environment. First ensure you have [Postgresql](https://www.postgresql.org/) installed, and a version of [Node.js](http://nodejs.org/) equal or greater than v6.8.0.

1. Clone the repository to your local machine: `git clone ttps://github.com/andela-mugochukwu/DocManager.git`.
2. Cd into the project directory:  `cd DocManager`
4. Install project dependencies `yarn install`
5. Start the express server in development mode: `yarn start:dev`.

## API Summary
### Users
EndPoint                           |   Functionality
-----------------------------------|------------------------
POST /api/v1/users/login         |   Logs in a user.
POST /api/v1/users/              |   Creates a new user.
GET /api/v1/users/                    |   Gets all registered users (available only to the Admin).
GET /api/v1/users/:id                 |   Finds a particular user by his/her id.
PUT /api/v1/users/:id                 |   Updates a user's attributes based on the id specified (available to the profile owner or admin)
DELETE /api/v1/users/:id              |   Deletes a user (available only to the profile owner)
GET /api/v1/users/:id/documents       | Gets all documents belonging to a particular user

### Documents
EndPoint                      |   Functionality
------------------------------|------------------------
POST /api/v1/documents/          |   Creates a new document.
GET /api/v1/documents/           |   Gets all documents.
GET /api/v1/documents/:id        |   Find a particular document by it's id.
PUT /api/v1/documents/:id        |   Updates a document attributes. (available only to the owner)
DELETE /api/v1/documents/:id     |   Delete a particular document. (available only to the owner)
GET /api/search/documents/?searchKey=${query} | Get all documents with title or content containing the search query

### Roles (available only to the SuperAdmin)
EndPoint                          |   Functionality
----------------------------------|------------------------
GET /api/v1/roles/                   |   Get all created Roles.
POST /api/v1/roles/                  |   Create a new Role.
DELETE /api/v1/roles/:id             |   Delete a Role.