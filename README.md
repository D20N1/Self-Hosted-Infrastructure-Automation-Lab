# Self-Hosted-Infrastructure-Automation-Lab
# Home Lab & Systems Automation Infrastructure

## 🛠 Technology Stack
* **OS:** Debian GNU/Linux (Stable)
* **Orchestration:** Docker Engine & Docker Compose
* **Networking & Connectivity:** Tailscale (WireGuard-based Mesh VPN)
* **Script:** Bash scripting
* **Databases:** PostgreSQL 14 (Shared instance for cross-application data)
* **IoT Protocols:** Matter, Thread, MQTT

## 🌐 Connectivity & Networking (CGNAT Bypass)
Due to **CGNAT** (Carrier-Grade NAT) limitations from my ISP, implemented a system-wide **Tailscale** service. 
* **Secure Remote Access:** This allows me to securely manage the Debian host and access web-based dashboards (Odoo, Home Assistant and NAS as well) from any location without port forwarding, and more secure.
* **Mesh Networking:** Tailscale provides a secure WireGuard-based overlay network, ensuring encrypted communication between my nodes.

## 🐳 Core Services (Docker Infrastructure)
I manage my applications using a **"Configuration as Code"** approach, ensuring portability and rapid deployment:

* **Home Assistant:** Centralized automation engine for IoT devices and sensor data for my home.
* **Odoo:** Enterprise Resource Planning (ERP) suite for testing business process automation and database integrations.
* **Joplin Server:** Self-hosted knowledge management system backed by a managed PostgreSQL instance.
* **AdGuard Home:** Network-wide DNS sinkhole and security management.
* **Mosquitto:** MQTT broker for low-latency machine-to-machine (M2M) communication.
* **Matter & OTBR:** Advanced Thread Border Router setup for next-generation IoT connectivity.

## 📁 Repository Structure
* `docker-compose.yml`: Sanitized orchestration file for the entire stack.
* `.env`: Template for environment variables and secrets management.
