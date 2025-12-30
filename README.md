# Self-Hosted-Infrastructure-Automation-Lab
# Home Lab & Systems Automation Infrastructure

## 🛠 Technology Stack
* **OS:** Debian GNU/Linux (Stable)
* **Orchestration:** Docker Engine & Docker Compose
* **Networking & Connectivity:** Tailscale (WireGuard-based Mesh VPN)
* **Script:** Bash scripting
* **Databases:** PostgreSQL 14 (Shared instance for cross-application data)
* **IoT Protocols:** Matter, Thread, MQTT

Overview

This repository contains a self-hosted infrastructure automation lab designed to explore and demonstrate practical aspects of deploying, operating, and maintaining containerized services on a single Linux host.

The project focuses on:

service orchestration using Docker Compose,

secure remote access to infrastructure,

management of stateful services,

and documenting operational considerations typical for real-world systems.

The environment is intentionally kept simple and transparent, reflecting realistic constraints of small to medium-scale deployments.

System Overview

Operating System: Debian GNU/Linux (stable)

Container Runtime: Docker Engine

Orchestration: Docker Compose

Database: PostgreSQL

Remote Access: Tailscale (WireGuard-based mesh VPN)

All services are deployed on a single host and managed declaratively through version-controlled configuration files.

Architecture

The system follows a single-node architecture:

Remote access (VPN)
        |
     Tailscale
        |
   Debian Host
        |
   Docker Engine
     ├─ Application containers
     ├─ PostgreSQL container
     └─ Supporting services


Services are not exposed directly to the public internet.

Remote access is limited to authenticated VPN peers.

Application data is persisted using Docker volumes.

Design Rationale
Docker Compose

Docker Compose is used to orchestrate services due to its simplicity, predictability, and suitability for single-host environments.
The project intentionally avoids more complex orchestration platforms where they would not provide clear benefits.

PostgreSQL

PostgreSQL is used as a centralized relational database for stateful services, reflecting common industry practice for reliability and data integrity.

Tailscale

Tailscale enables secure remote access without relying on public IP addresses or port forwarding, which simplifies network configuration and reduces exposure.

Operational Notes

This lab is designed with operational awareness in mind.

Services can be started, stopped, and updated independently.

Logs and service status can be inspected using standard Docker and Linux tools.

Configuration is separated from runtime data through the use of Docker volumes.

While the environment does not implement high availability or automated recovery, it provides a clear foundation for extending such features if required.
