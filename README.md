# Grafana Monitoring Stack

A complete monitoring solution using Prometheus, Grafana, and Node Exporter to monitor system metrics and create custom dashboards.

## Overview

This project sets up a monitoring stack with:
- **Prometheus**: Time-series database for metrics collection
- **Grafana**: Visualization and dashboarding platform
- **Node Exporter**: System metrics collector

## Prerequisites

- Docker 28.2.2 or later
- Docker Compose

## Quick Start

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd Grafana_monitoring
   ```

2. Start the monitoring stack:
   ```bash
   docker-compose up -d
   ```

3. Access the services:
   - **Grafana**: http://localhost:3000 (admin/admin)
   - **Prometheus**: http://localhost:9090
   - **Node Exporter**: http://localhost:9100

## Configuration

### Prometheus Configuration
The `prometheus.yml` file configures:
- Global scrape interval: 10 seconds
- Node Exporter as a scrape target on port 9100

### Docker Compose Services
- **Prometheus**: Runs on port 9090 with persistent data storage
- **Node Exporter**: Collects system metrics from the host
- **Grafana**: Web interface on port 3000 with persistent dashboards

## Usage

### Setting up Grafana
1. Login to Grafana at http://localhost:3000
2. Add Prometheus as a data source: http://prometheus:9090
3. Import dashboards or create custom ones
4. Monitor system metrics like CPU, memory, disk usage, and uptime

### Available Metrics
Node Exporter provides metrics including:
- System uptime
- CPU usage
- Memory utilization
- Disk space
- Network statistics

## Screenshots
The `screenshots/` directory contains step-by-step visual guides showing:
- Docker Compose startup
- Prometheus dashboard
- Grafana configuration
- Custom dashboard creation
- Imported dashboard examples

## Stopping the Stack

```bash
docker-compose down
```

To remove volumes (delete all data):
```bash
docker-compose down -v
```

## Troubleshooting

- Ensure ports 3000, 9090, and 9100 are not in use
- Check container logs: `docker-compose logs <service-name>`
- Verify Prometheus targets are up at http://localhost:9090/targets