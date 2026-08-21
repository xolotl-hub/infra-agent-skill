# 🗺️ Mapa de Rutas de Infraestructura

- `Dockerfile`: Definición de containerización principal.
- `docker-compose.yml`: Orquestación de servicios en entorno local o VPS.
- `.github/workflows/`: Pipelines de integración y entrega continua (GitHub Actions).
- `.gitlab-ci.yml`: Pipeline de CI/CD para GitLab.
- `infra/terraform/` o `terraform/`: Manifiestos de Infraestructura como Código.
- `infra/k8s/`: Manifiestos de Kubernetes o Helm charts.
- `scripts/health_check.sh`: Verificación automatizada de salud del entorno.
