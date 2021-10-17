# Bluetooth-controlled-arduino-car-with-obstacke-avoidance-
This prototype is a Bluetooth controlled car which uses an ultrasonic sensor to determine the distance of the obstacle. This car also helps by offering parking assistance.
# Working of the Car
When the power of the car is switched on the Arduino first establishes the Bluetooth connection with the phone using the HC-05 Bluetooth module at a serial baud rate of 9600 bits/s. The phone is connected to the car and then the command from the app is transmitted to the Arduino through the Bluetooth module. The command from the app  is then processed in the Arduino.
If the command from the app is forward or ‘F’ then the pins where the forward motors are connected in the motor driver are given a high voltage. Hence the forward motors are activated, and the car starts moving forward. Simultaneously the forward ultrasonic sensors are also activated, and it checks the forward distance. If the forward distance is ever found to be less than 20cm then the Arduino immediately gives low voltage to all the pins of the motor driver. Hence the motor driver stops all the motors, and the car comes to a stop. If the command from the app is backward or ‘B’ then the pins where the rear motors are connected in the motor driver are given a high voltage. Hence the backward motors are activated, and the car starts moving backward. Simultaneously the backward ultrasonic sensors are also activated, and it checks the backward distance. If the backward distance is ever found to be less than 20 cm then the Arduino immediately gives low voltage to all the pins of the motor driver and the motor driver stops all motors and the car comes to a stop. When the backward motors are activated the parking assistance also gets activated. If the parking assistance find the backward distance less than 30 cm then only 1 LED light is activated, if the distance is less than 25 cm then 2 LED are activated while if the distance is less than 20 cm then the car comes to a stop and all 3 LEDs are activated.
If the command from the app is left or ‘L’ then the pins where the right motors are connected in the motor driver are given a high voltage while the left motors are kept at low voltage. Hence the right motors are activated, and the left motors are kept stationary. This gives a torque that turns the car left.
If the command from the app is right or ‘R’ then the pins where the left motors are connected in the motor driver are given a high voltage while the right motors are kept at low voltage. Hence the left motors are activated, and the right motors are kept stationary. This gives a torque that turns the car right.
If the command from the app is stop or ‘S’ then all the pins are given a low voltage. This makes the motor driver stop all the motors if any of them are in motion.
