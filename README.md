# RTOS_HomeOffice


## Overview

This project is an embedded system application developed using the STM32 microcontroller. It includes functionalities such as ADC, RTC, UART, and PWM control along with FreeRTOS-based task management. The main features of this project include:

- **Temperature and Humidity Monitoring** using a DHT11 sensor.
- **Intruder Detection** mechanism.
- **LED Blinking Control**.
- **System Clock and RTC Configuration**.
- **Task and Semaphore Management** using FreeRTOS.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Hardware Requirements](#hardware-requirements)
3. [Software Requirements](#software-requirements)
4. [Configuration](#configuration)
5. [Project Structure](#project-structure)
6. [Features and Functionalities](#features-and-functionalities)
7. [How to Build and Run](#how-to-build-and-run)
8. [License](#license)

## Getting Started

To get started with this project, you will need the following hardware and software tools:

### Hardware Requirements

- STM32 Microcontroller (e.g., STM32F4 Series)
- DHT11 Temperature and Humidity Sensor
- LEDs and other GPIO peripherals
- UART Serial Debugger (e.g., USB to UART converter)
- Breadboard and jumper wires
- Power supply (5V or 3.3V, depending on your setup)

### Software Requirements

- [STM32CubeMX](https://www.st.com/en/development-tools/stm32cubemx.html)
- [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) or any IDE that supports STM32 development
- FreeRTOS
- [HAL (Hardware Abstraction Layer) libraries](https://www.st.com/en/embedded-software/stm32cube-mcu-packages.html)

## Configuration

The following configurations have been made in this project:

- **ADC (Analog to Digital Converter):** Configured for single conversion mode for reading analog sensors.
- **RTC (Real-Time Clock):** Configured to maintain real-time.
- **TIM (Timers):** Configured for PWM control and periodic interrupt generation.
- **UART (Universal Asynchronous Receiver-Transmitter):** Configured for serial communication with baud rate set to 115200.

## Project Structure

The project files are organized as follows:

- **main.c:** Main application code.
- **cmsis_os.h:** Header file for CMSIS-RTOS API.
- **Peripheral Drivers:** Includes files for UART, GPIO, TIM, ADC, and RTC initialization and configuration.
- **FreeRTOS Tasks:**
  - **defaultTask:** Main entry task of the application.
  - **led_blink:** Task to control LED blinking.
  - **countUp_init and CountDownInit:** Tasks for counting mechanisms.
  - **Intruder Detection Task:** Task to handle intruder detection using a sensor.
  - **Temperature Monitoring Task:** Task to monitor and process temperature data.

## Features and Functionalities

1. **Temperature Monitoring:**
   - Utilizes the DHT11 sensor to read temperature and humidity data.
   - Processes and displays data via UART.

2. **Intruder Detection:**
   - A separate task for handling intruder detection.
   - Uses a GPIO pin as an interrupt to trigger intruder alerts.

3. **LED Blinking Control:**
   - A dedicated task to manage LED blinking using PWM and GPIO control.

4. **Real-Time Clock:**
   - Configured to maintain and provide real-time clock functionalities.
   - Alarm functionalities are also configured.

5. **Task and Semaphore Management:**
   - Uses FreeRTOS for task management.
   - Semaphores are created for task synchronization.

## How to Build and Run

1. Open the project in STM32CubeIDE or any compatible IDE.
2. Connect your STM32 board to your PC via USB or Serial Debugger.
3. Load the project to your board.
4. Open a Serial Terminal (e.g., PuTTY or Tera Term) with the appropriate baud rate (115200) to view the UART output.
5. Build the project and flash it to your STM32 board.
6. Monitor the Serial Terminal to see temperature data, intruder detection messages, and other status updates.

## License

This project is licensed under the STMicroelectronics Software License. For more details, see the [LICENSE](./LICENSE) file in the root directory.

