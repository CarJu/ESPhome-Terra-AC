*ESPhome-Terra-AC: Optimize EV Charging with Solar Power (ABB Terra Wallbox)*

This guide details an ESPhome project designed to optimize electric vehicle (EV) charging by leveraging your home solar power production. By controlling the output power of your ABB Terra AC wallbox (TAC-W11-G5-R-0), you can prioritize utilizing excess solar energy (surplus) for charging. This approach minimizes reliance on the grid and potentially reduces charging costs.

**Focus: Practical Implementation**
This guide assumes you're already familiar with flashing ESPhome and using variables in Home Assistant. It focuses on the practical steps of building and implementing the project.

**Required Hardware:**
Wemos D1 Mini Pro (ESP8266) or a compatible ESP chip with 3.3V and 5V power pins
TTL to RS485 converter with automatic flow control
Jumper cables
Soldering iron

**Connecting Your Hardware:**
Ground and 3.3V: Locate the JTAG connector in the upper right corner of your wallbox. Connect the ground and 3.3V pins from the ESP board to the corresponding pins on the JTAG connector.
Grounding the ESP (Important): Since the Wemos D1 Mini lacks a dedicated ground pin, create a 3-way ground jumper cable. Connect one end to the wallbox ground, another to the ESP ground, and the last one to the RS485 converter ground.
5V Power: Supply 5V power to the RS485 converter from the D1 Mini board's 5V pin.
Integration with Node-RED

The project uses Node-RED to establish communication between your ESP device and the wallbox. You can send real-time solar surplus data to the topic tac11/carport/max_power. The wallbox will then automatically adjust its output power to stay within the specified limit.

**Prioritizing Solar Energy and Grid Dependence**
This setup prioritizes using your solar surplus for charging, minimizing reliance on the grid. However, it's important to note that the wallbox directly regulates amperage, and the conversion to watts may not be perfectly accurate.

**Important Considerations:**
Minimum Charging Power: Most EVs will stop charging if the surplus falls below 4125 watts (approximately 6 amps at 400 volts).
Modbus Communication Reference: This project references the ABB Terra AC Charger Modbus Communication documentation for detailed Modbus information: https://library.e.abb.com/public/4124e0d39f614ba7b0a7a6f7a2ce1f99/ABB_Terra_AC_Charger_ModbusCommunication_v1.7.pdf

**Compatibility Notice:**
Please note that this code is specifically tested and verified with the ABB Terra wallbox model (TAC-W11-G5-R-0) running firmware version 1.8.21. Compatibility with other models or firmware versions may require adjustments.

**Additional Notes:**
This description is improved with the assistance of a large language model (Google Gemini). Feel free to contribute to this project by sharing your experiences or suggesting improvements!
