# Runbook — Publicación de imagen en Harbor

## Propósito
Documento operativo paso a paso para recibir, validar, escanear, firmar y publicar una imagen de contenedor en el catálogo institucional (Harbor). Está pensado para operadores/Responsable del Catálogo de Imágenes.

## Pre-requisitos
- Acceso a Harbor con permisos de `project admin` o similar.
- Acceso a un nodo de laboratorio o CI runner con Docker/Podman instalado.
- Trivy disponible en el entorno (CLI): https://github.com/aquasecurity/trivy
- Cosign (o herramienta de firma) disponible: https://github.com/sigstore/cosign
- Acceso al repositorio de documentos (este repo) para anexar informes.
- Credenciales seguras para push a Harbor (usuarios de robot o cuenta de servicio).

## Roles y responsables
- Docente: solicita la imagen y provee justificación académica.
- Administrador del Laboratorio: valida solicitud y coordina pruebas.
- Responsable del Catálogo de Imágenes (Owner): ejecuta el runbook y publica la imagen.
- Equipo de Soporte Técnico: pruebas de integración y resolución de incidencias.

## Artefactos requeridos
- Formulario de solicitud (campos mínimos: Curso, Docente, Fecha requerida, Software+versión, Justificación, Prioridad, Contacto técnico).
- Imagen a publicar (tarball, referencia externa o Dockerfile).
- Reporte de escaneo Trivy (JSON y/o HTML).
- Firma de imagen (cosign signature).
- Checklist de pruebas funcionales (pasos y resultados).

## Criterios de aceptación
- La imagen ha pasado el escaneo de vulnerabilidades con problemas críticos resueltos o documentados.
- Pruebas funcionales completadas y aprobadas por Administrador/Docente si aplica.
- Imagen firmada y subida a Harbor con metadata (versión, autor, notas académicas).
- Registro en el catálogo (documento y/o entrada) y notificación al docente.

---

## Pasos detallados

### 1) Recepción y validación de la solicitud
1. Abrir la solicitud y validar campos mínimos:
   - Curso / Código
   - Docente (nombre + email)
   - Fecha requerida
   - Software y versión
   - Justificación académica
   - Contacto técnico
2. Si falta información, devolver al solicitante solicitando correcciones.
3. Asignar prioridad (alta/normal/baja) y anotar SLA (p. ej. respuesta inicial en 3 días, entrega en 7 días para prioridad normal).

### 2) Obtención de la imagen
- Si el solicitante proporciona un Dockerfile o tarball:
  - Construir la imagen localmente:
    - Docker: docker build -t catalog-temporal/<nombre>:<versión> .
    - Podman: podman build -t catalog-temporal/<nombre>:<versión> .
- Si la imagen proviene de un registro externo, importar o pull:
  - docker pull external/repo:tag
  - docker tag external/repo:tag catalog-temporal/<nombre>:<versión>

### 3) Escaneo de seguridad (Trivy)
- Ejecutar Trivy en la imagen y guardar reporte en JSON:
  - trivy image --format json -o reports/<nombre>-trivy.json catalog-temporal/<nombre>:<versión>
- Revisar resultados y corregir vulnerabilidades críticas/altas según política.
- Adjuntar reporte al issue/solicitud.

### 4) Pruebas funcionales
- Desplegar la imagen en un entorno de pruebas (pod o contenedor aislado).
- Ejecutar checklist de pruebas funcionales (ejemplos):
  - Arranque de servicio
  - Endpoints básicos responden
  - Herramientas/IDE incluidas funcionan
  - Persistencia/bind mounts si aplica
- Documentar resultado de cada prueba (pass/fail) y observaciones.

### 5) Firma de la imagen
- Firmar la imagen con cosign (ejemplo):
  - cosign sign --key cosign.key registry.example.com/project/<nombre>:<versión>
- Verificar la firma:
  - cosign verify --key cosign.pub registry.example.com/project/<nombre>:<versión>
- Guardar evidencia de la firma (output) en el issue/solicitud.

> Nota: si no usan cosign, documentar la herramienta de firma usada y el proceso equivalente.

### 6) Subida a Harbor
- Taggear la imagen para Harbor y hacer push:
  - docker tag catalog-temporal/<nombre>:<versión> harbor.example.com/project/<nombre>:<versión>
  - docker login harbor.example.com
  - docker push harbor.example.com/project/<nombre>:<versión>
- En Harbor: añadir metadata (labels/description), políticas de retención y escaneo si aplica.

### 7) Verificación post-publicación
- Comprobar que la imagen está disponible en Harbor y que los artefactos (firma, scan report) están accesibles o referenciados.
- Realizar un pull desde una máquina cliente de prueba:
  - docker pull harbor.example.com/project/<nombre>:<versión>
  - cosign verify --key cosign.pub harbor.example.com/project/<nombre>:<versión>
- Ejecutar pruebas funcionales rápidas en la imagen publicada para confirmar integridad.

### 8) Actualizar catálogo y notificar
- Actualizar el catálogo institucional (puede ser un documento markdown en este repo o un sistema separado) con:
  - Nombre, versión, autor, fecha, link a registro en Harbor, link al scan report, nota de aprobación.
- Notificar al docente (email/Slack/GitHub issue) que la imagen está disponible y cómo descargarla.

### 9) Rollback (si se descubre problema tras publicación)
- Marcar la imagen como `deprecated` o `disabled` en Harbor.
- Restaurar versión anterior si existe: re-etiquetar y promover la versión anterior.
- Notificar a usuarios y ejecutar análisis/mitigación.

---

## Checklists y templates (copiar/pegar)

### Checklist mínimo de publicación
- [ ] Solicitud completa (campos mínimos).
- [ ] Imagen construida/importada en entorno temporal.
- [ ] Escaneo Trivy realizado y reporte adjuntado.
- [ ] Pruebas funcionales ejecutadas (documentadas).
- [ ] Imagen firmada.
- [ ] Imagen subida y metadata completada en Harbor.
- [ ] Catálogo actualizado y docente notificado.

### Campos mínimos para la solicitud (recomendado incluir en docs/proceso-solicitud-imagen.md)
- Curso / Código
- Docente (nombre + email)
- Fecha requerida
- Software + versión
- Justificación académica
- Entorno base requerido
- Prioridad
- Contacto técnico

---

## Notas operativas
- Mantener reportes de Trivy y logs en una carpeta protegida (p. ej. storage S3/MinIO o repositorio con acceso controlado) vinculada a la solicitud/issue.
- Establecer un periodo de retención de imágenes (ej. 6–12 meses) y políticas de limpieza en Harbor.
- Definir SLA claros para cada tipo de prioridad.

## Referencias
- Trivy: https://github.com/aquasecurity/trivy
- Cosign: https://github.com/sigstore/cosign
- Harbor: https://goharbor.io/

---

*Runbook creado automáticamente y añadido a docs/runbooks/runbook-publicacion-imagen.md*