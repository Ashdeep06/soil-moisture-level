# ESP32 IoT Automated Irrigation Dashboard

A real-time IoT dashboard for soil moisture monitoring and automated irrigation using an ESP32 microcontroller, capacitive soil moisture sensor, and relay module.

## Features

- **Multi-Protocol Connectivity**:
  - **Demo Simulation Mode**: Test thresholds, triggers, and soil moisture changes without hardware.
  - **Web Serial API**: Connect your ESP32 directly via USB cable inside Google Chrome or Microsoft Edge.
  - **MQTT over WebSockets**: Stream live sensor data via any public or private MQTT broker (e.g., `broker.hivemq.com`).
  - **HTTP REST Endpoint**: Poll the ESP32's local web server directly.
- **Visual Meter & SVG Arc**: Real-time moisture percentage with dynamic color status (Optimal, Moderate, Critical Dry) and raw 12-bit ADC mapping.
- **Pump / Relay Trigger**: Animated water drop feedback, status indicator, and manual toggle.
- **Dynamic Threshold Rules**: Interactive sliders for Start Watering Threshold (default: 30%) and Stop Watering Threshold (default: 60%).
- **Live Telemetry Analytics**: Chart.js graph tracking soil moisture and pump state over time.
- **Terminal Console**: Color-coded live logs with timestamps for system events, commands, and sensor data.
- **Built-in ESP32 Firmware Generator**: One-click code modal supporting WiFi + MQTT, USB Web Serial, and HTTP REST WebServer.

## Hardware Wiring

| ESP32 Pin | Component | Description |
|-----------|-----------|-------------|
| **GPIO 34** | Capacitive Moisture Sensor AOUT | Analog Input (0 - 3.3V, ADC1) |
| **GPIO 26** | 5V / 12V Relay Module IN | Digital Output (Active HIGH) |
| **VCC (3.3V / 5V)** | Sensors & Relay VCC | Power Supply |
| **GND** | Sensors & Relay GND | Common Ground |

## Getting Started

1. Open `index.html` directly in any modern web browser (Google Chrome or Microsoft Edge recommended for Web Serial support).
2. By default, **Demo Simulation Mode** is active. You can adjust the moisture slider or click **Enable Soil Drying** to simulate real-world evaporation.
3. To connect physical hardware:
   - Click **Get ESP32 Code** in the top navigation bar.
   - Choose your communication mode (**WiFi + MQTT**, **USB Web Serial**, or **HTTP REST WebServer**).
   - Copy and upload the firmware to your ESP32 using the Arduino IDE.
   - Select the corresponding mode on the dashboard to connect.
