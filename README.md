# Emlak Ilan Sistemi

A web application for posting real estate ads.

**Tech Stack**:

- Java 11
- Spring Web
- PostgreSQL


## UserService
[repository](https://github.com/bozdogan/emlakilan_userservice)

NOTE: Once registered, User cannot change their username.

User entity fields:  
- username: `String`
- password: `String`
- email: `String`
- isAdmin: `bool`
- firstName: `String`
- lastName: `String`
- telephone: `String`


### API Endpoints
- `GET /api/users` lists all users
- `GET /api/users/:id` shows user with given id
- `POST /api/users` creates new user
- `DELETE /api/users/:id` deletes a user
- 
- `POST /login` generates a JWT if authentication is successful
- `POST /register` creates new user



## PropertyService
[repository](https://github.com/bozdogan/emlakilan_propertyservice)

Checks JWT provided in `Authentication` header before doing any operation

Property entity fields:  
- author: `String` 
- dateCreated: `LocalDate`
- dateModified: `LocalDate`
- status: `enum('PENDING', 'ACCEPTED', 'REJECTED')`
- title: `String`
- description: `String` - `TEXT`
- imagePath: `String`
- viewCount: `int`


### API Endpoints
- `GET /api/properties` lists all public property ads
- `GET /api/properties/:id` shows property ad with given id
- `POST /api/properties` creates new property ad
- `PUT /api/properties/:id` updates a property ad
- `DELETE /api/properties/:id` deletes a property ad
- 

- `GET /api/properties/latest` Lists latest 10 approved property ads
- <small>*ADMIN*</small> `GET /api/list-all`  
- <small>*ADMIN*</small> `GET /api/list-pending` 
- <small>*ADMIN*</small> `GET /api/list-rejected`
- <small>*ADMIN*</small> `GET /api/accept/:id`
- <small>*ADMIN*</small> `GET /api/reject/:id`



## ReportService
[repository](https://github.com/bozdogan/emlakilan_reportservice)

Creates reports for property ads. Report contains a message such as "The ad with id {POST_ID} created by {AUTHOR} {ELAPSED_TIME} ago. It is viewed {VIEW_COUNT} times.".


### API Endpoints
- `GET /api/report/:id` shows report for an ad
- `GET /api/report/:id` triggers to update report for an ad




