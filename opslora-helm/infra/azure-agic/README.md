# Azure AGIC Ingress Notes

This folder documents the Azure ingress direction for Opslora.

## Decision

Use Azure Application Gateway WAF v2 with the AKS AGIC add-on.

Do not deploy kgateway for the Azure phase 1 test environment.

## Routing Model

Current mainline charts use:

```text
Gateway API HTTPRoute + kgateway
```

Azure branch charts add:

```text
networking.k8s.io/v1 Ingress + azure/application-gateway ingress class
```

## Azure Test Values

Each externally routed app chart has a `values-azure-test.yaml` file.

These values:

- Disable Gateway API route rendering with `gateway.enabled: false`.
- Enable `ingress.enabled: true`.
- Route through `app-test.opslora.com`.
- Keep service backends unchanged.

## Required Azure Infrastructure

Terraform should create:

- AKS with Azure CNI Overlay.
- Application Gateway WAF v2 in `snet-ingress`.
- AGIC add-on attached to the Application Gateway.

The Helm charts should only create Kubernetes application resources and Ingress resources.

