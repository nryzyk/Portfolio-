As part of the project, REST API (Fake API) tests were performed using HTTP methods: GET, POST, PUT, PATCH, and DELETE to verify the correct operation of endpoints and data updates.

## The tests were carried out using automated test scripts (snippets), including:

 - checking the HTTP response code (request status check),
 - validating values in the JSON response (JSON value check),
 - verifying the presence of specific strings in the response (contains string check),
 - reading and using environment variables (get environment variable check),
 - validating JSON data in relation to environment variables.

---

## REST API Instruction

## 1. Ensure you have the following installed:

    Node.js 
    Postman app
    Environment.json (DEV env.postman_environment.json)
    Collection.json (TEST.postman_collection.json)
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




## 4. Test Results
presented in the directory: https://github.com/nryzyk/Portfolio-/tree/main/API_Testing/test_summary

A total of **13 API tests** were performed as part of the project, of which:
-  **11 tests were successful**
-  **2 tests were unsuccessful** - explained in the next step




## 5. Detected test failures: 2


Fail-01: DELETE post – incorrect response status

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);

- Endpoint: DELETE/ http://{{host}}:3000/posts/15
- Test description: Attempt to delete a post with the specified ID 15
- Expected result: Status code 200
- Actual result: Status code ≠ 200
- Reason: Post with the specified ID does not exist

- Note: Test failed due to an attempt to delete a non-existent resource.
The API behaviour is consistent with business logic and confirms the correct handling of invalid request.
The test is an example of a negative test.


Fail-02: GET /posts – title field value mismatch

pm.test("Check the title 1", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData[2].title).to.eql('Bye world');

- Endpoint: POST/ http://{{host}}:3000/posts
- Test description: Verify that the 3rd post (index 2) has a valid title field value.
- Expected result: "title": "Bye world"
- Actual result: "title": "json-server3333"
- Error:
"AssertionError: expected 'json-server3333' to deeply equal 'Bye world'"

- Note: The test failed because the test data did not match the test expectations.
This case is an example of a negative test and confirms that the response validation mechanism is working correctly.

  


