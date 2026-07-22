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

<br>
<div style="color: #d9534f; border-left: 4px solid #d9534f; padding-left: 10px; margin: 10px 0;">
<strong>Comentario (Edson Fabricio Subia Huaicane):</strong><br>
Complementando lo anterior, desde la ingeniería de sistemas me preocuparía la alta disponibilidad de los servicios on-premise: Harbor, Keycloak y PostgreSQL son dependencias críticas cuya caída detendría todo el laboratorio, así que propondría réplicas o, como mínimo, respaldos con un plan de restauración probado para cada uno. También sugiero fijar las imágenes por <em>digest</em> y no solo por <em>tag</em>, para que la promesa de "entorno idéntico" se cumpla de verdad y no se rompa con un tag sobrescrito. Y agregaría una capa de observabilidad (métricas y logs centralizados) desde el inicio: en una arquitectura híbrida con tantos componentes, detectar dónde falla algo es la mitad del trabajo.
</div>
