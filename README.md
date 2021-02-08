# simple Image grabber using ESP_CAM 

The following code: 

- Connects to a WiFi Network
- Creates a server with the following endoints:
  - **\<ip addr\>/** : Index page, show full interface (param controls and stream)
  - **\<ip addr\>/capture** : Shows current image (still image) 
  - **\<ip addr\>:81/stream** : Shows current stream (video image)
  - **\<ip addr\>/status** : Fetch stream status
  - **\<ip addr\>/control** : Fetch current settings

- Grabs images and deliver to the respective endpoints (capure & stream) 

## notes: 
- Arduino IDE must comply with the following settings:

  ```
  - Board: ESP32 Wrover Module
  - Upload Speed: 115200
  - Flash Frequency: 40 Mhz
  - Flash mode: QIO
  - Partition Scheme: Huge APP (3MB no OTA/1MB SPIFFS)
  ```
  
- Using: 
  
  ```
  - CAMERA_MODEL_AI_THINKER
  - 10348970
  ```
  
