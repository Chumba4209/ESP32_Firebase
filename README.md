# ESP32 BMP180 + Firebase  with WiFiManager

This project uses an **ESP32**, **BMP180 sensor**, and **OLED display** to collect environmental data (temperature and pressure), display it on the screen, and upload it to **Google Firebase Firestore**. It uses **WiFiManager** to configure WiFi and Firebase credentials at runtime, allowing flexible and portable deployments.



##  Features

- 📡 WiFiManager for runtime WiFi and Firebase config
- 🌡 Reads **temperature** and **pressure** from BMP180 sensor
- ☁ Uploads readings to **Firebase Firestore**
- 🖥 Displays readings on a 128x64 **OLED screen**
- 🔄 Auto reconnects and uploads data every 10 seconds



##  Hardware Required

| Component           | Quantity |
|---------------------|----------|
| ESP32 Board         | 1        |
| BMP180 Sensor       | 1        |
| OLED Display (SSD1306, 128x64) | 1        |
| Breadboard + Jumper Wires | 1 set    |

### 🔌 Default I2C Pins for ESP32

| Signal | GPIO |
|--------|------|
| SDA    | 23   |
| SCL    | 22   |



##  Libraries Used

Install the following libraries via the Arduino Library Manager:

- `WiFiManager by tzapu`
- `Firebase ESP Client by Mobizt`
- `Adafruit BMP085 Unified`
- `Adafruit GFX Library`
- `Adafruit SSD1306`
- `Wire` (default)



##  Firebase Setup

1. Go to [Firebase Console](https://console.firebase.google.com)
2. Create a new **project**
3. Enable **Email/Password Authentication**
4. Enable **Cloud Firestore** and start in test mode
5. Create a test user with:
   - Email: `your_email`
   - Password: `your_password`
6. Get your **Web API Key** from **Project Settings → General**

###  Required Inputs in WiFiManager Portal:
- Firebase API Key
- Firebase Project ID
- User Email
- User Password


##  How to Use

1. Flash the code to your ESP32
2. Power the board
3. Connect to the hotspot `BMP180Config`
4. Enter:
   - Your Wi-Fi SSID and password
   - Firebase API Key
   - Firebase Project ID
   - User Email and Password
5. Click **Save**, and the ESP32 will reboot and connect to WiFi and Firebase



##  Data Structure in Firestore

- **Collection**: `EspData`
- **Document**: `BMP180`
- **Fields**:
  - `Temperature` (stringValue)
  - `Pressure` (stringValue)


## Oled Output

Shows real time values:

BMP180
Temp: 23.45 C
Pres: 1002.75 hPa

## Serial Monitor Output

Connecting to WiFi...
Connected: 192.168.1.145
Temp: 23.45 C
Pres: 1002.75 hPa
Updating Firestore... ok




