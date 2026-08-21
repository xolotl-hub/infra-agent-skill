# 🏥 Script de Health Check de Infraestructura

> **Diagnóstico**: Script Bash para verificar la salud de endpoints tras un despliegue.

```bash
#!/usr/bin/env bash
set -euo pipefail

TARGET_URL="${1:-http://localhost:8080/health}"
MAX_RETRIES=10
SLEEP_TIME=3

echo "🔍 Verificando salud del endpoint: ${TARGET_URL}"

for i in $(seq 1 $MAX_RETRIES); do
  HTTP_STATUS=$(curl -s -o /dev/null -w "%{http_code}" "$TARGET_URL" || echo "000")
  if [ "$HTTP_STATUS" -eq 200 ]; then
    echo "✅ Health check exitoso (HTTP 200) en intento $i"
    exit 0
  fi
  echo "⏳ Intento $i/$MAX_RETRIES: Recibido HTTP $HTTP_STATUS... reintentando en ${SLEEP_TIME}s"
  sleep "$SLEEP_TIME"
done

echo "❌ ERROR: Health check falló tras $MAX_RETRIES intentos."
exit 1
```
