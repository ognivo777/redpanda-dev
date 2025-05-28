# 🐼 Redpanda + Console (Minimal Dev Stack)

This repository provides a **lightweight, minimal Kafka-compatible development setup** using [Redpanda](https://redpanda.com/) — a high-performance, Zookeeper-free streaming platform — and [Redpanda Console](https://docs.redpanda.com/current/console/) for local development and debugging.

## 📦 What's Included

- **Redpanda Server** — Kafka API-compatible streaming platform, single-node mode
- **Redpanda Console** — Web UI for inspecting topics, messages, and consumer groups
- Configured using a minimal `docker-compose.yml` and `bootstrap.yml`

## 🚀 Getting Started

### Requirements

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

All of this provided with [Docker desktop](https://www.docker.com/products/docker-desktop/).

### Start the Stack

```shell
docker compose up -d
```
This will launch:
| Service          | Port | Description                      |
| ---------------- | ---- | -------------------------------- |
| Redpanda Server  | 9092 | Kafka-compatible broker endpoint |
| Redpanda Console | 8080 | Web UI for inspecting Redpanda   |

### Access the Console
After everything starts, visit: http://localhost:8080

You can use the console to:
 - View and create topics
 - Produce and consume messages
 - Monitor consumer groups
 - Explore topic configurations

### 🧹 Shut Down
To stop and remove the containers:

```shell
docker compose down
```

## 🛠 Configuration 
 - `docker-compose.yml`: Defines Redpanda and Console docker compose services.
- `bootstrap.yml`: Provides initial configuration for the redpanda cluster.


## Tips
### Start with a Clean Broker
Maybe you want to start with a clean state each time? Run:
```bash
docker compose up --renew-anon-volumes --force-recreate
```
This will recreate the containers and discard any existing data.

## 📘 Resources
[Redpanda Docs](https://docs.redpanda.com/home/)

[Redpanda Console Docs](https://docs.redpanda.com/current/console/)

Based on [Redpanda Docker compose](https://github.com/redpanda-data/docs/tree/main/tests/docker-compose).

