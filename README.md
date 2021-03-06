# ECSE3038_Final-Project
# Low Cost Patient Monitor
  The aim of this project is to build a prototype of a low cost patient monitoring system. There should be a hardware and a software component to the project.

# Hardware
  Patients using the system should be outfitted with a module that should be designed to monitor and report on at least two parameters of the patient. Those two parameters are     body temperature and positional orientation.
  An atmel based embedded device should be developed containing a gyroscope/accelerometer, a temperature sensor and an ESP WiFi module. This device should read the value from     these sensors and make a POST request to a server.

# Backend Software
  The server should handle POST requests from the embedded circuit and the input JSON body should be saved to the database appropriately. Your backend application should also be   able to handle any errors that may occur. If the incoming data is misshapen or if there is an issue saving the data to the database, the route should return an appropriate       status code to the client and a suitable error message. Your backend application should also support incoming requests that come in from the user frontend application. The       routes should be able handle the following request from the frontend:

* GET /api/patient - This route should return an array of all patient objects stored in the database.

* GET /api/patient/:id - This route should return a single patient object. The patient returned should have an ID that matches the one specified in the request.

* POST /api/patent - This route should handle the creation of a new patient object. The parameters of this object should be taken from the JSON body of the incoming request.

* PATCH /api/patent/:id - This route should allow a user to edit any of the details of a specified patient object identified by their ID. The route should respond with the newly edited patient object.

* DELETE /api/patient/:id - This route should allow a user to delete a specified patient object identified by their ID. The route should respond with a message that indicates weather the operation was successful.

# Database

Your server should be able to support and store two key types of data. 

The frontend of the web app should allow a user to create a new "patient" object. A "patient" should have a first name, last name, age and a patient_id. A patient_id should match the mac address of the ESP8266 that the patient is wearing. 

Secondly, the database should be able to store data that's being posted to the server by the embedded device being worn by each patient. Each post should be added to the database as a new "record" object. A "record" should have a patient_id, position, a temperature and a last_updated (this value should be generated by the server, it should not be sent to the server by the embedded circuit.).

### Frontend

The frontend application should have two views:

1. A main page where a grid of patient cards are displayed. Each card should show the patient's first and last name and their current position. 
Each card should also have an edit and delete button. When the edit button is pressed, the view should be modified to accommodate new values to be sent to the backend in a PATCH request for the patient object. When the delete button is clicked, a DELETE request should be sent to the backend to remove the specified patient object.
The view should reflect the changes made by the user without the need of a full page refresh.

2. A secondary page that shows the details of a single patient. This view should be shown if a user clicks on one of the patient cards from the main view. This new view should show only the details of the patient in focus. The patient's first and last name should be displayed along with their current position, their current temperature in numerical form as well as a graph of the patients temperature over time. The graph should show temperature of the patient over the time span of the last half hour. This graph should update as soon as new a record data point is received by the backend and saved in the database. The graph should display a plot of temperature vs last_updated. There should be a BACK button that, when clicked, returns the user to the patient grid view.
