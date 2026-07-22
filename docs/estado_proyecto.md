# Estado del Proyecto — Resumen de contribuciones y pasos restantes

Este documento resume específicamente TODO lo que ya se implementó en el repositorio (por mí) y divide el trabajo restante en las partes necesarias para terminar el proyecto. Está escrito para ser pegado en el repositorio como documento operativo y referencia del equipo.

---

## ¿Qué se hizo (concretamente) — entregables añadidos al repo

1. docs/runbooks/runbook-publicacion-imagen.md
   - Runbook operativo completo: pasos detallados para recibir, validar, escanear (Trivy), firmar (cosign) y publicar imágenes en Harbor; checklist mínimo; criterios de aceptación; comandos de ejemplo.
   - Commit: `0552f1e365140be1dc4fc4a18b99f181573bf617`.

2. README.md (actualizado)
   - Añadí enlace al runbook en la sección "Anexos" para que sea fácil de encontrar desde la raíz del repositorio.
   - Commit: `4d4da5c3bc827358814b8f3a956e2ea40dbb1a7d`.

3. docs/proceso-solicitud-imagen.md (actualizado)
   - Inserté el **Formulario mínimo para solicitud** (campos obligatorios) y la **tabla de SLAs sugeridos**. También añadí indicadores mínimos y metadatos (responsable/fecha).
   - Commit: `a7a4877b40914108b84384542747fb7e53b9d972`.

4. (Pendiente listo para añadir) docs/training/guia-capacitacion-operadores.md
   - Guía de capacitación redactada en MD (objetivo, agenda, ejercicios, checklist y criterios de aprobado). Está lista para añadirse al repo cuando me confirmes.

---

## Resumen de por qué estas contribuciones importan
- Proveen procesos operativos reproducibles y trazables para la gestión del catálogo de imágenes. 
- Dotan al equipo de instrucciones prácticas y listas para ejecutar (runbook + formulario mínimo). 
- Facilitan la transición a la fase operativa (instalación y pilotaje) sin necesidad de código adicional.

---

## ¿Cuántas partes faltan para terminar el proyecto?
Propuesta: el trabajo restante lo organizo en 9 partes (cada "parte" agrupa actividades relacionadas que deben completarse para que el proyecto esté en producción operativa y mantenible).

Total de partes restantes: 9

A continuación se listan las 9 partes, con tareas clave y entregables mínimos para cada una.

### Parte 1 — Infraestructura física/virtual (Provisionamiento)
- Tareas: aprovisionar hosts/VMs o confirmar acceso a Proxmox, redes, VLANs, almacenamiento.
- Entregables: inventario de hosts, diagrama de red, credenciales operativas (seguras).
- Estimación: 1–3 semanas.

### Parte 2 — Plataforma base y servicios (Despliegue)
- Tareas: desplegar Proxmox (si aplica), Kubernetes (K3s/Talos), Harbor, Keycloak, PostgreSQL, MinIO.
- Entregables: servicios accesibles, proyectos iniciales en Harbor y realm en Keycloak.
- Estimación: 1–3 semanas.

### Parte 3 — Seguridad y gestión de secretos
- Tareas: integrar Trivy, cosign, configurar políticas RBAC (Keycloak+Harbor), gestionar secretos (Vault / sealed secrets), habilitar TLS.
- Entregables: pipeline de escaneo, firma, roles definidos y secretos cifrados.
- Estimación: 1–2 semanas.

### Parte 4 — Backup, recuperación y continuidad
- Tareas: configurar backups para Postgres, MinIO, snapshots de Proxmox/VMs, y procedimientos de restore.
- Entregables: runbooks de backup/restore, prueba de restauración documentada.
- Estimación: 1 semana.

### Parte 5 — Observabilidad y monitoreo
- Tareas: desplegar Prometheus + Grafana (métricas), sistema de logs (Loki/ELK), alertas básicas (espacio, servicios caídos).
- Entregables: dashboards operativos y alertas configuradas.
- Estimación: 1–2 semanas.

### Parte 6 — Flujos operativos y catálogo (Workflows)
- Tareas: formalizar pipeline o proceso manual para: build/import → scan → sign → publish; integrar con runbook; definir metadata y retención en Harbor.
- Entregables: catálogo operativo con procesos documentados y automatización mínima (scripts o CI simple si se desea).
- Estimación: 1–3 semanas.

### Parte 7 — Pilotaje y pruebas con usuarios
- Tareas: planificar y ejecutar piloto en 1 laboratorio (N máquinas, M estudiantes), pruebas funcionales y de carga, recopilar feedback.
- Entregables: informe de piloto, lista de issues, mejoras priorizadas.
- Estimación: 2–4 semanas.

### Parte 8 — Formación y gobernanza
- Tareas: impartir capacitaciones (operadores, docentes), definir owners y SLAs finales, políticas, roles y procesos de mejora continua.
- Entregables: guía de capacitación (MD), listas de responsabilidades con nombres, SLAs acordados.
- Estimación: 1–2 semanas (en paralelo al pilotaje).

### Parte 9 — Documentación final, legal y aprobación presupuestal
- Tareas: completar diagramas C4, anexos de costos, políticas de privacidad y SLA institucional; obtener aprobaciones formales.
- Entregables: documentación completa enlazada en README y aprobación de stakeholders.
- Estimación: 1–3 semanas.

---

## Prioridad inicial y orden sugerido
1. Parte 1 (Infra) — sin infraestructura no hay despliegue. 
2. Parte 2 (Plataforma base) — desplegar Harbor/Keycloak/Postgres/MinIO.
3. Parte 3 (Seguridad) y Parte 4 (Backup) — para operar de forma segura.
4. Parte 6 (Workflows) — usar runbook y formalizar flujo de imágenes.
5. Parte 5 (Observabilidad) — monitoreo y alertas básicas.
6. Parte 7 (Pilotaje) y Parte 8 (Formación) — ejecutar piloto y capacitar.
7. Parte 9 (Documentación final y aprobaciones).

---

## Siguientes pasos inmediatos (qué puedo hacer ahora en el repo)
- Añadir `docs/training/guia-capacitacion-operadores.md` (ya redactada) — puedo añadirla ahora en main. 
- Crear issues/épicas en GitHub para las 9 partes con listas de tareas y asignar prioridades/responsables. 
- Generar plantillas (issue template para solicitud de imagen, PR template para documentación y runbooks).

Si querés que avance, indicame cuál de estas tres acciones realizo ahora (puedo hacerlas en main):
- A: añadir la Guía de capacitación en docs/training/ (recomendado)
- B: crear issues/épicas para las 9 partes y tareas internas (necesito nombres para asignar si querés asignaciones)
- C: crear plantillas (issue + PR) y enlazarlas en CONTRIBUTING.md

---

*Documento generado automáticamente y añadido al repositorio cuando se indique.*

> **Comentario de Renzo Geomar Mamani Quispe:**
> Me parece excelente cómo se ha estructurado este reporte de estado. La integración de los runbooks y los procesos de solicitud nos da una base operativa muy sólida, reduciendo la fricción para cuando pasemos a producción. El roadmap dividido en 9 fases es súper claro y coherente; destaco especialmente la decisión de consolidar la seguridad y los backups (Partes 3 y 4) justo después de la plataforma base, lo cual es vital para un entorno de laboratorios. Para no frenar el impulso, sugiero que procedamos de inmediato con la **Opción A** para dejar la guía de capacitación oficializada en la rama `main`. A la par, sería ideal avanzar con la **Opción B** para mapear estas 9 partes en épicas e issues dentro de GitHub, lo que nos dará la visibilidad necesaria para empezar a atacar las tareas de infraestructura.
