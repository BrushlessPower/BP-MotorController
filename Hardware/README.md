# Prototype Versions

Hardware is developed with Eagle (HW up to V0.32) and with Altium Designer (HW 1.0)

## Version 0.0
- MCU STM32F405 or STM32F051 (BlHeli_32)
- Step Down for 5V BEC
- Step Down for 12V Gate Driver Voltage
- Step Down for 3,3v MCU Voltage
- Issues: 5V BEC to weak (50mA)
- No Logging, No Limits (Stock BlHeli_32)
- One ESC still working in a F1-E (+1kg) with around 160A and 8S (my own)

## Version 0.28
- MCU STM32F051 (BleHeli_32) + ATMega328P (Telemetry) + ATMega328P (Logging)
- Step Down for 5V BEC
- Charge Pump from 5V BEC to 12V Gate Driver Voltage
- LDO 3,3V from 5V BEC
- SD-CARD
- Issues: 3,3V to weak for SD-Card, 5V BEC to weak (1A...1,5A)
- No Public Firmware
- 2 ESC's still working in F1-E (+1kg) with 220A/8S and 180A/6S

## Version 0.32
- MCU STM32F051 (BlHeli_32) + ESP32 (BLE+Telemetry+Logging)
- Step Down for 5V BEC
- Step Down for 5V Internal
- Charge Pump from 5V Internal to 12V Gate Driver Voltage
- LDO 3,3V from 5V Internal
- LDO 3,3v from 5V BEC (for SD-Card)
- SD-CARD
- USB
- Firmware in Development (actual V0.9.17)
- 3 ESC's running -> F1-E with 280A/10S; F3-E with 50A/4S (my own); F1-E planned

## Version 1.0
- Hardware similar Version 0.32 with Bug fixes
- 12V Gate Drive Voltage from HV LDO from Lipo
- Step Down for 5V BEC (3A) adjustable Voltage
- Step Down for 3V3 Internal
- SD Card
- No USB
- Firmware not tested (Hardware not ready)

