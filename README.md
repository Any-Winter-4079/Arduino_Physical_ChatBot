# Arduino Physical ChatBot

## Demo

## Description

## Setup

### Computer

Clone (and cd into) the repository:

```
git clone https://github.com/Any-Winter-4079/Arduino_Physical_ChatBot.git
cd Arduino_Physical_ChatBot
```

Create a virtual environment:

```
python -m venv venv
```

Activate the virtual environment:

- Windows: `venv\Scripts\activate`
- macOS/Linux: `source venv/bin/activate`

Install the dependencies:

```
pip install -r requirements.txt
```

### Robot

Install the Arduino IDE

Install esp32 by espressif into Boards Manager

Add:

- https://github.com/me-no-dev/AsyncTCP
- https://github.com/me-no-dev/ESPAsyncWebServer

into `XXXX/Arduino/libraries` (e.g. `Users/you/Documents/Arduino/libraries/` on macOS) for an async web server to send the images to your computer (to go from 1 fps to 37 fps at (320x240) resolution)

#### ESP32

To allow your ESP32s to communicate with your computer in your local network, replace:

```
const char* ssid1 = "****";
const char* password1 = "****";
IPAddress staticIP1(*, *, *, *);
IPAddress gateway1(*, *, *, *);
```

with your primary network (e.g. your home Wi-Fi) details

And replace:

```
const char* ssid2 = "****";
const char* password2 = "****";
IPAddress staticIP2(*, *, *, *);
IPAddress gateway2(*, *, *, *);
```

with your secondary (backup) network (e.g. phone hotspot)

Then, for each of your 2 cameras (e.g. AiThinker, M5StackWide) and WROVER (e.g. Freenove), flash (through their USB type C or VCC/GND/TX/RX) `esp32/XXXX/production.ino` (e.g. `esp32/m5stackwide/production.ino`) with the following `Tools` setup:

```
Board: "ESP32 Dev Module"
Port: "/dev/cu.usbserial-110" (select your own)
CPU Frequency: "240MHz (WiFi/BT)"
Core Debug Level: "None"
Erase All Flash Before Sketch Upload: "Disabled"
Events Run On: "Core 1"
Flash Frequency: "80MHz"
Flash Mode: "QIO"
Flash Size: "4MB (32Mb)"
JTAG Adapter: "Disabled"
Arduino Runs On: "Core 1"
Partition Scheme: "Huge APP (3MB No OTA/1MB SPIFFS)"
PSRAM: "Enabled"
Upload Speed: "115200"
```

#### Arduino Uno

Flash (through its USB type B) `arduino/production.ino` with the RX pin temporarily disconnected

## Usage

## License

MIT
