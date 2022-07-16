# Emlak Ilan Sistemi

A web application for posting real estate ads.


**Tech Stack**:

- Java 11
- Spring Web
- PostgreSQL


## UserService

User entity fields:  
- username
- password
- email
- isAdmin
- firstName
- lastName
- telephone


### API Endpoints
- `GET /api/users` lists all users
- `GET /api/users/:id` shows user with given id
- `POST /api/users` creates new user
- `DELETE /api/users/:id` deletes a user

- `POST /login` generates a JWT if authentication is successful
- `POST /register` creates new user



## PropertyService

Checks JWT provided in `Authentication` header before doing any operation (except `GET /properties`)

Property entity fields:  
- authorId: Long
- dateCreated: LocalDate
- dateModified: LocalDate
- status: enum('PENDING', 'ACCEPTED', 'REJECTED')
- title: String
- description: String `TEXT`
- imagePath: String


