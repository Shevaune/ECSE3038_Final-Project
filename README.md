# ECSE3038_Final-Project
# Low Cost Patient Monitor
  The aim of this project is to build a prototype of a low cost patient monitoring system. There should be a hardware and a software component to the project.

# Hardware
  Patients using the system should be outfitted with a module that should be designed to monitor and report on at least two parameters of the patient. Those two parameters are     body temperature and positional orientation.
  An atmel based embedded device should be developed containing a gyroscope/accelerometer, a temperature sensor and an ESP WiFi module. This device should read the value from     these sensors and make a POST request to a server.

Backend Software
The server should handle POST requests from the embedded circuit and the input JSON body should be saved to the database appropriately. Your backend application should also be able to handle any errors that may occur. If the incoming data is misshapen or if there is an issue saving the data to the database, the route should return an appropriate status code to the client and a suitable error message. Your backend application should also support incoming requests that come in from the user frontend application. The routes should be able handle the following request from the frontend:

GET /api/patient
This route should return an array of all patient objects stored in the database.

GET /api/patient/:id
This route should return a single patient object. The patient returned should have an ID that matches the one specified in the request.

POST /api/patent
This route should handle the creation of a new patient object. The parameters of this object should be taken from the JSON body of the incoming request.

PATCH /api/patent/:id
This route should allow a user to edit any of the details of a specified patient object identified by their ID. The route should respond with the newly edited patient object.

DELETE /api/patient/:id
This route should allow a user to delete a specified patient object identified by their ID. The route should respond with a message that indicates weather the operation was successful.
