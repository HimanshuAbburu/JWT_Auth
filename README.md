# Pre-requisites
- Node.js.
- Postman or any other client to make calls to the API endpoints. (curl commands if you are familar).

# Set-up
- Clone this reository to your local machine.
- Run the following command in the terminal/command propmpt where the repository is cloned, to install all the dependencies.
``` npm install```
- Have 2 terminals/command lines open to run on 2 different ports. And enter the following command and hit enter ```npm run devstart``` & ```npm start```.


# cURLs to call the API endpoints

*Copy the curl requests and paste it in the postman URL bar, the whole request should be set for you to make calls.*

1. To generate a JWT access_token. (It also returns a refresh_token, which can be used in the step 3).<br/>
```curl --location 'http://localhost:4000/login' \ --header 'Content-Type: application/json' \ --data '{ "username": "Jane"}' ```
2. To retrieve the value associated with the JWT token. (Use the access_token generated from above curl).<br/>
```curl --location 'http://localhost:3000/posts' \ --header 'Authorization: Bearer access_token'```
3. To refresh the access_token, if expired. (Use the refresh_token generated in step 1).<br/>
```curl --location 'http://localhost:4000/token' \ --header 'Content-Type: application/json' \ --data '{"token": "refresh_token"}'```
4. To delete the tokens and restrict future access.<br/>
```curl --location --request DELETE 'http://localhost:4000/logout' \ --header 'Content-Type: application/json' \ --data '{"token": "access_token"}'```
<br/>
<br/>
<br/>
<br/>

*This project is a replica from Web Dev Simplified YT channel. It was developed in the interest of learing about JWT tokens and its development.*
