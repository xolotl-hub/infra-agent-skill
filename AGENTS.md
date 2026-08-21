---
name: infra-agent-skill
description: Transversal Infrastructure, CI/CD, Containerization, IaC, and Deployment Skill for AI Agents.
---

# 🏗️ Infra Agent Skill Directive

## Bootstrap de la Habilidad

Al detectar `$infra` o tareas relacionadas con Docker, CI/CD, Terraform, Kubernetes, VPS o despliegues, cargar y ejecutar:

1. `.skill/infra-agent-skill/SKILL.md` ← **Directiva principal de la habilidad**
2. `.skill/infra-agent-skill/core/commands.md`
3. `.skill/infra-agent-skill/core/brain.md`
4. `.skill/infra-agent-skill/core/path_map.md`

## Regla Canónica Agnóstica

Esta habilidad opera en cualquier lenguaje o plataforma (**Flutter, Node/TypeScript, Python, Go, Rust, C++, C# Game Engine**):
- **Cero acoplamiento rígido**: Usar abstracciones genéricas de containerización y despliegue.
- **Eficiencia de Capas Docker**: Siempre separar dependencias de código fuente para maximizar el uso de caché.
- **Rollback preventivo**: Ningún pipeline o despliegue es válido sin verificación explícita del endpoint `/health` post-deploy.
- **Economía de Tokens**: Generar manifiestos limpios sin comentarios redundantes ni bloques vacíos.
