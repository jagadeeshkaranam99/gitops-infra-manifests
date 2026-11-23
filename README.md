# gitops-infra-manifests

Declarative Kubernetes, Helm, Terraform, ArgoCD, and Observability manifests for the **End-to-End GitOps CI/CD Platform on Kubernetes**.

## Architecture
- **Infrastructure as Code (`terraform/`)**: Provisions an AWS VPC and managed EKS cluster using Terraform.
- **Helm Chart (`charts/flask-app/`)**: Packages the Flask REST API Deployment (with `/api/v1/healthz` liveness/readiness probes and zero-downtime rolling updates), ClusterIP Service, and Traefik Gateway API `HTTPRoute`.
- **GitOps Continuous Delivery (`argocd/`)**: ArgoCD `Application` manifest configured with automated sync, pruning, and self-healing.
- **Observability (`monitoring/`)**: Prometheus and Grafana configuration for cluster and application health monitoring.
