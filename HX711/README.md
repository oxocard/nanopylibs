# HX711 Load Cell Amplifier

Library for the HX711 Load Cell Amplifier

### Data Sheet

https://download.bastelgarage.ch/Datasheet/HX711_Datasheet.pdf

## Usage

To be able to use the library, you need to import it and create an object.  
Then you can call the init method to initialize the sensor.

The library code (hx711npy) has to be loaded on the Device before using the library.

```python
import hx711

myScale:HX711
myScale.init(C_PIN_01, C_PIN_02)
myScale.tare()

while true:
    delay(100)
    clear()
    drawTextCentered(120, 120, myScale.getWeight() + "g")
    update()
```

To see a more examples, check the examples folder.

## Calibration

For the sensor to be able to read the weight precisely, it needs to be calibrated with a reference weight.  
See method `calibrate` for more information.

## Description

The HX711 class provides methods to read, calibrate or zero the weight.

### Methods

- `init`: Initializes the sensor
- `getWeight`: Reads the weight from the sensor
- `tare`: Tares (set to zero) the sensor
- `calibrate`: Calibrates the sensor

### init(sckPin:byte, dtPin:byte)

The `init` method initializes the sensor.  
It needs the pins for the clock (SCK) and the data pin (DT)

```python
myScale:HX711
myScale.init(C_PIN_01, C_PIN_02)
```

### getWeight()

The `getWeight` method returns the weight in grams from the sensor.

```python
myScale:HX711
myScale.init(C_PIN_01, C_PIN_02)
weight:int = myScale.getWeight()
```

### tare()

The `tare` method tares (set to zero) the weight sensor.  
Call this method after initialization or e.g. on button press.

```python
myScale:HX711
myScale.init(C_PIN_01, C_PIN_02)
myScale.tare()
```

### calibrate(ref:float)

The `calibrate` method calibrates the sensor.  
For the sensor to calibrate the weight, you need to calibrate it with a known weight.  
The value of the known weight has to be passed as a parameter in grams.

```python
myScale:HX711
myScale.init(C_PIN_01, C_PIN_02)
myScale.calibrate(1000)
```
