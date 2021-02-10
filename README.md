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
- You will need an FTDI module to upload your code. 
- Instead of FTDI, You can upload your code using an arduino UNO with the following connection*:
  ```
  RESET Arduino ------------- GND Ardunio 
  3.3   Arduino ------------- 3v  Esp32CAM 
  GND   Arduino ------------- GND Esp32CAM
  RX    Arduino ------------- VOR Esp32CAM (this is not a mistake RX to rx & TX to tx)
  TX    Arduino ------------- VOT Esp32CAM
  IO0   Esp32CAM ------------ GND Esp32CAM
  ```
  *(**NOTE:**)For this to work you may need to: **1)** Press the reset button **2)** Upload the code **3)** Remove the jumper connected to IO0 **4)** Press the reset button
