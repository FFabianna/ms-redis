# 🧠 ms-redis

This microservice deploys a Redis instance as a container within an AKS cluster. Redis is an in-memory key-value store, commonly used for caching, session management, and lightweight message queues.

---

## 🔗 Project Links

- 📋 [Trello Board](https://trello.com/invite/b/680296aa17864e87fc6c7fed/ATTI82505e108ae3e7a005ede0081ec437f87CDDDEF1/microservice)
- 📄 [Project Documentation](https://docs.google.com/document/d/1FER2lpkZJk2eI5tpMnMy8mFhd42g3f4jioasHwZ0klo/edit?usp=sharing)


## 📁 Project Structure

- `Dockerfile`: Builds a lightweight image based on the official Redis image.
- `k8s/deployment.yaml`: Deploys a Redis pod in Kubernetes.
- `k8s/service.yaml`: Exposes Redis internally via a `ClusterIP` service.
- `.github/workflows/deploy.yaml`: GitHub Actions workflow to build, push, and deploy Redis automatically.
- `.github/workflows/slack.yaml`: Slack integration to send notifications on repository changes.

---

## 🐳 Docker Image

The service uses the official `redis:latest` image. Port 6379 is exposed to allow communication. Redis is started using the default `redis-server` command.

---

## ☸️ Kubernetes Deployment

Redis is deployed as a single replica using a `Deployment`. A corresponding `Service` allows internal communication under the hostname `redis` within the Kubernetes cluster.

---

## 🔁 CI/CD Pipeline

The main GitHub Actions workflow automates:

1. Azure authentication.
2. Docker image build and push to Azure Container Registry (ACR).
3. Redis deployment to AKS.
4. Image update via `kubectl set image`.

---

## 📢 Slack Integration

A secondary GitHub Actions workflow notifies a Slack channel when changes are pushed to the `main` branch. This helps keep the team informed of updates in the `ms-redis` microservice repository.

---
## <b> Made by </b>

+ [Fabiana Valderruten](https://github.com/FFabianna "FFabianna")
+ [Gloria Vicuña](https://github.com/Vanesa155 "Vanesa V.")

[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)