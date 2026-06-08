# Azure Test Helm Environment

This environment is for AKS with Azure-native platform services.

Use Azure-managed services for:

- Ingress: Application Gateway WAF v2 + AGIC.
- Monitoring: Azure Monitor Container Insights.
- Metrics: Azure Monitor managed service for Prometheus.
- Dashboards: Azure Managed Grafana.
- Database: Azure Database for MySQL Flexible Server.

Do not deploy these legacy in-cluster infra charts for Azure:

- `infra/gateway`
- `infra/gateway-namespace`
- `infra/mysql`
- `infra/monitoring/prometheus`
- `infra/monitoring/loki`
- `infra/monitoring/promtail`
- `infra/monitoring/grafana-agent`
- `infra/storage`

Keep temporarily:

- `infra/app-namespace`
- `infra/rabbitmq`, until we decide whether to replace RabbitMQ with Azure Service Bus.

