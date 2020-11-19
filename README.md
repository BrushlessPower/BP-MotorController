# BP-MotorControler
Public Documentation for the Brushless Power Motor Controller

# Prototype Versions
## Version 0.0
- MCU STM32F405 or STM32F051 (BlHeli_32)
- Step Down for 5V BEC
- Step Down for 12V Gate Driver Voltage
- Step Down for 3,3v MCU Voltage
- Issues: BEC to weak (50mA)
- No Frimware

## Version 0.28
- MCU STM32F051 (BleHeli_32) + ATMega328P (Telemetry) + ATMega328P (Logging)
- Step Down for 5V BEC
- Charge Pump from 5V BEC to 12V Gate Driver Voltage
- LDO 3,3V from 5V BEC
- SD-CARD
- Issues: 3,3V to weak for SD-Card, 5V BEC to weak (1A...1,5A)
- No Public Firmware

## Version 0.32 (untested)
- MCU STM32F051 (BlHeli_32 or AM32) + ESP32 (BLE+Telemetry+Logging)
- Step Down for 5V BEC
- Step Down for 5V Internal
- Charge Pump from 5V Internal to 12V Gate Driver Voltage
- LDO 3,3V from 5V Internal
- LDO 3,3v from 5V BEC (for SD-Card)
- SD-CARD
- Firmware in Development (actual V0.5)

# Firmware V0.5
For Hardware Version 0.32 on ESP32
- Logging internal and external Values to SD-Card
- BEC Voltage scalable with DAC
- Transmit Telemetry Data to Futaba
- BLE & USB Connection to BlHeli_32 Suite/App for config Motor Parameters
- USB Connection for BlHeli Configurator with AM32 Firmware
- Servo Input (with Failsafe) and Servo Output for ESC

## Bugs
- Step Down Voltage Sensing not working (Hardware)
- ADC2 - Wifi Bug (ESP32 Bug)

## Comming Soon
- DShot Output for ESC
- Brushless Power App Support
- liite Bug fixes
