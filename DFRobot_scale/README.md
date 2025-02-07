# DFRobot Weight Sensor NanoPy Library

Library for the Gravity: I2C 1Kg Weight Sensor Kit - HX711 [SKU: KIT0176](https://www.dfrobot.com/product-2289.html).

### Wiki

https://wiki.dfrobot.com/HX711_Weight_Sensor_Kit_SKU_KIT0176

## Usage

To be able to use the library, you need to import it and create an object.  
Then you can call the init method to initialize the weight sensor.

The library code (weight_sensor.npy) has to be loaded on the Device before using the library.

```python
import weight_sensor

myScale:WeightSensor
myScale.init()

while true:
    delay(100)
    clear()
    drawTextCentered(120, 120, myScale.getWeight() + "g")
    update()
```

To see a more examples, check the examples folder.

## Description

The WeightSensor class provides methods to read, calibrate or zero the weight.

### Methods

- `init`: Initializes the sensor
- `getWeight`: Reads the weight from the sensor
- `tare`: Tares (set to zero) the sensor
- `calibrate`: Calibrates the sensor

### init()

The `init` method initializes the sensor.

```python
myScale:WeightSensor
myScale.init()
```

### getWeight()

The `getWeight` method returns the weight in grams from the sensor.

```python
myScale:WeightSensor
weight:int = myScale.getWeight()
```

### readALS()

The `tare` method tares (set to zero) the weight sensor.

```python
myScale:WeightSensor
myScale.tare()
```

### calibrate(ref:int)

The `calibrate` method calibrates the sensor.  
For the sensor to calibrate the weight, you need to calibrate it with a known weight.  
The value of the known weight has to be passed as a parameter in grams.

```python
myScale:WeightSensor
myScale.calibrate(100)
```
