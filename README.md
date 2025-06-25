# DevOps Intern Assignment: Nginx Reverse Proxy + Docker 🐳🛡️

This project sets up a containerized microservices environment with:

- Two backend services:
  - `service1`: A Go-based API
  - `service2`: A Python Flask API (run using `uv`)
- An `nginx` reverse proxy that routes all traffic to the appropriate backend based on URL path

All services are run using Docker Compose and accessible through a single port: `localhost:8080`.

---

## 🚀 Setup Instructions

1. Clone the repository

```bash
git clone https://github.com/Surendiran2003/devops-nginx-docker.git
cd devops-nginx-docker   

```

2. Build and start the services
``` bash
docker-compose up --build -d
```
3. Verify everything is running
```bash
docker ps
```
## How Routing Works (via Nginx)

Nginx routes incoming HTTP requests based on the URL path prefix:
| Request Path     | Routed To     | Description                 |
| ----------------- | ------------- | --------------------------- |
| `/service1/ping`  | Go service    | Health check                |
| `/service1/hello` | Go service    | Returns greeting from Go    |
| `/service2/ping`  | Flask service | Health check                |
| `/service2/hello` | Flask service | Returns greeting from Flask |

Example:
```bash
curl http://localhost:8080/service1/ping
curl http://localhost:8080/service2/hello

```
🛠️ Tech Stack

    Docker 🐳

    Docker Compose

    Nginx (Alpine)

    Golang (service1)

    Python + Flask + uv (service2)

📁 Project Structure
```bash
.
├── docker-compose.yml
├── nginx/
│   ├── Dockerfile
│   └── nginx.conf
├── service_1/
│   ├── Dockerfile
│   └── main.go
├── service_2/
│   ├── Dockerfile
│   ├── app.py
│   ├── pyproject.toml
│   └── uv.lock
└── README.md
