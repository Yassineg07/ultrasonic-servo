# Ultrasonic Servo Control System

## Overview

This project implements a distance-responsive servo control system using an STM32F407VG microcontroller. The system uses an ultrasonic sensor to measure distance and dynamically adjusts a servo motor's position based on the detected distance. The closer an object gets to the sensor, the more the servo rotates, creating an interactive distance-to-angle mapping system.

## Hardware Components

- **MCU**: STM32F407VGTx
- **Sensors**: Ultrasonic distance sensor (HC-SR04 or similar)
- **Actuators**: Servo motor
- **Communications**: UART (for debugging and monitoring)

## Features

- Real-time distance measurement using ultrasonic sensor (2cm - 200cm range)
- Smooth servo movement with configurable step sizes
- Distance to servo angle mapping (maps 5cm-30cm to full servo range)
- Invalid reading filtering and timeout protection
- Serial output of distance, position, and angle information

## Pin Configuration

- **PA0**: Ultrasonic sensor trigger pin
- **PA1**: Ultrasonic sensor echo pin
- **PE9**: Servo control signal (TIM1_CH1)
- **PA2/PA3**: UART TX/RX for debugging

## How It Works

1. The ultrasonic sensor sends sound pulses and measures the time until the echo returns
2. The system calculates the distance based on the echo time
3. Distance is mapped to a servo position (angle)
4. Servo moves gradually toward the target position for smooth operation
5. Current distance, servo position, and angle are transmitted over UART

## Setup and Usage

1. Connect the ultrasonic sensor (trigger to PA0, echo to PA1)
2. Connect the servo motor control wire to PE9
3. Connect a serial terminal to UART2 (PA2/PA3) at the standard baud rate
4. Power the system and observe the servo responding to distance changes

## Development Environment

- STM32CubeIDE
- STM32CubeMX for peripheral configuration
- STM32F4xx HAL drivers

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For questions or support, please open an issue or contact [Yassineg07](mailto:gharbiyasine040@gmail.com).