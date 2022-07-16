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

