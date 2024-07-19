# Tunerpro-serial-WB
Tunerpro data acquisition plugin for ECU + WideBand O2 sensor with serial port connection.
Works like Tunerpro Data Acquisition plugin, but returns WB O2 value with command "WBO2"

Beta software, use at your own risk!
Please report any results, success or failure to: joukoy@gmail.com

* Requires VC++ 2019 runtime: https://aka.ms/vs/17/release/vc_redist.x86.exe


 # Add wideband O2 to definition:
 * Commands -> Add New Item -> Send command
   - Title: Request AFR
   - ASCII string: WBO2
 * Commands -> Add new Item -> Listen for packet/Response
   - Title: Receive AFR
   - Process data
   - Body size: 2
   - Payload size 2
* Values -> Add new Item
  - Source data size: 16 Bit
  - Command Association: Receive AFR
  - Conversion for AEM: X/10
  - Conversion for Innovate: (X/1000 + 0.5) * 14.7
  - Conversion for PLX: (X/25.5) + 10

  
