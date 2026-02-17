# Node.js Prometheus Monitoring & Alerting Project 🚀

This project demonstrates how to:
- Build a Node.js application with custom Prometheus metrics
- Containerize the app using Docker
- Deploy it on Kubernetes
- Monitor it using Prometheus
- Trigger alerts and send notifications to Slack via Alertmanager

---

## 📌 Application Overview

The Node.js application:
- Uses Express.js
- Exposes Prometheus metrics on `/metrics`
- Counts HTTP requests to the root endpoint `/`
- Sends alerts when request rate exceeds a defined threshold

---

## 🧱 Project Architecture

- Node.js App → Exposes metrics
- Docker → Container image
- Kubernetes Deployment → Runs the app (3 replicas)
- NodePort Service → Exposes the app
- ServiceMonitor → Allows Prometheus scraping
- PrometheusRule → Defines alert conditions
- AlertmanagerConfig → Sends alerts to Slack

---

## 📁 Project Structure

```
.
├── index.js
├── Dockerfile
├── nodejs-app.yaml
├── nodejs-svc.yaml
├── nodejs-alert.yaml
├── nodejs-alert-manager.yaml
```

---

## ⚙️ Node.js Application

- Custom Metric:
  `http_requests_root_total`
- Metrics endpoint:
  `/metrics`
- App endpoint:
  `/`

---

## 🐳 Docker

Build image:
```
docker build -t nodejs-app .
```

Tag & push:


---

## ☸️ Kubernetes Deployment

Deploy:
```
kubectl apply -f nodejs-app.yaml
kubectl apply -f nodejs-svc.yaml
```

---

## 📊 Prometheus & Alerting

Alert rule triggers when:
```
rate(http_requests_root_total[5m]) > 10
```

Apply:
```
kubectl apply -f nodejs-alert.yaml
kubectl apply -f nodejs-alert-manager.yaml
```

---

## Load Testing

```
chmod +x send.sh
./send.sh
```

---
