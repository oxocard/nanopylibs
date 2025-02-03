# DHT20 NanoPy Library

Library for the DHT20 temperature and humidity sensor.

## Usage

To be able to use the library, you need to import it and create a sensor object.  
Then you can call the init method to initialize the sensor.

The library code (dht20.npy) has to be loaded on the Device before using the library.

```python
# Import the sensor lib
import dht20

# Create a sensor object
sensor:DHT20

# read the data ( array with temp and humi value)
data = sensor.readData()

clear()
drawTextCentered(120, 80, data[0] + " °C")
drawTextCentered(120, 160, data[1] + " %RH")
update()
```

To see a full examples, check the examples folder.

## Description

The DHT20 class provides methods to read the temperature and humidity from the sensor.

### Methods

- `init`: Initializes the UART interface
- `readData`: Reads the temperature and humidity from the sensor

### init()

The `init` method initializes the UART interface.  
The method returns a boolean value, true if the initialization was successful, false otherwise.

```python
sensor:DHT20
sensor.init()
```

### readData()

The `readData` method returns an array with the temperature and humidity values.

```python
sensor:DHT20
data = sensor.readData()
temp = data[0]
humi = data[1]
```
