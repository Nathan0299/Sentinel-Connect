# Sentinel Connect

[![status](https://img.shields.io/badge/status-alpha-yellow)]() [![license](https://img.shields.io/badge/license-MIT-blue)]()

A secure, lightweight comms + alerting platform for high-trust groups.  
Provides role-based dashboards, real-time messaging (WebSocket/MQTT), and tamper-evident audit logs.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Status](#status)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Quickstart (Dev)](#quickstart-dev)
  - [Backend Setup (FastAPI)](#backend-setup-fastapi)
  - [Frontend Setup (Flutter)](#frontend-setup-flutter)
  - [Docker (Optional)](#docker-optional)
- [Environment Variables](#environment-variables)
- [Testing](#testing)
- [Contributing](#contributing)
- [Roadmap](#roadmap)
- [Security & Privacy](#security--privacy)
- [License](#license)
- [Contact](#contact)

---

## Project Overview
Sentinel Connect is built for secure, real-time alerting and communication for small teams and trusted groups.  
Minimal footprint, hardened defaults, and auditability are primary goals.

---

## Status
**Alpha** — core messaging + authentication implemented.  
Pending: hardening, encryption audits, and scale tests.

---

## Key Features
- Role-based access (Admin / Operator / End-user)
- Real-time messaging & alerts (WebSocket / MQTT)
- Persistent event storage with tamper-evident audit logs
- Redis-backed queues and caching
- Dockerized for development and production

---

## Tech Stack
- **Frontend**: Flutter (web + mobile)
- **Backend**: Python (FastAPI)
- **Real-time**: WebSockets / MQTT
- **Database**: PostgreSQL
- **Cache/Queue**: Redis
- **CI/CD**: GitHub Actions, Docker
- **Storage**: S3-compatible (for attachments/archives)

---

## Architecture
Browser / Mobile (Flutter)
↕
WebSocket / MQTT Broker
↕
Backend API (FastAPI)
↕
PostgreSQL + Redis

Security:  
- End-to-End encryption primitives for messages  
- Immutable, tamper-evident audit logs  

---

## Quickstart (Dev)

> Prerequisites: `python3.11`, `docker`, and `flutter` installed.  
> Ensure SSH to GitHub is configured for cloning private repos.

### 1. Clone the repository
```bash
git clone git@github.com:Nathan0299/Sentinel-Connect.git
cd Sentinel-Connect
2. Backend Setup (FastAPI)
cd backend                # Move into backend folder
python -m venv venv       # Create virtual environment
source venv/bin/activate  # Activate the environment
pip install -r requirements.txt   # Install dependencies
uvicorn app.main:app --reload     # Run dev server
3. Frontend Setup (Flutter)
cd frontend        # Move into frontend folder
flutter pub get    # Install dependencies
flutter run -d chrome   # Run in Chrome (or another device)
4. Docker (Optional)
docker compose up --build
Environment Variables
Create a .env file in the backend directory with values like:
DATABASE_URL=postgresql://user:password@localhost:5432/sentinel
REDIS_URL=redis://localhost:6379/0
SECRET_KEY=your_secret_key_here
MQTT_BROKER_URL=localhost
Testing
Backend:
pytest
Frontend:
flutter test
Contributing
Pull requests are welcome.
For major changes, please open an issue first to discuss what you’d like to change.
Roadmap
 End-to-end encryption audit
 Mobile app packaging
 Kubernetes deployment templates
 Scaling tests (Redis/Postgres clusters)
Security & Privacy
Zero-trust design principles
Tamper-evident logs for auditability
Strong role-based access controls
Minimal external dependencies
License
MIT License. See LICENSE for details.
Contact
Project lead: Nathan Petrelli
📧 Email: [add your contact email]
🌍 GitHub: @Nathan0299

---
