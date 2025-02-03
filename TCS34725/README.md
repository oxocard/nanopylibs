# TCS34725 NanoPy Library

Library for the TCS34725 RGB and ALS sensor.

## Usage

To be able to use the library, you need to import it and create a sensor object.  
Then you can call the init method to initialize the sensor.

The library code (tcs34725.npy) has to be loaded on the Device before using the library.

```python
rgbSensor:TCS34725
rgbSensor.init()
c:int[3] = rgbSensor.readRGB()

clear()
drawText(10, 10, "Red = " +c[0])
drawText(10, 50, "Green = " +c[1])
drawText(10, 90, "Blue = " +c[2])
update()
```

To see a more examples, check the examples folder.

## Description

The TCS34725 class provides methods to read RGB and ambient light (ALS) values from the sensor.

### Methods

- `init`: Initializes the sensor
- `readRGB`: Reads the RGB values from the sensor
- `readALS`: Reads the ALS value from the sensor

### init()

The `init` method initializes the sensor.

```python
rgbSensor:TCS34725
rgbSensor.init()
```

### readRGB()

The `readRGB` method reads the RGB values from the sensor.

```python
rgbSensor:TCS34725
c:int[3] = rgbSensor.readRGB()
```

### readALS()

The `readALS` method reads the ALS value from the sensor.

```python
rgbSensor:TCS34725
als = rgbSensor.readALS()
```
