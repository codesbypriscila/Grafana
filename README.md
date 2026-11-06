# DevOps Lab · Monitoring with Grafana

A monitoring stack with Docker Compose: Node Exporter exposes the machine's metrics, Prometheus collects them and Grafana shows them in dashboards.

Part of my DevOps labs (Electiva 2).

## What it shows

- Starting several services together with **Docker Compose**.
- Setting up **Prometheus** to scrape metrics every 15 seconds from itself and from Node Exporter.
- Connecting **Grafana** to Prometheus to build dashboards (CPU, memory, disk, network).

## Tech stack

- **Docker Compose**
- **Prometheus**
- **Node Exporter**
- **Grafana**

## Files

```
Grafana-main/
├── docker-compose.yml  Prometheus, Grafana and Node Exporter
└── prometheus.yml      Scrape settings
```

## Running it

```bash
cd Grafana-main
docker compose up -d
```

| Service | URL |
| --- | --- |
| Grafana | [http://localhost:3000](http://localhost:3000) (user `admin`, password `admin`) |
| Prometheus | [http://localhost:9090](http://localhost:9090) |
| Node Exporter | [http://localhost:9100/metrics](http://localhost:9100/metrics) |

In Grafana, add Prometheus as a data source with the URL `http://prometheus:9090`, then create a dashboard or import a ready-made Node Exporter one.
