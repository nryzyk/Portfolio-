As part of the project, REST API (Fake API) tests were performed using HTTP methods: GET, POST, PUT, PATCH, and DELETE to verify the correct operation of endpoints and data updates.

##The tests were carried out using automated test scripts (snippets), including:

 - checking the HTTP response code (request status check),
 - validating values in the JSON response (JSON value check),
 - verifying the presence of specific strings in the response (contains string check),
 - reading and using environment variables (get environment variable check),
 - validating JSON data in relation to environment variables.



## REST API Instructions

## 1. Ensure you have the following installed:

    Node.js 
    Postman app
    Environment.json
    Collection.json 
    db.json 
    

## 2. Installation fake API - command prompt for Windows (instruction source: https://github.com/typicode/json-server/tree/v0.17.4)
 
- Install JSON Server 
  * npm install -g json-server@0.17.4    # NPM

- Start JSON Server 
  * cd db.json_directory
  * json-server --watch db.json

- Import collection and environment to Postman
Make sure that the DEV environment is set on and has the following values:
  * host = localhost 
  * author = author dev
  * title = title dev
  * anyname = 


## 3. Run collection in Postman

## 4. Following test and results

USED SNIPPETS

 * request status check
 * JSON value check
 * contains string check
 * get an environment variable check 
 * JSON value check related to environment 
  


