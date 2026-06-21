# Azure Prod Helm Environment

This environment mirrors the Azure test shape for production.

Do not apply this until the Azure test environment is validated.

Use Azure-managed services for:

- Ingress: Application Gateway WAF v2 + AGIC.
- Monitoring: Azure Monitor Container Insights.
- Metrics: Azure Monitor managed service for Prometheus.
- Dashboards: Azure Managed Grafana.
- Database: Azure Database for MySQL Flexible Server.

Do not deploy legacy in-cluster infra charts for Azure:

- kgateway
- in-cluster MySQL
- Prometheus
- Loki
- Promtail
- Grafana Agent
- storage class chart

