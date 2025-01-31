# Serial Servo NanoPy Library

Library for controlling servos via serial communication.  
This library is designed to work with the SC series of serial servos.

## Usage

To be able to use the library, you need to import it and create a SerialServoBus object.  
Then you can call the init method to initialize the UART interface.

The library code (serial_servo.npy) has to be loaded on the Device before using the library.

```python
# Import serial servo lib
import serial_servo

# Create serial servo bus object
servoBus:SerialServoBus

# Call init to initialize the UART interface
#              Tx Pin    Rx Pin   Baudrate
servoBus.init(C_PIN_01, C_PIN_02, 1000000)

# Set the position of a servo
#                  ID, Pos, Speed
servoBus.setPosition(1, 0, 500)
```

To see more examples, check the examples folder.

## Description

The serial servo bus class provides methods to control servos via serial communication:

### Control individual servos

- `init`: Initializes the UART interface
- `setPosition`: Sets the position of a servo in servo mode
- `getPosition`: Gets the position of a servo
- `setMotorSpeed`: Sets the speed of a servo in motor mode
- `stopServo`: Stops the servo
- `changeId`: Changes the id of a servo
- `isServoMoving`: Checks if a servo is moving
- `getLoad`: Gets the load of a servo
- `getSpeed`: Gets the speed of a servo

### Control multiple servos

- `setAllPositions`: Sets the position of all servos
- `setAllMotorSpeeds`: Sets the speed of all servos in motor mode
- `stopAllServos`: Stops all servos

TODO: Detailed description of the library
