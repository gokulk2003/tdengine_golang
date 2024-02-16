# MQTT to TDengine Data Ingestion

This Go application subscribes to an MQTT topic, listens for incoming messages, decodes the payload, and inserts the data into a TDengine database. Here's a simple guide to understand and use the application:

## Prerequisites
- **Go Installation**: Make sure you have Go installed on your machine.

- **MQTT Broker**: Ensure that an MQTT broker is running and accessible on `localhost:1883`.

- **TDengine Server**: Make sure the TDengine server is running, and update connection details in the code.

## Setup
1. **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd <repository-name>
    ```

2. **Install Dependencies:**
    ```bash
    go get -u github.com/eclipse/paho.mqtt.golang
    go get -u github.com/taosdata/driver-go/v3/taosSql
    ```

3. **Update TDengine Connection:**
    - Modify username, password, and server address in the `setupTDengine` function.

## Run the Application
```bash
go build
./<executable-name>
