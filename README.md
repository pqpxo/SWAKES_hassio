# Welcome to SWAKES - Home Assistant

Hi there and welcome to my Github repo containing my configuration and setup files/code for Home Assistant. I will en-devour to keep this up to date however please check out my other references and sources in the following links before

 - [SWAKES Blog](https://blog.swakes.co.uk/tag/home-assistant/)
 - [SWAKES Reddit](https://old.reddit.com/user/swake88/)
 - [SWAKES Home Assistant Community](https://community.home-assistant.io/u/pqpxd/summary)
 - [Home Assistant Facebook Community Page](https://www.facebook.com/groups/HomeAssistant)
 - [Screenshots](https://github.com/pqpxo/SWAKES_hassio/tree/master/screenshots)

Please note that some files, images, custom components and addons have been referenced but not uploaded in this repo.

<style>.bmc-button img{height: 34px !important;width: 35px !important;margin-bottom: 1px !important;box-shadow: none !important;border: none !important;vertical-align: middle !important;}.bmc-button{padding: 7px 15px 7px 10px !important;line-height: 35px !important;height:51px !important;text-decoration: none !important;display:inline-flex !important;color:#ffffff !important;background-color:#5F7FFF !important;border-radius: 8px !important;border: 1px solid transparent !important;font-size: 18px !important;letter-spacing:-0.08px !important;box-shadow: 0px 1px 2px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;margin: 0 auto !important;font-family:'Lato', sans-serif !important;-webkit-box-sizing: border-box !important;box-sizing: border-box !important;}.bmc-button:hover, .bmc-button:active, .bmc-button:focus {-webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;text-decoration: none !important;box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;opacity: 0.85 !important;color:#ffffff !important;}</style><link href="https://fonts.googleapis.com/css?family=Lato&subset=latin,latin-ext" rel="stylesheet"><a class="bmc-button" target="_blank" href="https://www.buymeacoffee.com/swakes">🍺<span style="margin-left:5px;font-size:18px !important;">Support me and Buy Me a Beer</span></a>

### 04/09/2020 - Updated 'dashboards'

#### Screenshots
![System Dashboard](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/HA-System.png)![Light Dashboard](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/HA-Lights.png)![Security Dashboard](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/HA-Security.png)![Media Dashboard](https://github.com/pqpxo/SWAKES_hassio/blob/master/screenshots/HA-Media.png)
# Hardware


## Operating System

#### Ubuntu Sever 18 Virtual Machine (ESXi)     
 - 1vCPU
 - 3GB RAM
 - 40GB HDD

#### HASSIO Supervisor
 - Docker Image

#### Add-Ons
  - ESPHome
  - File Editor
  - File Editor
  - JupyterLab Lite
  - MariaDB
  - Mosquitto Broker
  - Node-RED
  - Terminal & SSH

#### Integrations
- Alexa Media Player
- Belkin WeMo
- Certificate Expiry
- deCONZ
- ESPHome
- ESXi Stats
- Fontawesome icons
- Garbage Collection
- Glances
- Google Cast
- HACS
- Internet Printing Protocol
- Local IP Address
- Meteorologisk Institutt
- Mobile App
- MQTT
- OwnTracks
- Pi-Hole
- Plex Meda Server
- Samsung Smart TV
- Sonarr
- Sony Playstation 4
- Speedtest.net
- Transmission
- Ubiquiti UniFi
- UniFi Protect
- UPnP  

#### HACS (Integrations)
- Authenticated
- Bad Nest
- ESXi Stats
- fontawesome
- Garage Collection
- Monitor Docker
- Plex Recently Added
- Radarr Upcoming Media
- Samsung Multi Room
- simpleicons
- Sonarr Upcoming Media
- Sonoff LAN
- UniFi Gateway
- UniFi Protect Integration for Home Assistant

#### HACS (Frontend)
- Animated Weather Card
- Atomic Calendar
- auto-entities
- Banner Card
- Battery State Card
- Button Entity Card
- Button Text Card
- button-card
- card-mod
- card-tools
- Climate Thermostat Card
- Custom Header
- Custom Slidebar
- fold-entity-row
- gap-card
- Garbage Collection Card
- hui-element
- kibibit Theme
- layout-card
- Lightalarm Card
- Mini Graph Card
- Mini Media Card
- Multiple Entity Row
- Nord Theme
- Paper Button Row
- RGB Light Card
- Search Card
- Select List Card
- Simple Thermostat
- slider-entity-row
- Spotify Lovelace Card
- Stack In Card
- state-switch
- Swipe Card
- Text Divider Row
- TV Remote Card
- Upcoming Media Card
- Vertical Stack in Card
- Weather Card

#### Custom Components
- PS4 Waker
- browser_mod
- HASS-sonoff-ewelink

## Devices/Sensors

#### ZigBee - deCONZ ConBee II (Raspberry Pi 3B)
   - Xiaomi Door/Windows Contact Sensor [18]
   - Xiaomi Temperate/Humidity Sensor [4]
   - Xiaomi Water Leak Sensor [1]
   - IKEA TRADFRI LED Bulb E27 [2]
   - IKEA TRADFRI LED Bulb GU10 [3]
   - IKEA TRADFRI Remote Control [1]
   - IKEA TRADFRI Wireless Motion Sensor [1]
   - IKEA TRADFRI Dimmer Switch [2]

#### 433Mhz RF - Sonoff RF Bridge (Tasmota)
- KERUI PIR Motion Sensor [3]
- Sonoff DW1 Door/Window Contact Sensor [4]
- eTIGER Fire/Smoke Detector [1]
- fashionhome Wall Panel Remote Control [1]   

#### ESPHome - ESP8266/ESP32 nodeMCU
- WS2818b RGB LED Strip [5]
- DHT22 Temperature/Humidity Sensor [3]
- AM312 PIR Motion Sensor [5]
- LDR Sensor [1]  

#### Lights
- Yeelight Smart LED Bulb [2]

#### Switches
- Sonoff Basic R2 [2]
- Sonoff Dual R2 [2]
 
#### Security Cameras - Ubiquiti UVC (CloudKey Gen2+ - UniFi Protect)
- Ubiquiti UVC-G3 [2]
- Ubiquiti UVC-Flex [1]  

#### Media Players
- Samsung M5 Speaker [1]
- Google Home Mini [2]
- Google ChromeCast [2]
- Sony Playstation 4 [1]   

