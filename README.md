# Welcome to SWAKES - Home Assistant

Hi there and welcome to my Github repo containing my configuration and setup files/code for Home Assistant. I will en-devour to keep this up to date however please check out my other references and sources in the following links before

 - [SWAKES Blog](https://hmas.swakes.co.uk/tag/home-assistant/)
 - [SWAKES Reddit](https://old.reddit.com/user/swake88/)
 - [SWAKES Home Assistant Community](https://community.home-assistant.io/u/pqpxd/summary)
 - [Home Assistant Facebook Community Page](https://www.facebook.com/groups/HomeAssistant)
 - [Screenshots](https://github.com/pqpxo/SWAKES_hassio/tree/master/screenshots)

Please note that some files, images, custom components and addons have been referenced but not uploaded in this repo.

If you like what you've read ... Support me here on Buy Me a Coffee: https://www.buymeacoffee.com/swakes

### 16/10/2020 - Updated 'dashboards' and Screenshots

#### Screenshots
![System Dashboard](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/NEW_System_Dashboard.png)![Light Dashboard](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/NEW_Lights_Dashboard.png)![Security Dashboard](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/NEW_Security_Dashboard.png)![Media Dashboard](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/NEW_Media_Dashboard.png)

## **Security Dashboard (Mobile)**
![enter image description here](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/sec1.jpg?raw=true)
![enter image description here](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/sec2.jpg?raw=true)
![enter image description here](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/sec3.jpg?raw=true)![enter image description here](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/sec4.jpg?raw=true)

## **Dashboards In Progress**
![enter image description here](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/temp1.jpg?raw=true)![enter image description here](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/temp2.jpg?raw=true)


# Hardware


## Operating System

#### Ubuntu Sever 18 Virtual Machine (ESXi)     
 - 1vCPU
 - 3GB RAM
 - 40GB HDD

#### HASSIO Supervisor
 - Docker Image

#### Add-Ons
- AppDaemon
- Dasshio
- ESPHome
- File editor
- Frigate NVR
- Home Assistant Google Drive Backup
- MariaDB
- Mosquitto broker
- Network UPS Tools
- SSH & Web Terminal
- TasmoAdmin

#### Integrations
- Alarmo
- Broadlink
- Browser mod
- Google Cast
- Coronavirus (COVID-19)
- deCONZ
- ESPHome
- ESXi Stats
- Fully Kiosk Browser
- Garbage Collection
- Google Calendars
- Google Assistant
- HACS
- Hyperion
- Meteorologisk institutt (Met.no)
- Mobile App
- Monitor Docker
- Mopidy
- MQTT
- Nest
- OpenWeatherMap
- Plex Media Server
- Radarr
- Sonarr
- Speedtest.net
- Spotify
- Tasmota
- TP-Link Kasa Smart
- Transmission
- UniFi Network
- UniFi Protect
- Waze Travel Time
- WLED
- Xbox
- Yeelight 

#### HACS (Integrations)
- Alarmo
- Anniversary
- Authenticated
- Auto Areas
- browser_mod
- ESXi Stats
- Event sensor
- Frigate
- Fully Kiosk Browser
- Garbage Collection
- Google Home
- Holidays
- Monitor Docker
- Mopidy Media Player component
- Plex Recently Added
- Radarr Upcoming Media
- Sonarr Upcoming Media
- Spotcast
- Spotify Playlist Sensor

#### HACS (Frontend)
- Alarmo
- Battery State Card / Entity Row
- Button Text Card
- button-card
- Custom Animated Weather Card
- Custom brand icons
- Dark Thermostat
- ESXi Stats
- Flexible Horseshoe Card for Lovelace
- Garbage Collection Card
- HA Dashboard
- layout-card
- Light Entity Card
- Number Box
- Select list Card
- Simple Thermostat
- Slider Button Card
- slider-entity-row
- state-switch
- Switch popup card
- Text Divider Row
- Toggle Control Button Row

## Devices
### Lights

|  **Device** | Connectivity  | Amount  |
| - | ------------ |  :------------: |
| TRADFRI bulb E27  | Zigbee (deCONZ)  | 5 |
| TRADFRI bulb GU10 | Zigbee (deCONZ) | 21 |
| Lidl HG06106C | Zigbee (deCONZ) | 2 |
| WS2812b RGB Strip  | WiFi (ESPHome/WLED)  | 10 |
| Sonoff Basic R2  | WiFi (Tasmota)  | 2 |
| Hyperion (Raspberry Pi)  | WiFi (Integration)  | 2 |

### Sensors

|  Device | Connectivity  | Amount  |
| - | ------------ |  :------------: |
| Aqara Contact Sensor  | Zigbee (deCONZ)  | 15  |
| Aqara Temp/Humidity Sensor  | Zigbee (deCONZ)  | 5  |
| IKEA TRADFRI Motion Sensor | Zigbee (deCONZ)  | 3 |
| Sonoff Motion Sensor (SNZB-03)  | Zigbee (deCONZ)  | 1  |
| KERUI Motion Sensor  | 433Mhz (Tasmota)  | 3  |
| KERUI Contact Sensor  | 433Mhz (Tasmota)  | 1  |
| Philips Hue Motion/Temp/Light  Sensor  | Zigbee (deCONZ)  | 1  |
| IKEA VINDRIKTNING (Air Quality Sensor)  | WiFi (ESPHome)   | 1  |
| HC-S501/S505 Motion Sensor | WiFi (ESPHome)  | 8  |
| DHT22/DS18B20 Temp/Humidity Sensor | WiFi (ESPHome)  | 5  |
| Weight Sensor (HX711) | WiFi (ESPHome)  | 1  |
| Fingerprint Sensor (R503) | WiFi (MQTT)  | 1  |
| EMASTIFF Smoke Alarm  | 433Mhz (Tasmota)  | 1  |

### Switches

|  Device | Connectivity  | Amount  |
| - | ------------ |  :------------: |
| Heiman Smart Plug (TS011F)   | Zigbee (deCONZ)  | 2  |
| SmartThings Smart Plug (D0005)   | Zigbee (deCONZ)  | 2  |
| TP-Link Smart Plug (KP105/KP303)   | WiFi (HA Integration)  | 3  |
| 5V Relay Module (SRD-05VDC-SL-C)   | WiFi (ESPHome)  | 3  |
| Sonoff Basic R2  | WiFi (Tasmota)  | 3 |
| Electric Blinds  | 433Mhz (Tasmota)  | 1 |
| Smart Air Freshener  | WiFi (ESPHome)  | 1 |
| LEGO Train  | WiFi (MQTT)  | 1 |

### Remotes

|  Device | Connectivity  | Amount  |
| - | ------------ |  :------------: |
| IKEA TRADFRI Remote Control | Zigbee (deCONZ)  | 2 |
| IKEA TRADFRI Dimmer | Zigbee (deCONZ)  | 1 |
| 3 Button Remote | 433Mhz (Tasmota)  | 1 |
| Broadlink R3 Mini | WiFi (Integration)  | 1 |

### Cameras

|  Device | Connectivity  | Amount  |
| - | ------------ |  :------------: |
| Ubiquiti G3 Bullet (UVC-G3-BULLET) | LAN (UniFi Protect)  | 2 |
| Ubiquiti G3 Flex (UVC-G3-FLEX) | LAN (UniFi Protect)  | 1 |
| ESP32-CAM (OV2640) | WiFi (ESPHome)  | 1 |
| Amazon Fire Tablet 7 (Onboard) | WiFi (Integration)  | 1 |

### Media

|  Device | Connectivity  | Amount  |
| - | ------------ |  :------------: |
| Google Home Mini Speaker  | WiFi (Integration)  | 3 |
| Google Home Speaker  | WiFi (Integration)  | 1 |
| Google Nest Hub  | WiFi (Integration)  | 1 |
| Google Chromecast  | WiFi (Integration)  | 1 |
| Raspberry Pi (Mopidy) | WiFi (LAN)  | 2 |
| Xbox Series S | WiFi (LAN)  | 1 |

### Network

|  Device | Connectivity  | Amount  |
| - | ------------ |  :------------: |
| Ubiquiti Dream Machine Pro (UDM-PRO)  | LAN (Integration)  | 1 |
| Ubiquiti UniFi 16-Port PoE Switch (USW-16-POE)  | LAN (Integration)  | 1 |
| Ubiquiti UniFi 5-Port PoE Switch (USW-Flex-Mini)  | LAN (Integration)  | 1 |
| Ubiquiti UniFi AP AC LR (UAP-AC-LR)  | LAN (Integration)  | 2 |
| AdGuard (Raspberry Pi) | LAN (Integration)  | 1 |
| Sonoff RF Bridge (Tasmota) | WiFi (MQTT)  | 1 |
| Raspberry Pi (deCONZ - Conbee II) | WiFi (Integration)  | 1 |

### Others

|  Device | Connectivity  | Amount  |
| - | ------------ |  :------------: |
| APC Smart-UPS (1000va)  | USB (Addon)  | 1 |
| Pi-KVM (Raspberry Pi)  | LAN (MQTT)  | 1 |
| Epson XP-4100 Printer (XP-4100)  | WiFi (Integration)  | 1 |
| Fire Tablet 7 (Fully Kiosk Browser)  | WiFi (Integration)  | 1 |
| Touchscreen Display (Raspberry Pi)  | WiFi (Dashboard)  | 1 |
| Dell PowerEdge T330 (ESXi)  | LAN (Integration)  | 1 |
| Lenovo ThinkCenter PC (Windows 11)  | LAN (MQTT)  | 1 |
