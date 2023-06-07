# Talon-one-QA-task
## Postman Collection for Comment Functionality Testing

This repository contains a Postman collection and environment variables file for testing the comment functionality of an API. The collection is designed to prevent regressions and ensure the expected behavior and responses are met. The tests are performed using a JSON Server to simulate the REST API responses.

## Prerequisites
To run the tests in this Postman collection, you need to have the following software installed:

  * Postman
  * JSON Server
* You can install JSON Server globally using npm (Node Package Manager) by running the following command in your terminal

       sudo npm install -g json-server
       
## Setting up the Environment

* Clone the repository to your local machine.
* Navigate to the project folder.
* Open a terminal or command prompt in the project folder.

       json-server --watch db.json --port 4000
This will start the JSON Server and load the data from the db.json file.

## Running the Tests

* Open Postman on your machine.
* Import the Postman collection (Talon.one.postman_collection.json) into Postman.
    * Click on the "Import" button in the top-left corner of the Postman app.
    * Select the JSON file (Talon.one.postman_collection.json) from the cloned repository.
* Import the environment variables file (Test.postman_environment.json) into Postman.
    * Click on the "Import" button in the top-left corner of the Postman app.
    * Select the JSON file (Test.postman_environment.json) from the cloned repository.
    * Make sure to select the appropriate environment variables file when running the tests.
* Once imported, the collection will appear in the left sidebar of Postman.
* Select the desired environment variables file from the dropdown menu in the top-right corner of Postman.
   
 ![Screenshot 2023-06-07 at 12 40 36](https://github.com/MythiliMohanbabu04/Talon-one-QA-task/assets/71710850/ba2d6d19-4536-4c22-b4c7-dded171d0014)

   
* Click on the collection to expand it and view the available requests.
* Before running the tests, make sure the JSON Server is still running and listening on the specified port (default is http://localhost:4000).
*  Select the desired request and click on the "Send" button to execute it.
* The test results will be displayed in the "Test Results" section of Postman, showing the status of each test case.

  ### Only in case of errors - When server is already listening to specified port
   * There is possibility that server is already listening to that port , in such case
   * Open the terminal or command prompt on your computer.
   * Run the following command to find the process ID (PID) of the process running on port 4000:
           
           lsof -i :4000
   This command lists the processes running on port 4000 and their corresponding PIDs.
   * Look for the process with the "LISTEN" status and note down its PID.

           kill -9 <PID>
    Replace < PID > with the actual process ID you noted down. Using the kill -9 command should forcefully terminate the process, allowing you to free up port 4000 for other purposes.
           


## Note
* The tests in the collection cover various positive and negative scenarios to ensure the comment functionality behaves as expected.
* Environment variables are used to store and reuse dynamic values throughout the collection, such as comment IDs.
* Couple of cases "Create a Comment - (Invalid Post ID)" & "Create a Comment - (Empty Comment Body)" will fail which is expected and should be fixed when the mentioned issue here https://trello.com/b/dl6DVRoP/qa-task-talonone is fixed.
* Screenshots or summaries of test results can be captured and added as attachments to the individual test cases in the collection.
