# express_app_heroku_test
## NodeJS Express App to Test Heroku Deployment 

## Express Deployment Steps
1. Add the code snippet below to the `package.json` file
```JS
"engines": {
    "npm": "6.14.5",
    "node": "12.18.1"
  }
```
2. Update the port number specified in the entry point or config keys file to allow for any available port
```JS
let port = process.env.PORT || 8000;
```
3. Update the MongoDB connection string in the entry point for config keys file to pass in the MongoURI as a heroku environment variable
```JS
let mongoDB = process.env.MONGODB_URI || YOURCONNECTIONSTRING
```
4. 
