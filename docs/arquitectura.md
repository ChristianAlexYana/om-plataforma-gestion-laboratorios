# Arquitectura Técnica Propuesta

## Modelo General
**Híbrido**: Local (On-Premise) + Nube

## Componentes Principales

- **GitLab** → Código fuente y CI/CD
- **Harbor** → Registro privado de imágenes de contenedores
- **Keycloak** → Gestión de identidad y acceso
- **Proxmox VE** → Virtualización de hardware
- **Kubernetes** → Orquestación de contenedores
- **PostgreSQL + MinIO** → Base de datos y almacenamiento

## Flujo Recomendado
Estudiantes → Descargan imagen → Ejecutan localmente con Docker/Podman → Entorno idéntico al laboratorio.

<br>
<div style="color: #d9534f; border-left: 4px solid #d9534f; padding-left: 10px; margin: 10px 0;">
<strong>Comentario (Mauro Snayder Sullca Mamani):</strong><br>
La arquitectura híbrida propuesta logra un equilibrio idóneo entre gobernanza y eficiencia operativa. La combinación de Keycloak y Harbor garantiza el control centralizado de accesos y software seguro, mientras que delegar la ejecución a Docker/Podman local mediante imágenes estandarizadas evita la saturación de los servidores Proxmox y Kubernetes. Además, la integración con GitLab CI/CD, PostgreSQL y MinIO asegura la trazabilidad completa del ciclo de vida del software en el laboratorio.
</div>