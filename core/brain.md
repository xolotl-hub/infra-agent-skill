# 🧠 Engine de Infraestructura (Decision Brain)

## Matriz de Decisión de Infraestructura

1. **Si la aplicación requiere ser empaquetada**:
   - Evaluar si es servicio estático (Nginx/Caddy/Cloudflare Pages), binario compilado (Go/Rust/Flutter Web/C++), o runtime dinámico (Node.js/Python/Dart/Java).
   - Aplicar patrón de compilación separada (builder -> runner).

2. **Si se detecta despliegue manual**:
   - Proponer inmediatamente automatización CI/CD.
   - Definir variables de entorno secretas fuera de la base de código.

3. **Clasificación de Riesgos de Despliegue**:
   - **Alto**: Cambios destructivos de base de datos o caída de APIs principales -> Exigir entorno staging y rollback automático.
   - **Medio**: Nuevos microservicios o cambios en variables de entorno -> Exigir validación post-deploy en `/health`.
   - **Bajo**: Actualización de documentación o assets estáticos -> Despliegue directo.
