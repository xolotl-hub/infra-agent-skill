# 🚀 Estrategias de Despliegue y Rollback

## 1. Despliegue Blue/Green
- Se mantienen dos entornos idénticos (Azul = Activo, Verde = Nuevo).
- Se despliega la nueva versión en Verde y se ejecutan pruebas de humo.
- Se cambia el enrutador/load balancer de Azul a Verde instantáneamente.

## 2. Despliegue Canary
- Se direcciona un % pequeño de tráfico (ej. 5%) al nuevo contenedor.
- Se monitorean métricas de error durante 15 minutos.
- Si no hay incremento en el error rate, se incrementa al 100%.

## 3. Protocolo de Rollback Automático
- Si el health check del nuevo contenedor falla durante 3 intentos consecutivos, el sistema debe revertir automáticamente el registro DNS o puntero de contenedor anterior.
