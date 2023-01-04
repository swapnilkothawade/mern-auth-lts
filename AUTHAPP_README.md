# auth-app

Minimal Mongo Express Node app with authentication using passport and JWTs. I chose this approach to build this based on the requirements and my experience building applications with MERN stack. Since the requirement was to have register/login/logout functionality I decided to use bcryptjs library to store the encrypted password in the database. I also used passport and passport-jwt library for authentication using JSON web token. 

## Built With

- [Express](http://expressjs.com/) 
- [NodeJs](https://nodejs.org/en/)
- [MongoDB](https://www.mongodb.com/)

## Folder Structure

.
├── Dockerfile - docker file contains commands while creating an image
├── config
│   ├── keys.js - Contains the MongoDB URI and secret for passport JWT authentication
│   └── passport.js - contains passport JWT strategy code for validating user
├── docker-compose.yml - This file defines services and volumes for docker application
├── models
│   └── User.js - Mongo db user model
├── package-lock.json
├── package.json
├── routes
│   └── api
│       └── users.js - Contains register/login/logout routes
├── server.js - This file has the server creation code
└── validation
    ├── login.js - Contains code to validate the login fields
    └── register.js - Contains code to validate the register fields


## Configuration

Make sure to add your own `MONGOURI` from your [mLab](http://mlab.com) database in `config/keys.js`.

```javascript
module.exports = {
  mongoURI: "YOUR_MONGO_URI_HERE",
  secretOrKey: "secret"
};
```

## Dependencies

1. "bcryptjs": "^2.4.3" - This library is used to encrypt and decrypt the password
2. "body-parser": "^1.20.0" - This library parses all *bodies* as a Buffer and only looks at requests where the Content-Type header matches the type option.
3. "express": "^4.18.1", - This library helps manage the servers and routes
4. "is-empty": "^1.2.0" - This library was used to check whether value is empty
5. "jsonwebtoken": "^8.5.1" - This library helps create a JWT web token on login
7. "mongoose": "^5.13.14". - Mongoose is a MongoDB tool library to support both promises and callbacks.
8. "passport": "^0.4.1" - This library was for authentication of requests
9. "passport-jwt": "^4.0.0" - This library was used for authentication using JSON web token
10. "validator": "^12.2.0" - This library was used to validate strings

## Getting Started

Instructions on setting up your project locally. To get a local copy up and running follow these simple example steps.

### Prerequisites

- npm

  ```javascript
  npm install npm@latest -g
  ```

### Installation & Getting started


```javascript
// Install dependencies for server
cd auth-app && npm install 

// Build an image from a Dockerfile
docker build -t app .

// Create and start containers
docker-compose up -d

// Server runs on port 8080
```
