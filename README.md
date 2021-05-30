# ECSE3038_Final-Project
# Low Cost Patient Monitor
The aim of this project is to build a prototype of a low cost patient monitoring system. There should be a hardware and a software component to the project.

Hardware
Patients using the system should be outfitted with a module that should be designed to monitor and report on at least two parameters of the patient. Those two parameters are body temperature and positional orientation.
An atmel based embedded device should be developed containing a gyroscope/accelerometer, a temperature sensor and an ESP WiFi module. This device should read the value from these sensors and make a POST request to a server.

 {
     "patient_id": <esp_mac_address>,
     "position": <gyro_value>,
     "temperature": <temp_value>
 }
