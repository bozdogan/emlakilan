
## UserService

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

