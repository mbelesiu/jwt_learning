# jwt Node.js Example


#### About
This is a basic example of a jwt authentication server architecture. 

Two servers are implemented 
* An Authentication Server - handles the generation, refreshing, and deletion of jwt tokens
* A API server - Retrieves posts made by the user

The API server is generic for the example, but what ever your API server is doing, it just needs access to ACCESS_TOKEN_SECRET and REFRESH_TOKEN_SECRET, which are "secretly" stored in an .env file.

## Setup
#### Inital setup 
```
$ cd ../jwt_learning
$ npm install
```
#### To Start the servers
##### To start the API server
```
$ npm start
```
##### To start the authentication server
```
$ npm run start2
```
Servers are running on ports 3000 and 4000 respectively 

#### TO Run Examples
`Note: I used Postman to handle example requests`
>POST http://localhost:4000/login Content-Type: json {"username": "Jim"}

