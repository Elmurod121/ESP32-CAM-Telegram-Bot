ESP32-CAM Telegram Bot
Overview
This project implements an IoT-based system using the ESP32-CAM module to create a Telegram bot for remote image and video capture. Users can send commands (/photo, /video) via Telegram to capture images or 5-second videos, which are sent back as GIFs.
Features

Capture images with /photo command (320x240 resolution).
Record 5-second videos with /video command (15 fps, sent as GIF).
Stable Wi-Fi connectivity (2.4 GHz).
Telegram bot integration for remote control.
Error handling for network and memory issues.

Hardware Requirements

ESP32-CAM (AI Thinker model with OV2640 camera)
Arduino Uno (for programming)
Breadboard and jumper wires
USB cable (Micro-USB, 5V)

Software Requirements

Arduino IDE (version 1.8.19 or higher)
Libraries:
WiFi.h
WiFiClientSecure.h
UniversalTelegramBot.h (version 1.3.0)
esp_camera.h



Setup Instructions

Hardware Setup:

Connect the ESP32-CAM to the Arduino Uno: GND to GND, 5V to 5V, RX/TX pins for serial communication.
Configure camera pins: PWDN_GPIO_NUM (32), XCLK_GPIO_NUM (0), etc.
Upload code using the Arduino Uno.


Wi-Fi Configuration:

Update the SSID and password in the code (Mama and 19962003 in this project).


Telegram Bot Setup:

Create a bot via @BotFather on Telegram to get a token.
Get your Chat ID using @myidbot.
Update the BOT_TOKEN and CHAT_ID in the code.


Install Libraries:

Install the required libraries in Arduino IDE via the Library Manager.


Upload Code:

Upload the code to the ESP32-CAM using Arduino IDE.



Usage

Send /start to the bot for instructions.
Use /photo to capture and receive an image.
Use /video to capture and receive a 5-second GIF.
Use /flash to toggle the ESP32-CAM flash LED.

Code Structure

setup(): Initializes Wi-Fi, camera, and bot.
loop(): Checks for new Telegram messages.
sendPhotoTelegram(): Sends images to Telegram.
sendVideoTelegram(): Sends videos as GIFs.
handleNewMessages(): Processes bot commands.

Known Issues

Memory limitations may cause video capture failures; reduce frame quality if needed.
Requires a stable 2.4 GHz Wi-Fi connection (signal strength > -60 dBm).

Future Improvements

Add SD card support for video storage.
Integrate OpenCV for motion detection.
Implement Deep Sleep mode for power saving.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgments
Thanks to the Arduino and Telegram communities for their resources and support.
