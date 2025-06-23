# DevOps Docker + NGINX Reverse Proxy Assignment

## ✅ Project Overview

This project sets up a reverse-proxy architecture using Docker Compose with:

- `service_1`: A GoLang-based microservice running on port 8001
- `service_2`: A Python Flask-based microservice running on port 5000
- `nginx`: Acts as a reverse proxy to route traffic on port 8080

## 🧱 Project Structure


├── docker-compose.yml
├── nginx/
│ ├── Dockerfile
│ └── nginx.conf
├── service_1/
│ ├── Dockerfile
│ ├── main.go
│ └── go.mod
├── service_2/
│ ├── Dockerfile
│ ├── app.py
│ └── requirements.txt
└── README.md


## 🛠 Setup Instructions

1. Install Docker Desktop
2. Open terminal in project root
3. Run:

   ```bash
   docker compose build --no-cache
   docker compose up

Access the services via:

http://localhost:8080/service1/ping

http://localhost:8080/service2/ping

🔀 NGINX Routing Rules
/service1/ → service1 (Go server on port 8001)

/service2/ → service2 (Flask server on port 5000)

🩺 Healthchecks
Both services include Docker healthchecks that ping /ping every 30s.

📝 Notes
This is a dev setup using nginx:alpine

Not suitable for production without WSGI for Flask or TLS for NGINX

✅ Bonus Implemented
Healthchecks for both services

Clean, modular Docker setup

Functional NGINX routing