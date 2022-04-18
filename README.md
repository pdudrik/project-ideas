# Introduction

This repository contains my personal ideas for potentially upcoming projects.

# List

- [Synchronise EduPage with Google Calendar](#synchronise-edupage-with-google-calendar)
- [Feature ideas for Smart House Solution](#feature-ideas-for-smart-house-solution)
  - [Command groups](#command-groups)
  - [Room radio](#room-radio)
  - [Variable light control](#variable-light-control)
  - [Thermostat controller](#thermostat-controller)
- [Smart House Solution](#smart-house-solution)

# Project Ideas Description

## Synchronise EduPage with Google Calendar

Synchronise all new tasks (HW, Project) and assignmets (Test) in EduPage with your personal Google Calendar account by creating new event for specific occasion.

Each task has specific:

- name of subject
- task type
- task title
- deadline - date and time

e.g.

- event title: "*MAT (Project) - Project about linear functions*"
- deadline set: "*2022/02/22 12:00 PM*"

Each assignmet has specific:

- name of subject
- assignmet title
- date and time of event (from - to)

e.g.

- event title: "*MAT (Test) - Equations with fractions*"
- date and time set: "*2022/02/22 01:15 PM - 02:00 PM*"

Script which will be checking for a new tasks and assignmets, will be executed in certain time during day (e.g. *02:00 PM* and *08:00 PM*). Script will be stored at local server.

### Technologies to use

- Python v3 - Google API, EduPage API
- server storage (e.g. Raspberry Pi)

## Smart House Solution

Create centralized system for smart houses (objects). System will be capable of maintaing and managing a household to a certain level. Whole object will be able to divide into specific areas (let's say rooms). Each room will have some devices. The number and the type of devices will depend only on the user. How many and which devices will they put into their household is only up to them. After device launch, the device will connect to the server. Then it will be up to user to decide in which room the device will be stored in system (not physical position, but logical position in system). Web server Nginx will be used as reverse proxy and will be used as gate between server and other modules - Web, ESP nodes.

The system will be divided into 3 parts:

- Server
- Web
- ESP nodes

### Server

Server side of project will be responsible for all communication among modules and other parts of system. It will be considered as core (heart) of the system. Backend of the system includes database, REST API, logs and other communication modules.

### Web

Web side of project will be that what user sees. The web application will have the options to control and monitor the whole system, specifically the devices within (ESP nodes in general). User will be able to see current values of specific evniromental properties (temperature, humidity, etc). There will be an option to control devices as appliances, lamps, etc.

### ESP nodes

Physical part of the project. Each *ESP node* is considered as a one device (e.g. thermometer, 2-channel relay controller, etc.). Part *ESP nodes* was named by using the majority of ESP controllers (ESP32, etc.) as the main MCU of device. Each device will be build by the main MCU and all necessry components such as sensors, relay modules, etc.

### Communication

Communication with *Web* will be through HTTP/HTTPS protocol.

Communication with *ESP nodes* will be through MQTT protocol.

### Technologies to use

Server:

- server - Raspberry Pi 4
- web server - Nginx
- REST API - Python3 Flask
- databse - sqlite3/PostreSQL (Python3 SQLAlchemy)
- communication - HTTP requests, paho MQTT
- logs - Python3 logger

Web:

- HTML5
- CSS3 - Bootstrap/Tailwind
- JavaScript - Jquery, AJAX

ESP nodes:

- Arduino.h
- MQTT - PubSubClient

## Feature ideas for Smart House Solution

This item consists of potentionaly upcomming features for project Smart House Solution. It has its own section because of complexity of project and for easier readability.

### Command groups

User will have an option to group up specific commands together. Those commands will be executed in order. The group will be user-defined.

e.g. *morning routine* :

1. trigger the alarm in specific time (user-defined as well)
2. pull up blinds
3. read the weather forecast
4. play some pleasent morning music or radio

### Room radio

Create new ESP nodes device which will operate as internet radio and music player. User will be able to control radio device from web application.

Device functions:

- play/pause/stop
- rewind/fast forward/set specific time

Device will be capable of playing:

- different radio stations
- own music - Spotify, Youtube or local storage

### Variable light control

Create ESP nodes device which will be capable of controlling the level of lights from the web application. Variable controller in range e.g. 0-100%.

### Thermostat controller

Link SHS system with thermostat system (Honeywell Home) by using their public API for developers. In the result of this, the system will have an access to manage and maitain the thermostats within the object through Web application.

By this, the system will be exposed to 3rd party enviroment.
