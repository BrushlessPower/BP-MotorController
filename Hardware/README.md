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

## Version 0.32
- MCU STM32F051 (BlHeli_32 or AM32) + ESP32 (BLE+Telemetry+Logging)
- Step Down for 5V BEC
- Step Down for 5V Internal
- Charge Pump from 5V Internal to 12V Gate Driver Voltage
- LDO 3,3V from 5V Internal
- LDO 3,3v from 5V BEC (for SD-Card)
- SD-CARD
- Firmware in Development (actual V0.8)

