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

1. **Build the Program**: Build the Go program using the following command:

    ```bash
    go build
    ```

2. **Run the Program**: Execute the compiled program:

    ```bash
    ./mqtt_to_tdengine
    ```

3. **Output**: The program will subscribe to the MQTT topics specified in the configuration file and insert received data into the TDengine database.


# Building a Go Application with TDengine Client in Docker

This Dockerfile is designed to build a Go application that interacts with TDengine (formerly TaosData) using the official Golang Docker image. It includes steps to download and extract the TDengine client, set up the environment, and compile the Go application.

## Requirements

- **Docker**: Ensure Docker is installed on your system.

## Dockerfile

```Dockerfile
# Use the official Golang image
FROM golang:latest

# Install wget and tar
RUN apt-get update && apt-get install -y wget tar

# Download and extract TDengine client
RUN wget https://www.tdengine.com/assets-download/3.0/TDengine-client-3.2.3.0-Linux-x64.tar.gz && \
    tar -xzvf TDengine-client-3.2.3.0-Linux-x64.tar.gz && \
    cd TDengine-client-3.2.3.0 && \
    chmod +x install_client.sh && \
    ./install_client.sh && \
    cd ..

# Set the working directory inside the container
WORKDIR /app

COPY . .

# Build the Go application
RUN go mod tidy
RUN go build -o main .

# Command to run the executable
CMD ["./main"]


## Usage

1. **Create Dockerfile**: Copy the provided Dockerfile content into a file named `Dockerfile` in your Go project directory.

2. **Build Docker Image**: Run the following command in your terminal to build the Docker image:

    ```bash
    docker build -t my-go-app .
    ```

    Replace `my-go-app` with the desired name for your Docker image.

3. **Run Docker Container**: Once the image is built, you can run a Docker container using the following command:

    ```bash
    docker run --rm my-go-app
    ```

    This command will execute the compiled Go application inside the Docker container.

4. **Output**: The application will interact with TDengine using the installed client library as configured in your Go code.

This setup provides a convenient way to containerize your Go application with TDengine client dependencies included. Adjust the versions and paths in the Dockerfile as needed for your specific project requirements.



