# 📦 Best Practices: Docker Multi-Stage Containerization

## Principios Fundamentales

1. **Aislamiento de la Etapa de Construcción**:
   Las herramientas de compilación (SDKs, compiladores, paquetes dev) NO deben llegar a la imagen final.

2. **Seguridad y Usuario No-Root**:
   Nunca correr el contenedor como `root`. Crear un usuario `appuser` explícito.

3. **Inmutabilidad y Tags Semánticos**:
   Evitar el uso de `:latest` en producción. Usar SHA del commit (`:sha-a1b2c3d`) o SemVer (`:v1.2.3`).

4. **Cache Layering**:
   Copiar archivos de definición de dependencias antes que el código fuente.
