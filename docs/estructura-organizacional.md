# Estructura Organizacional del Laboratorio de Computación


---

## 1. Objetivos de la Organización

La estructura organizacional propuesta busca alcanzar los siguientes objetivos:

- Definir claramente las responsabilidades de cada participante en la gestión física y virtual.
- Reducir la duplicidad de funciones entre personal administrativo y académico.
- Facilitar la comunicación fluida entre los responsables de desarrollo y de operación.
- Garantizar una adecuada administración de los recursos tecnológicos (hardware e imágenes).
- Estandarizar los procesos operativos del laboratorio mediante flujos BPMN.
- Favorecer la mejora continua de los servicios brindados mediante indicadores de desempeño (KPIs).

---

## 2. Principios Organizacionales

La organización del laboratorio se fundamenta en los siguientes principios:

- **Claridad en la asignación de responsabilidades:** Definición puntual de funciones operativas, técnicas y estratégicas.
- **Separación entre funciones administrativas y técnicas:** Desacople entre la gestión física de salas y la curaduría de software en contenedores.
- **Coordinación permanente entre docentes y administradores:** Alineación previa al inicio de cada semestre académico.
- **Gestión basada en procesos:** Estandarización de reservas, solicitudes de imágenes y gestión de incidencias.
- **Trazabilidad de las actividades realizadas:** Registro auditable mediante SBOM, firmas digitales (*Cosign*) y métricas de uso.
- **Mejora continua mediante indicadores de desempeño:** Evaluación periódica de tiempos de respuesta, nivel de automatización y tasa de ocupación.

---

## 3. Organigrama General

El siguiente organigrama representa la estructura organizacional mínima propuesta para la operación del laboratorio:

![Organigrama del Laboratorio](img/organigrama-laboratorio.png)

## 4. Roles Organizacionales

### 4.1 Director de Tecnologías de Información
Es el responsable de establecer las políticas generales relacionadas con la infraestructura tecnológica de la institución y la gestión del laboratorio.

#### Responsabilidades
- Aprobar políticas tecnológicas, de seguridad y de licenciamiento de software.
- Autorizar inversiones en hardware local (servidores Proxmox) y recursos en la nube.
- Supervisar el funcionamiento general y el cumplimiento de metas del laboratorio.
- Aprobar proyectos de mejora y la transición hacia estándares empresariales.

---

### 4.2 Administrador del Laboratorio
Es el responsable directo de la operación física y la gestión diaria del laboratorio.

#### Responsabilidades
- Administrar recursos físicos (PCs, servidores, impresoras y equipamiento de red).
- Coordinar el uso y la reserva de los laboratorios físicos mediante validación QR.
- Gestionar inventarios y monitorear el estado operativo del hardware.
- Coordinar mantenimientos preventivos y correctivos.
- Supervisar las actividades del Equipo de Soporte Técnico.
- Gestionar incidencias operativas y garantizar el control de acceso.

---

### 4.3 Responsable del Catálogo de Imágenes
Es el encargado de administrar el repositorio oficial de contenedores utilizados por los cursos y proyectos.

#### Responsabilidades
- Validar, empaquetar e importar nuevas imágenes Docker / Podman al registry privado (**Harbor**).
- Mantener actualizado el catálogo y gestionar el historial de versiones por asignatura.
- Verificar vulnerabilidades de seguridad en las imágenes utilizando herramientas de escaneo (**Trivy / Grype**).
- Aprobar nuevas versiones, generar el inventario de software (**SBOM**) y firmar digitalmente las imágenes (**Cosign**).
- Documentar los cambios realizados y asegurar que las imágenes estén disponibles para descarga local por parte de los estudiantes.

---

### 4.4 Equipo de Soporte Técnico
Brinda soporte operativo y de conectividad de primer nivel a estudiantes y docentes.

#### Responsabilidades
- Resolver incidencias técnicas en las estaciones de trabajo del laboratorio.
- Instalar y reconfigurar equipos físicos cuando sea necesario.
- Verificar el correcto funcionamiento del hardware, periféricos y conectividad local.
- Registrar problemas detectados para el análisis de causa raíz.

---

### 4.5 Docentes
Representan a los responsables académicos de cada curso y actúan como *Product Owners* de sus entornos de enseñanza.

#### Responsabilidades
- Solicitar imágenes de software requeridas para sus asignaturas con anticipación al inicio del semestre.
- Definir necesidades tecnológicas específicas para prácticas, evaluaciones y proyectos.
- Validar los recursos e imágenes provistas en Harbor antes de iniciar sus sesiones.
- Reservar bloques horarias para sus clases y supervisar el correcto uso de la infraestructura por parte de los alumnos.

---

### 4.6 Estudiantes
Son los usuarios finales directos de los recursos del laboratorio.

#### Responsabilidades
- Utilizar correctamente los recursos físicos y virtuales asignados.
- Cumplir las políticas de uso, reserva y normas de convivencia del laboratorio.
- Reportar incidencias o fallas en el software/hardware oportunamente.
- Utilizar únicamente imágenes oficiales autorizadas y descargarlas para sus prácticas en PCs personales.

---

## 5. Chapter de Organización y Procesos
Como parte del modelo organizacional propuesto, se incorpora un **Chapter de Organización y Procesos**, integrado por docentes con experiencia en gestión organizacional, arquitectura e ingeniería de procesos.

Su finalidad es asegurar que los procesos del laboratorio permanezcan documentados, estandarizados y alineados con los objetivos institucionales y las metodologías ágiles del proyecto.

### Responsabilidades Principales
- Diseñar y modelar nuevos procesos operativos bajo notación **BPMN**.
- Revisar y optimizar los procesos existentes de forma periódica.
- Mantener actualizada la documentación técnica y funcional en el repositorio GitHub.
- Definir indicadores de gestión (**KPIs**) y dar seguimiento a su cumplimiento.
- Coordinar auditorías internas de seguridad, licenciamiento y trazabilidad de software.
- Promover la mejora continua conectando los *Squads* de desarrollo con el equipo de operaciones.

---

## 6. Relaciones entre Roles
La interacción entre los diferentes actores se desarrolla de la siguiente manera:

- **El Director de Tecnologías de Información** establece las políticas generales y directrices estratégicas.
- **El Administrador del Laboratorio** coordina la operación diaria física y el trabajo del soporte técnico.
- **El Responsable del Catálogo de Imágenes** administra la plataforma Harbor y asegura la disponibilidad de entornos virtualizados.
- **Los Docentes** definen los requerimientos académicos y alimentan el flujo de solicitudes de imágenes.
- **El Equipo de Soporte Técnico** atiende las incidencias operativas en el sitio.
- **El Chapter de Organización y Procesos** audita los flujos, evalúa métricas y actualiza las mejores prácticas.
- **Los Estudiantes** consumen los recursos de forma autónoma respetando las políticas establecidas.

Esta distribución permite mantener una adecuada separación entre responsabilidades estratégicas, tácticas y operativas.

---

## 7. Beneficios de la Estructura Organizacional
La implementación de esta estructura permite:

- Mejor distribución y claridad de responsabilidades entre el personal técnico y docente.
- Mayor control y seguridad sobre los recursos tecnológicos físicos y digitales.
- Disminución de tiempos de respuesta en la configuración de entornos de aprendizaje.
- Mejor coordinación entre las distintas áreas académicas y administrativas.
- Mayor trazabilidad de las actividades, cambios de software e imágenes utilizadas.
- Facilita la implementación y automatización de procesos BPMN.
- Favorece la mejora continua mediante el análisis sistemático de indicadores.

---

## 8. Procesos Operativos Principales

### 8.1 Proceso: Pedido de Imágenes de Contenedores para Cursos
Este flujo garantiza que los entornos de software requeridos por los docentes estén probados, libres de vulnerabilidades y disponibles en el registry privado (**Harbor**) antes del inicio de clases.

1. **Solicitud de Requerimientos (Docente):** Con mínimo 2 semanas de anticipación al inicio del semestre, el docente registra la solicitud especificando sistema operativo base, lenguaje, librerías y herramientas requeridas.
2. **Evaluación de Factibilidad y Licencias (Resp. de Imágenes):** Se analiza si la imagen existe en Harbor o si debe construirse un `Dockerfile` personalizado, verificando que no incumpla políticas de software ni licencias restrictivas.
3. **Construcción y Escaneo de Vulnerabilidades:** Se construye la imagen y se ejecuta un análisis automatizado con **Trivy**. Si se detectan vulnerabilidades críticas, se aplican parches o se notifica al docente.
4. **Firma Digital y Publicación (Cosign):** Una vez aprobada, la imagen se firma digitalmente con **Cosign**, se le asigna su **SBOM** (inventario de software) y se etiqueta oficialmente en Harbor para su libre descarga.
5. **Validación Final (Docente):** El docente descarga y prueba la imagen en el laboratorio para dar su conformidad final.

---

### 8.2 Proceso: Separación de Horarios de Laboratorio (Cursos y Proyectos)
Este proceso regula la asignación de recursos físicos y capacidad de cómputo para evitar traslapes de horarios y optimizar el uso de las salas.

1. **Carga del Horario Académico Base (Administrador del Lab):** Al inicio del semestre, el Administrador del Laboratorio ingresa en el sistema el horario oficial de clases fijas aprobadas por la facultad.
2. **Solicitud de Bloques Especiales (Docentes / Investigadores):** Para sesiones extraordinarias, exámenes, laboratorios de recuperación o proyectos especiales, el docente solicita la reserva de franjas horarias a través de la plataforma.
3. **Validación de Disponibilidad y Aprobación:** El sistema verifica de forma automática si existen cruces de horarios o capacidad física/servidores disponibles en Proxmox:
   - **Si hay disponibilidad:** La reserva se aprueba automáticamente y se bloquea el aula/recursos.
   - **Si hay conflicto:** El Administrador del Laboratorio interviene para proponer un horario alternativo o ajustar la asignación.
4. **Habilitación de Reservas Libres (Estudiantes):** Las franjas horarias no ocupadas por clases o proyectos quedan disponibles para que los estudiantes reserven estaciones de trabajo de forma autónoma mediante validación por código QR.

