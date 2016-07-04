# JWT authorisation server

## Prerequisite

* mongo db daemon running
* node installed
* nodemon installed

Create a config.js file in the root with following content (replace
the secret string with your secret

```js
module.exports = {
    secret: "your_secret_here"
};
```

## Config

* Run **npm install** to install dependencies
* Run **npm run dev** to start the server

## Endpoints

### Sign up

Create a user and receive a JWT token

Reach with POST request to http://localhost:3090/signup

#### The parameters

```js
{"email":"test@example.com","password":"test"}
```

Example of a response : 

```js
{
  "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI1NzdhNDMwNmU4Yjk1ZjU3MTljZDY4NTciLCJpYXQiOjE0Njc2MzA0MDU4OTB9.aiANjSWtpk8LYaqJ870ODUa3lu8nAPRwhSY8_y1LpU4"
}
```

### Sign in

Handle the user login process
 
Reach with POST to http://localhost:3090/signin

#### The parameters

```js
{"email":"test@example.com","password":"test"}
```

Example of a response : 

```js
{
  "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI1NzdhNDMwNmU4Yjk1ZjU3MTljZDY4NTciLCJpYXQiOjE0Njc2MzA0MDU4OTB9.aiANjSWtpk8LYaqJ870ODUa3lu8nAPRwhSY8_y1LpU4"
}
```

### Protected resource

User needs to be authenticated to fetch data from this endpoint.

Reach with GET to http://localhost:3090/

#### The parameters

A header called authorization which must be set to a valid JWT token