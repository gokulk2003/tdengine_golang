MQTT to TDengine Data Ingestion
This Go application subscribes to an MQTT topic, listens for incoming messages, decodes the payload, and inserts the data into a TDengine database. Here's a simple guide to understand and use the application:

Prerequisites
Make sure you have Go installed on your machine.
Ensure that both MQTT broker (listening on localhost:1883) and TDengine server are running.
Setup
Clone the repository.

Install the required Go dependencies:

bash
Copy code
go get -u github.com/eclipse/paho.mqtt.golang
go get -u github.com/taosdata/driver-go/v3/taosSql
Update TDengine connection details in the setupTDengine function (e.g., username, password, and server address).

Run the Application
Execute the following commands in your terminal:

bash
Copy code
go build
./<executable-name>
Configuration
MQTT broker details can be adjusted in the AddBroker function.
MQTT topic to subscribe is set to "td_engine" and can be changed in the Subscribe function.
TDengine table name and database name can be modified in the insertDataIntoTDengine function.
Exit Gracefully
To exit the application gracefully, send an interrupt signal (typically Ctrl+C). The application will wait for ongoing processes to finish before exiting.
