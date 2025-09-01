# 📊 Observability Study – Spring Boot + Prometheus + Grafana

This project is a **study and exploration of observability metrics** in a Spring Boot application using **Prometheus** and **Grafana**, running inside a **Docker Compose** environment.

The stack includes:

* **Spring Boot API** (exposing Actuator metrics)
* **MySQL** (database)
* **Redis** (cache)
* **Nginx** (reverse proxy)
* **Prometheus** (metrics collection)
* **Grafana** (visualization dashboards)
* **React Client** (frontend to consume the API)

---

## 🛠️ Tech Stack

* **Spring Boot** 3.x
* **Docker / Docker Compose**
* **MySQL 5.7**
* **Redis**
* **Nginx**
* **Prometheus**
* **Grafana**
* **React (client)**

---

## 📂 Project Structure

```
.
├── app/                # Spring Boot application (API)
│   ├── Dockerfile
│   └── ...
├── client/             # Frontend
│   ├── Dockerfile
│   └── ...
├── nginx/              # Reverse proxy configs
│   ├── nginx.conf
│   └── proxy.conf
├── prometheus/         # Prometheus config and data
│   ├── prometheus.yml
│   └── prometheus_data/
├── grafana/            # Grafana data storage
├── mysql/              # Database init scripts
├── docker-compose.yml  # Docker Compose stack
└── README.md
```

---

## ▶️ Running the Project

### 1. Clone the repository

```bash
git clone https://github.com/your-user/your-repo.git
cd your-repo
```

### 2. Start the containers

```bash
docker-compose up -d --build
```

### 3. Access the services

* **API (Spring Boot)** → [http://localhost](http://localhost)
* **Prometheus** → [http://localhost:9090](http://localhost:9090)
* **Grafana** → [http://localhost:3000](http://localhost:3000)

    * Default user: `admin`
    * Default password: `admin`

---

## 📈 Observability Setup

* The Spring Boot app exposes metrics via **Spring Actuator** at:

  ```
  http://localhost/actuator/prometheus
  ```

* **Prometheus** is configured (in `prometheus/prometheus.yml`) to scrape these metrics.

* **Grafana** is connected to Prometheus as a **data source** to visualize the collected metrics.

You can create dashboards to monitor:

* API health (`/actuator/health`)
* JVM memory usage
* Request counts and latency
* Database metrics (via Actuator)
* Custom business metrics (if exposed)

---

## ⚙️ Useful Commands

* Check running containers:

  ```bash
  docker ps
  ```
* View logs of a service:

  ```bash
  docker logs app-forum-api -f
  ```
* Rebuild and restart:

  ```bash
  docker-compose up -d --build
  ```

---

## 📌 Next Steps

* Add custom metrics in the Spring Boot app
* Configure alerts in Prometheus
* Create Grafana dashboards for API performance and database health

---

## 📜 License

This project is for **learning and exploration** purposes. Feel free to fork and extend it.
