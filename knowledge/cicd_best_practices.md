# 🔄 Best Practices: CI/CD Pipelines Agnósticos

## 1. Estructura Estándar de Pipeline

Un pipeline de CI/CD moderno debe estructurarse en 4 etapas secuenciales independientes:

1. **Lint & Static Analysis**: Validación de sintaxis, reglas linter, formateo estricto.
2. **Automated Test Matrix**: Ejecución concurrente de pruebas unitarias y de integración.
3. **Artifact Build & Package**: Compilación de binarios o construcción de contenedores Docker multi-stage.
4. **Deploy & Smoke Verification**: Promoción al entorno correspondiente y validación post-despliegue.

## 2. Optimización de Rendimiento
- Usar caché de dependencias (npm/cargo/gradle/pub/pip) indexado por hash del lockfile.
- Ejecutar jobs en paralelo cuando no tengan dependencias directas entre sí.
- Evitar instalar CLI innecesarios dentro de los runners; utilizar imágenes docker pre-configuradas.
