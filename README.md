🌡️ Dashboard Température MQTT

A real-time temperature monitoring dashboard built with HTML, Chart.js, and MQTT over WebSockets.

Features


Live temperature display with color-coded indicators (blue = cold, green = comfortable, yellow = warm, red = hot)
Historical chart showing the last 20 temperature readings via Chart.js
MQTT connection status with live feedback (connected, subscribing, reconnecting, offline)
Connection quality indicator reflecting the current broker state
Responsive design that adapts to mobile screens


How It Works

The dashboard connects to a HiveMQ cloud broker over a secure WebSocket (wss://). It subscribes to the capteurs/temperature topic and expects messages in JSON format:

json{ "temperature": 23.45 }

Each incoming message updates the live reading and appends a data point to the chart.

Tech Stack

TechnologyRoleHTML/CSSUI and layoutMQTT.jsMQTT client over WebSocketChart.jsTemperature history chartHiveMQ CloudMQTT broker

Getting Started

No build step required. Just open index.html in a browser.


Note: The broker credentials (username/password) are currently hardcoded in the script. For any production use, move these to a secure backend or environment variables.



Temperature Color Scale

RangeColorMeaning< 20 °C🔵 BlueCold20–25 °C🟢 GreenComfortable26–31 °C🟡 YellowWarm≥ 32 °C🔴 RedHot
