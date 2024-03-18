# XML Parser with Java

This Java program is designed to parse XML data retrieved from a specified URL and extract values based on provided tags. It utilizes Java's built-in XML parsing capabilities along with the Jackson library for handling JSON configuration.

## Requirements

- **Java Development Kit (JDK)**: Ensure JDK is installed on your system.
- **Internet Connection**: Required to access XML data from a specified URL.
- **Maven or any Build Tool**: Optional for dependency management.

## Configuration
The program requires a configuration file named `config.json`, which should be located in the same directory as the Java source code. The configuration file should have the following structure:
```json
{
"MACHINE_PARAMS": {
"PROTOCOL": "mtconnect",
"MACHINE_IP": "localhost:5001",
"INTERVAL": 5,
"STATIC": {
"GATEWAY_ID": "GW1234",
"MACHINE_ID": "M1234"
},
"TAGS": [
{
"ControllerMode": "mode",
"Availability": "avail",
"Execution": "execution",
"Load": "Sload",
"EmergencyStop": "estop",
"RotaryVelocity": "Srpm",
"PartCount": "PartCountAct",
"PalletId": "pallet_num"
}
]
}
}


- **PROTOCOL**: Protocol used for communication (e.g., "mtconnect").
- **MACHINE_IP**: IP address and port of the machine from which XML data is to be fetched.
- **INTERVAL**: Interval (in seconds) at which the program will fetch the XML data.
- **STATIC**: Static parameters such as gateway ID and machine ID.
- **TAGS**: Array of objects specifying XML tag names and corresponding aliases.

## Dependencies

- [Jackson](https://github.com/FasterXML/jackson) library is used for parsing JSON configuration files.

## Usage

1. **Compile the Code**: Compile the Java source code using the following command:

    ```bash
    javac main.java
    ```

2. **Run the Program**: Execute the compiled Java program using the following command:

    ```bash
    java main
    ```

3. **Output**: The program will fetch XML data from the specified URL, parse it, and print the values of sp
