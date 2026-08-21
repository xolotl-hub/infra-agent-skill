# 📦 Plantillas de Containerización Docker

## Dockerfile Multi-Stage (Agnóstico)

```dockerfile
FROM alpine:3.19 AS builder
WORKDIR /app
# Pasos de compilación según la plataforma activa

FROM alpine:3.19 AS runner
WORKDIR /app
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser
EXPOSE 8080
CMD ["/app/server"]
```

## Docker Compose

```yaml
version: '3.8'

services:
  app:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "8080:8080"
    environment:
      - NODE_ENV=production
    restart: unless-stopped
    healthcheck:
      test: ["CMD", "wget", "-qO-", "http://localhost:8080/health"]
      interval: 10s
      timeout: 5s
      retries: 3
```
