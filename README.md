# ECOlibrium Remote Sensor Module

This project comprises two distinct sensor modules designed to monitor environmental conditions in both indoor and outdoor settings. By leveraging various sensors, the modules provide real-time data, ensuring a comprehensive understanding of environmental parameters in both contexts. <br>
The indoor and outdoor modules share similarities in design, but differences exist in the functionality of some sensors.

## Description
### General WiFi/Web Server Functionality
The modules use the WiFiManager for seamless WiFi connection management. This allows the module to automatically connect to available networks when powered on. For serving web content, ESPAsyncWebServer allows for asynchronous handling of web requests, improving the efficacy of the web interface. The data from the sensors is presented via a user-friendly HTML interface, enabling users to have clear insights into the environmental parameters being monitored.
### Sensors Used for Indoor Module
SCD40: Measures carbon dioxide concentrations, crucial for monitoring indoor air quality and ventilation efficiency.<br>
SEN55: measures particulate matter, humidity, temperature, VOCs (Volatile Organic compounds), and NOx (Nitrogen Oxide) to provide a clear picture of air quality.
### Sensors Used for Outdoor Module
PMS5003: Measures varous sizes of particulate matter. <br>
PMS7003: Measures varous sizes of particulate matter (Interchangeable with the PMS5003). <br>
BME280: Measures temperature, humidity, and barometric pressure, and altitude. <br>
SHT31: Measures temperature and humidty (Interchangeable with the BME280). <br>
SGP41: Measures VOCs and NOx, integrating with the BME280 to obtain essential temperature and humidity data for accurate algorithmic readings. <br>
Detailed explanations of the functionalities and associated libraries will be provided below.

## Getting Started
### Wiring
### SCD40
| ESP32 Pin | Sensor Pin | Description |
|:-:|:-:|:--|
| `3.3V`(BUS) | `Vcc` | The SCD40 runs off of 5 and 3.3 volts, but we chose to use 3.3V |
| `GND`(BUS)| `GND` | Ground |
| `IO22` |  `SCL` | I2C clock line |
| `IO21`| `SDA` | I2C data line |
### SEN55
| ESP32 Pin | Sensor Pin | Description |
|:-:|:-:|:--|
| `5V`(BUS) | `Vcc` | The SEN55 runs off of 5V |
| `GND`(BUS)| `GND` | Ground |
| `IO22` |  `SCL` | I2C clock line |
| `IO21`| `SDA` | I2C data line |

Refer to datasheets for pin numbers and their respective assignments if it is not specified
### PMS7003
| ESP32 Pin | Sensor Pin | Description |
|:-:|:-:|:--|
| `5V`(BUS) | `Vcc` | The PMS5003 runs off of 5V. |
| `GND`(BUS)| `GND` | Ground |
| `IO22` |  `SCL` | I2C clock line |
| `IO21`| `SDA` | I2C data line |
### BME280/SGP41
| ESP32 Pin | Sensor Pin | Description |
|:-:|:-:|:--|
| `3v3`(BUS) | `Vcc` | The BME280 runs off of 3.3V. |
| `GND`(BUS)| `GND` | Ground |
| `IO22` |  `SCL` | I2C clock line |
| `IO21`| `SDA` | I2C data line |
| `DNC`| `SDO` | Ignore, Do not connect |
| `DNC`| `CSB` | Ignore, Do not connect |

### Dependencies

We developed the Sensor module in Arduino IDE version 1.8.19, since this version accommodated all of our libraries
####Libraries
```
#include <WiFiManager.h> 
#include <WiFi.h>
#include <ESPAsyncWebServer.h>
#include <Adafruit_Sensor.h>
#include <Adafruit_BME280.h>
#include <NOxGasIndexAlgorithm.h>
#include <SensirionI2CSgp41.h>
#include <VOCGasIndexAlgorithm.h>
#include <Wire.h>
#include <time.h>
#include "PMS.h"
```
These are the libraries used for the Outdoor module. ESPAsyncWebServer.h Must be downloaded as a .zip library <br>
# How to Download and Install `.zip` Libraries in Arduino IDE

Follow these steps to add `.zip` libraries to your Arduino environment:

## 1. Download Library
- Download the desired library in `.zip` format to your computer.

## 2. Open Arduino IDE
- Launch the Arduino software.

## 3. Add Library
- Navigate to: `Sketch` > `Include Library` > `Add .ZIP Library...`.
- Browse and select the downloaded `.zip` file.
- Click 'Open'.

## 4. Verify Installation
- Restart the Arduino IDE.
- Check for the new library under: `File` > `Examples`.

## 5. Use the Library
- In your sketches, select: `Sketch` > `Include Library` > [Your Library Name].

---

Your library should now be successfully added to the Arduino IDE!

* Describe any prerequisites, libraries, OS version, etc., needed before installing program.
* ex. Windows 10

### Installing

* How/where to download your program
* Any modifications needed to be made to files/folders

### Executing program

* How to run the program
* Step-by-step bullets
```
code blocks for commands
```

## Help

Any advise for common problems or issues.
```
command to run if program contains helper info
```

## Authors

Contributors names and contact info

Arav Sharma <br>
Isaac Amar <br>
Manhim Liu <br>
Jonas Margono

## Version History

* 0.2
    * Various bug fixes and optimizations
    * See [commit change]() or See [release history]()
* 0.1
    * Initial Release

## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details

## Acknowledgments

Inspiration, code snippets, etc.
 
