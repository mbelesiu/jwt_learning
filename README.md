# JWT Node.js Example


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

#### To Run Examples
`Note: I used Postman to handle example requests`
For login and generating new Access Token & Refresh Token:
>POST http://localhost:4000/login Content-Type: json {"username": "Jim"}


`Note: Default timeout for Access tokens has been set to 30 seconds`
For accessing the user's posts:
>GET http://localhost:3000/posts Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiS3lsZSIsImlhdCI6MTYxNDU0MzY0NywiZXhwIjoxNjE0NTQzNjc3fQ.YfKRYItIOEZ27wfw5S9V6asxWatHRdrdSiHvGuLvpPw

For refreshing Access Token before loging out:
>POST http://localhost:4000/token Content-Type: json {"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiSmltIiwiaWF0IjoxNTY4NzU5OTIyfQ.RT6wszuCeFLwC_6ksmNMIELxiC5s-uRivfRxyZof5ag"}

For loging the user out, and ensuring the refresh token is removed as well:
>DELETE http://localhost:4000/logout Content-Type: json {"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiSmltIiwiaWF0IjoxNTY4NzU5OTIyfQ.RT6wszuCeFLwC_6ksmNMIELxiC5s-uRivfRxyZof5ag"}
