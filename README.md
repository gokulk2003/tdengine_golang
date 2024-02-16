# MQTT to TDengine Data Ingestion

This Go application subscribes to an MQTT topic, listens for incoming messages, decodes the payload, and inserts the data into a TDengine database.

## Prerequisites
- **Go Installation**: Ensure that you have Go installed on your machine.

- **MQTT Broker**: Make sure an MQTT broker is running and accessible on `localhost:1883`.

- **TDengine Server**: Ensure that the TDengine server is running.

## Getting Started
1. **Clone the Repository:**
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

4. **Run the Application:**
    ```bash
    go build
    ./<executable-name>
    ```

## Configuration
- **MQTT Broker Details:** Adjust in the `AddBroker` function.

- **MQTT Topic:** Set to "td_engine" and can be changed in the `Subscribe` function.

- **TDengine Table and Database Names:** Modify in the `insertDataIntoTDengine` function.

## Exit Gracefully
To exit the application gracefully, send an interrupt signal (typically `Ctrl+C`). The application waits for ongoing processes to finish before exiting.

## Customization
Feel free to customize the application based on your MQTT and TDengine configurations. Refer to the code comments for additional information.

For any issues or questions, please refer to the [documentation](#) or open a [new issue](<repository-url>/issues).

---

**Note:** Replace `<repository-url>` and `<repository-name>` with the appropriate values for your GitHub repository.
