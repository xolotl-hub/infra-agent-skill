# 🏗️ IaC & Terraform Guide

## 1. Remote State Lock
Siempre configurar un backend remoto con locking habilitado (ej. AWS S3 + DynamoDB o GCP Bucket con Object Versioning) para prevenir condiciones de carrera.

## 2. Estructura Modular
- `main.tf`: Declaración de recursos principales.
- `variables.tf`: Entradas parametrizadas con tipos y validaciones explícitas.
- `outputs.tf`: Salidas necesarias para consumo de pipelines.
- `providers.tf`: Configuración de proveedores y versiones fijas.

## 3. Idempotencia y Drift Detection
Ejecutar `terraform plan` en CI para detectar descompensación de infraestructura antes de `terraform apply`.
