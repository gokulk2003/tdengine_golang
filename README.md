# MQTT to TDengine Data Forwarder

This Go program subscribes to MQTT topics, receives data payloads, and inserts the data into a TDengine database. It utilizes the Eclipse Paho MQTT Go client library for MQTT communication and the TaosData Go driver for interacting with TDengine.

## Requirements

- **TDengine Database**: Ensure TDengine is installed and running on your system.
- **MQTT Broker**: Have an MQTT broker accessible to which the program can connect.
- **Go Programming Language**: Make sure Go is installed on your system.

## Configuration

The program requires a configuration file named `config.json`, which should be located in the same directory as the executable. The configuration file should have the following structure:

```json
{
  "topics": [
    "topic1",
    "topic2"
  ]
}
```
- **topics: Array of MQTT topics to subscribe to.
## Dependencies

- **Eclipse Paho MQTT Go client**: For MQTT communication.
- **TaosData Go driver**: For interacting with TDengine.
- The required dependencies (`github.com/eclipse/paho.mqtt.golang` and `github.com/taosdata/driver-go/v3/taosSql`) will be fetched automatically using Go modules.

## Usage

1. **Clone the Repository**: Clone or download the repository containing the Go source code.

2. **Build the Program**: Build the Go program using the following command:

    ```bash
    go build
    ```

3. **Run the Program**: Execute the compiled program:

    ```bash
    ./mqtt_to_tdengine
    ```

4. **Output**: The program will subscribe to the MQTT topics specified in the configuration file and insert received data into the TDengine database.
