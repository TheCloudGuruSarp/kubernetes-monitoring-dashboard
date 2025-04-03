# Kubernetes Monitoring Dashboard

A comprehensive monitoring solution for Kubernetes clusters using Prometheus, Grafana, and Loki.

## ✨ Developed by Sarper ✨

---

## Features

- Real-time monitoring of Kubernetes resources
- Custom dashboards for different metrics
- Alerting system for critical events
- Log aggregation and analysis
- Resource usage visualization

## Architecture

The architecture consists of Prometheus for metrics collection, Grafana for visualization, and Loki for log aggregation, all deployed on a Kubernetes cluster.

## Components

- **Prometheus**: Metrics collection and storage
- **Grafana**: Visualization and dashboards
- **Loki**: Log aggregation
- **Alertmanager**: Alert handling and notifications
- **Node Exporter**: Host metrics collection
- **kube-state-metrics**: Kubernetes state metrics

## Getting Started

### Prerequisites

- Kubernetes cluster (v1.19+)
- Helm (v3+)
- kubectl configured to access your cluster

### Installation

```bash
# Add Helm repositories
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update

# Create namespace
kubectl create namespace monitoring

# Install Prometheus Stack
helm install prometheus prometheus-community/kube-prometheus-stack \
  --namespace monitoring \
  --values ./helm/prometheus-values.yaml

# Install Loki Stack
helm install loki grafana/loki-stack \
  --namespace monitoring \
  --values ./helm/loki-values.yaml
```

## Dashboard Examples

- Cluster Overview
- Node Resources
- Pod Resources
- Application Metrics
- Log Analysis

## Alerting Configuration

Alerts are configured in `./prometheus/alerts.yaml` and can be customized based on your requirements.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.