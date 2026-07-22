# Modelo Organizacional Ágil - Spotify Adaptado


## Tribe Principal
**Nombre:** Platform Lab

## Squads - Proyecto Universitario (Fase 1)

- **Squad Core Platform**
- **Squad Image & Container Management**
- **Squad Hardware & Lab Operations**
- **Squad Frontend & User Experience**

## Squads - Proyecto Empresa (Fase 2)

- Squad Core Enterprise Platform
- Squad Advanced Image & Security
- Squad Hardware Fleet & Hybrid Operations
- Squad Enterprise Experience & Analytics
- Squad Integration & Ecosystem

## Roles de Profesores
Los **Chapters** serán liderados por profesores con experiencia en industria (mínimo 5 años).

**Chapters:**
- Chapter Backend & Arquitectura
- Chapter DevOps & Platform Engineering
- Chapter Security & Compliance
- Chapter Frontend & UX

<br>

> **Comentario (Mauro Snayder Sullca Mamani):**
> La propuesta organizacional basada en el Modelo Spotify facilita el desarrollo del proyecto mediante equipos multidisciplinarios. Como complemento, sería recomendable incorporar una estructura organizacional para la operación del laboratorio, definiendo los roles y responsabilidades de los actores involucrados en la gestión de los recursos y servicios.

> **Comentario (Christian Yana):**
>
> La adaptación del modelo Spotify al contexto académico está bien planteada. Para avanzar a ejecución, conviene especificar la configuración mínima en la primera etapa: número de squads y chapters a formar, responsables iniciales y entregables clave del primer sprint (por ejemplo: infraestructura mínima, catálogo inicial, runbooks). También es recomendable definir un par de métricas operativas para evaluar el progreso del modelo (por ejemplo: tiempo medio de ciclo de una solicitud y número de imágenes publicadas por mes).

> **Comentario de Edson Fabricio Subia Huaicane:**
> Buena adaptación del modelo. Para que la autonomía de los squads no genere retrabajo, enfatizaría dos cosas desde la ingeniería de sistemas: definir interfaces y *ownership* claros entre squads —sobre todo entre *Core Platform* e *Image & Container Management*, que comparten Harbor— y tratar lo transversal (CI/CD, seguridad, plantillas) como un *producto interno* que los Chapters mantienen y el resto consume, en lugar de que cada squad reinvente lo mismo. Alinear los límites de los squads con los límites técnicos del sistema (ley de Conway) reduce dependencias cruzadas; y, junto a las métricas ya propuestas, añadiría una de acoplamiento (porcentaje de historias que requieren coordinar con otro squad) para saber si el modelo realmente está dando autonomía.

