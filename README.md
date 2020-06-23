# express_app_heroku_test
## NodeJS Express App to Test Heroku Deployment 

## Express Deployment Steps
1. Add `"start": "node index.js"` to `scripts` property in `package.json` file
2. Add the code snippet below to the `package.json` file
```JS
"engines": {
    "npm": "6.14.5",
    "node": "12.18.1"
  }
```
3. Update the port number specified in the entry point or config keys file
```JS
let port = process.env.PORT || 8000;
```
4. Update the MongoDB connection string in the entry point for config keys file to pass in the MongoURI as a heroku environment variable
```JS
let mongoDB = process.env.MONGODB_URI || YOURCONNECTIONSTRING
```
4. Add and commit your changes
5. Run `heroku local` to test build
6. If step 5 is successful, run `git push heroku master` to deploy changes
7. Run `heroku open` to view running site

Optional : Send a string at the site root from the entry point file so that the response is displayed instead of `CANNOT GET /`
```JS
// route for site root 
app.get('/', (req,res) => {
    res.send(`Append /api to the url to access my api `);
});
```
