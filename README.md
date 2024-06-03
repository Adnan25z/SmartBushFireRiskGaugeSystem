# Bushfire Risk Gauge

## About

The Bushfire Risk Gauge is an IoT project designed to predict and warn local residents of the risk of bushfires based on environmental conditions. The system uses multiple sensors to collect data, processes it via edge servers, and provides real-time updates and notifications through a website and Telegram messages.

## Group Members
- Dhruv Parikh (103592267)
- Adnan Zafar (103169535)
- Rohan Soni (103169933)
- Shivang Patel (103603570)

## Table of Contents
- [Introduction](#introduction)
- [Conceptual Design](#conceptual-design)
- [Implementation](#implementation)
  - [Sensing System](#sensing-system)
  - [Edge Server](#edge-server)
  - [Communication Protocol](#communication-protocol)
  - [API and Website Details](#api-and-website-details)
  - [Cloud Computing](#cloud-computing)
- [User Manual](#user-manual)
- [Limitations](#limitations)
- [Resources](#resources)

## Introduction

Bushfires are a significant risk in Australia due to the hot and dry climate. Recent bushfires have had devastating impacts, burning millions of hectares, destroying homes, and causing loss of life and wildlife. This project aims to provide a bushfire risk gauge system to warn local residents when there is a high risk of a bushfire, allowing them to prepare and evacuate if necessary.

## Conceptual Design

The system uses various sensors to detect environmental conditions that indicate a high risk of bushfires. Data from these sensors is processed and sent to a website for real-time monitoring. Residents are notified via Telegram when the risk is high.

## Implementation

### Sensing System

- **DHT22 Sensor**: Measures temperature and humidity.
- **Soil Moisture Sensor**: Measures the moisture level in the soil.
- **Flame Sensor**: Detects the presence of flames.
- **Smoke Sensor**: Detects smoke, indicating fire.

### Edge Server

- Four edge servers collect data from sensors and communicate with each other using MQTT.
- The edge servers run Python scripts to control and manipulate data from the Arduino devices.
- They also run APIs for notifications and a website for data visualization.

### Communication Protocol

- **Serial Communication**: Between Arduino devices and edge servers.
- **MQTT Protocol**: Used for communication between edge servers, enabling bi-directional data exchange.

### API and Website Details

- The API checks sensor data against threshold values and sends notifications via Telegram when these values are exceeded.
- The website displays visual data from the sensors, including minimum, maximum, and average values, and graphs for each sensor.

### Cloud Computing

- Uses ThingsBoard for device management, data collation, and visualization.
- Access tokens are used to collect sensor data and display it in a visually appealing format.

## User Manual

- The system uses various sensors and actuators to detect and respond to environmental conditions.
- Sensors include DHT22 for temperature and humidity, soil moisture sensors, flame sensors, and smoke sensors.
- Actuators include LCD screens, buzzers, LEDs, and a DC motor to alert users and mitigate risks.

## Limitations

- Sensors have a limited detection range, requiring multiple systems to cover a larger area.
- Flame sensor is prone to false alarms from sunlight or lightbulbs.
- M1 MacBooks' incompatibility with virtual machines required using a single Windows laptop for edge server development.
- Small radius of water dispersion from the DC motor limits effectiveness in real scenarios.
- Small buzzer, LED, and LCD visibility and audibility are limited to short distances.

## Resources

- Libraries: DHT, Telepot (for Telegram API), LiquidCrystal.
- Datasheets from Jaycar for sensor connections.
- Circuit.io and Lucidchart for conceptual design diagrams.
- Lab exercises for additional guidance.

