# DefendIoT

**DefendIoT** is an IoT-based environmental monitoring and cybersecurity research platform developed as part of an undergraduate research project.

The system collects real-time environmental data from ESP32 IoT devices, securely transfers it through MQTT, stores it in a PostgreSQL database hosted on an Oracle Cloud VPS, and prepares the collected data for future AI/ML-based intrusion detection and threat analysis.

---

# Project Architecture

```
ESP32 Sensor Node
        │
        │ Wi-Fi
        ▼
 Raspberry Pi Gateway
        │
        │ MQTT
        ▼
 Mosquitto Broker
        │
        ▼
Python MQTT Collector
        │
        ▼
 PostgreSQL Database
        │
        ▼
 Machine Learning Dataset
        │
        ▼
 Future Threat Detection Engine
```

---

# Features

- Real-time environmental monitoring
- MQTT-based communication
- Raspberry Pi edge gateway
- Dockerized PostgreSQL database
- Oracle Cloud VPS deployment
- Automatic data logging
- CSV dataset generation
- Machine Learning dataset preparation
- Scalable IoT architecture

---

# Hardware

- ESP32-C3 Super Mini
- Raspberry Pi 3 Model B
- DHT11 Temperature & Humidity Sensor
- MQ-135 Air Quality Sensor
- Flame Sensor
- LEDs
- Breadboard
- Jumper Wires

---

# Software Stack

## Embedded

- Arduino IDE
- ESP32 Board Package
- ArduinoJson
- PubSubClient
- DHT Sensor Library

## Edge Computing

- Raspberry Pi OS Lite
- Mosquitto MQTT Broker
- Python 3

## Backend

- Docker
- PostgreSQL
- pgAdmin
- Oracle Cloud VPS

## Languages

- C++
- Python
- SQL

---

# Project Structure

```
DefendIoT/

│
├── esp32/
│   ├── environmental_node/
│   └── README.md
│
├── collector/
│   ├── collector.py
│   ├── requirements.txt
│   └── data/
│
├── database/
│   ├── docker-compose.yml
│   └── init.sql
│
├── docs/
│   ├── architecture.png
│   ├── diagrams/
│   └── report/
│
├── datasets/
│   └── env_data.csv
│
├── images/
│
└── README.md
```

---

# Workflow

1. ESP32 reads sensor values.

2. Sensor data is converted into JSON.

3. ESP32 publishes data via MQTT.

4. Raspberry Pi receives MQTT messages.

5. Python Collector subscribes to the MQTT topic.

6. Data is stored inside PostgreSQL.

7. Data is exported for Machine Learning.

---

# Example MQTT Message

```json
{
    "device":"ENV_01",
    "temperature":29.4,
    "humidity":72,
    "air_quality":842,
    "flame":0,
    "wifi":-54,
    "timestamp":"2026-07-13T10:25:17"
}
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/DefendIoT.git

cd DefendIoT
```

---

## Install Python Dependencies

```bash
python3 -m venv venv

source venv/bin/activate

pip install -r requirements.txt
```

---

## Start PostgreSQL

```bash
docker compose up -d
```

---

## Start Mosquitto

```bash
sudo systemctl start mosquitto

sudo systemctl enable mosquitto
```

---

## Run MQTT Collector

```bash
python collector.py
```

---

# Database

The project stores environmental data in PostgreSQL.

Example table:

| Column | Description |
|---------|-------------|
| id | Primary Key |
| device | Device ID |
| temperature | Temperature (°C) |
| humidity | Humidity (%) |
| air_quality | MQ-135 Reading |
| flame | Flame Detection |
| timestamp | Time Received |

---

# Current Progress

✅ ESP32 Environmental Node

✅ MQTT Communication

✅ Raspberry Pi Gateway

✅ Oracle Cloud VPS

✅ Docker PostgreSQL

✅ Python Collector

✅ CSV Dataset Generation

⬜ ML Model Training

⬜ Intrusion Detection

⬜ Dashboard

⬜ Alert System

---

# Future Work

- AI-based anomaly detection
- Intrusion Detection System (IDS)
- Device trust scoring
- Real-time dashboard
- Email alerts
- Mobile notifications
- Network visualization
- Multi-node deployment

---

# Research Objective

The objective of DefendIoT is to develop a lightweight and scalable IoT monitoring platform that supports future AI-driven cyber threat detection using real-world IoT sensor data.

---

# Authors

**G.K.K.S.Gankanda**

Department of Network Technology

Faculty of Technology

University of Sri Jayewardenepura

Sri Lanka

**D.T.S.K.Jayathissa**
Department of Network Technology

Faculty of Technology

University of Sri Jayewardenepura

Sri Lanka

**P.R.Wayendra**

Department of Network Technology

Faculty of Technology

University of Sri Jayewardenepura

Sri Lanka
---

# License

This project is developed for academic and research purposes.

```


```
DefendIoT/
│
├── esp32/
├── raspberrypi/
├── collector/
├── database/
├── docker/
├── datasets/
├── docs/
├── images/
├── diagrams/
├── LICENSE
├── .gitignore
├── requirements.txt
└── README.md
```

