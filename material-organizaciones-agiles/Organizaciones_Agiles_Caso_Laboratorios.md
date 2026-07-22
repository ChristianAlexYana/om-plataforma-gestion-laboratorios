# Organizaciones Ágiles para Problemas Complejos

**El Modelo Spotify aplicado a un caso real: la Plataforma Híbrida de Gestión de Laboratorios de Computación**

Curso de Organización y Métodos · Julio 2026

---

## 1. Introducción

La disciplina de Organización y Métodos (O&M) estudia cómo diseñar estructuras, procesos y flujos de trabajo que permitan a una institución cumplir sus objetivos de forma eficiente. Durante d[...]

El presente material aborda un escenario distinto: el diseño organizacional para problemas complejos, es decir, problemas con múltiples partes interesadas, tecnología cambiante, requisitos que [...]

---

## 2. Problemas complejos: por qué la organización tradicional no basta

### 2.1 El entorno VUCA

La sigla VUCA (Volatility, Uncertainty, Complexity, Ambiguity) describe entornos donde el cambio es rápido y difícil de anticipar (volatilidad), la información disponible es insuficiente para p[...]

### 2.2 El marco Cynefin: distinguir tipos de problema

El marco Cynefin, desarrollado por Dave Snowden, clasifica los problemas en cuatro dominios y es útil para decidir qué tipo de organización aplicar a cada uno:

- **Simple (claro):** relación causa-efecto evidente. Se resuelve con procedimientos estandarizados y buenas prácticas. Ejemplo: check-in de un equipo en el inventario.
- **Complicado:** requiere conocimiento experto para identificar la solución, pero es analizable. Ejemplo: configurar una red o un clúster de Kubernetes.
- **Complejo:** la relación causa-efecto solo se comprende en retrospectiva; no hay una única solución correcta de antemano. Requiere experimentar, observar y adaptar ("probar-sentir-responder")[...]
- **Caótico:** no hay relación causa-efecto discernible; se requiere actuar primero para estabilizar la situación. Ejemplo: una caída total del laboratorio en plena evaluación.

> **Idea central:** los problemas complejos no se resuelven con más planificación anticipada, sino con estructuras organizacionales que permitan experimentar rápido, aprender del error y ajusta[...]

Una organización jerárquica clásica —con aprobaciones en cascada y especialización rígida por departamento— es eficiente para lo simple y lo complicado, pero se vuelve lenta y frágil fre[...]

---

## 3. Agilidad organizacional (más allá del equipo)

La agilidad organizacional traslada los principios ágiles —iteración corta, entrega incremental, retroalimentación continua, autonomía del equipo— desde el nivel de un solo equipo de desar[...]

### 3.1 El equilibrio entre autonomía y alineación

El reto central del diseño organizacional ágil es lograr que los equipos tengan autonomía suficiente para decidir cómo resolver un problema (sin esperar aprobaciones de arriba hacia abajo para[...]

Cuando la autonomía es alta pero la alineación es baja, el resultado es caos: equipos desconectados, duplicación de esfuerzo, inconsistencias. Cuando la alineación es alta pero la autonomía e[...]

---

## 4. El Modelo Spotify

El Modelo Spotify es un patrón de diseño organizacional que la empresa Spotify popularizó (aunque la propia compañía aclara que evolucionó y nunca fue un modelo "cerrado") para escalar equip[...]

### 4.1 Squad

Es la unidad básica: un equipo pequeño, multidisciplinario (5-9 personas) y autónomo, con todas las competencias necesarias para diseñar, construir y entregar una parte del producto de princip[...]

### 4.2 Tribe

Agrupa varios squads que trabajan en un área de producto relacionada (por ejemplo, toda la plataforma de un mismo proyecto). El tribe coordina la visión general y evita que los squads dupliquen [...]

### 4.3 Chapter

Es la agrupación transversal de personas que comparten la misma disciplina o especialidad (por ejemplo, todos los desarrolladores backend, aunque estén repartidos en distintos squads). El chapte[...]

### 4.4 Guild

Es una comunidad de interés informal y voluntaria que cruza toda la organización (por ejemplo, un guild de seguridad o de accesibilidad), abierta a cualquiera interesado en el tema, independient[...]

| Unidad | Tipo de agrupación | Propósito principal |
|---|---|---|
| Squad | Multidisciplinaria, por misión de producto | Entregar valor de forma autónoma y de punta a punta |
| Tribe | Conjunto de squads relacionados | Alinear visión y coordinar dependencias entre squads |
| Chapter | Por disciplina/especialidad técnica | Estandarizar calidad técnica y desarrollo profesional |
| Guild | Comunidad de interés voluntaria | Compartir conocimiento transversal |

*El resultado es una matriz: cada persona pertenece "verticalmente" a un squad (donde entrega valor día a día) y "horizontalmente" a un chapter (donde mantiene su desarrollo técnico), y opciona[...]

---

## 5. Por qué este diseño encaja con problemas complejos

- Reduce el tamaño del lote de decisión: al ser autónomo, un squad puede probar una solución, observar el resultado y corregir el rumbo en días, no en meses.
- Distribuye el conocimiento experto sin fragmentarlo: los chapters evitan que cada squad reinvente sus propios estándares.
- Permite escalar sin perder identidad de producto: los tribes agrupan squads por área de negocio, no por función, lo que mantiene el foco en el problema del usuario.
- Favorece el aprendizaje continuo, coherente con el dominio "complejo" de Cynefin: probar, sentir, responder, en vez de planificar-ejecutar-controlar.

---

## 6. El caso: Plataforma Híbrida de Gestión de Laboratorios de Computación

### 6.1 El problema

Los laboratorios de computación universitarios y las empresas de software comparten un mismo dolor: gestión fragmentada de recursos físicos y digitales, tiempo perdido en instalaciones manuales[...]

El proyecto propone una plataforma híbrida (local + nube) que integre gestión de hardware, usuarios, proyectos/cursos, repositorios de código (GitLab) y un catálogo centralizado de imágenes d[...]

### 6.2 ¿Por qué es un problema complejo (y no solo complicado)?

Aplicando el marco Cynefin al caso: no existe una única arquitectura "correcta" conocida de antemano, porque las necesidades de un aula universitaria (bajo presupuesto, alta rotación de estudia[...]

### 6.3 Aplicación del Modelo Spotify: el Tribe "Platform Lab"

El proyecto organiza a los estudiantes y docentes bajo un Tribe único llamado "Platform Lab", que evoluciona en dos fases secuenciales.

| Fase 1 – Proyecto Universitario | Fase 2 – Proyecto Empresa (evolución) |
|---|---|
| Squad Core Platform | Squad Core Enterprise Platform |
| Squad Image & Container Management | Squad Advanced Image & Security |
| Squad Hardware & Lab Operations | Squad Hardware Fleet & Hybrid Operations |
| Squad Frontend & User Experience | Squad Enterprise Experience & Analytics |
| — | Squad Integration & Ecosystem |

Cada squad es multidisciplinario y responsable de una porción vertical del producto (por ejemplo, el squad de imágenes cubre desde el diseño hasta la entrega del catálogo de contenedores), re[...]

### 6.4 Chapters liderados por docentes

Los Chapters agrupan a los estudiantes por especialidad técnica, transversalmente a los squads, y están liderados por profesores con un mínimo de cinco años de experiencia en la industria, lo[...]

- Chapter Backend & Arquitectura
- Chapter DevOps & Platform Engineering
- Chapter Security & Compliance
- Chapter Frontend & UX

### 6.5 El dilema organizacional: ¿dónde ubicar la gestión de procesos?

Durante la planificación del backlog surgió una pregunta típica del diseño organizacional ágil: los procesos administrativos del laboratorio (reserva de equipos, aprobación de imágenes, ma[...]

> **Solución adoptada:** un Chapter de "Organización y Procesos" liderado por un docente con experiencia en Gestión de Proyectos o ITIL, combinado con un rol de Process Owner (u "Organization [...]

Esta decisión ilustra en la práctica el principio de autonomía + alineación: cada squad sigue siendo dueño de sus procesos (autonomía), mientras el Chapter transversal garantiza una matriz [...]

### 6.6 Cadencia y artefactos ágiles del proyecto

- Dedicación semanal: 15-20 horas/estudiante en la Fase 1 (Universitaria) y 20-25 horas/estudiante en la Fase 2 (Empresa).
- Ritmo de coordinación: 2 reuniones de squad y 1 revisión con el Chapter (docente) por semana.
- Backlog priorizado con MoSCoW (Must/Should/Could/Won't have), organizado en épicas: Organización y Procesos, Usuarios y Permisos, Catálogo de Imágenes, Hardware e Inventario, Frontend, Arqu[...]
- Fases de implementación: Análisis y Diseño (1 mes) → Proyecto Universitario (4-6 meses) → Evolución a Proyecto Empresa (5-7 meses) → Piloto → Mejora continua.

---

## 7. Lecciones para el diseño organizacional

- La estructura debe reflejar el tipo de problema: procesos simples/complicados admiten jerarquía y procedimiento; problemas complejos requieren squads autónomos que aprendan iterando.
- La agilidad organizacional no elimina la necesidad de coordinación: los Chapters y la matriz RACI muestran que "ágil" no significa "sin estructura", sino una estructura distinta, orientada a [...]
- Los dilemas organizacionales (como "¿dónde va Organización y Procesos?") rara vez se resuelven creando más unidades separadas; con frecuencia la mejor respuesta es un rol transversal combin[...]
- Un mismo diseño organizacional (Tribe → Squads → Chapters) puede evolucionar de un contexto académico a uno empresarial simplemente ajustando el número y enfoque de los squads, sin redis[...]

---

## 8. Conclusiones

El caso de la Plataforma Híbrida de Gestión de Laboratorios muestra que Organización y Métodos, aplicada a problemas complejos, no consiste en imponer un procedimiento fijo sino en diseñar u[...]

---

## 9. Preguntas de discusión

1. ¿Qué otros procesos del laboratorio caen en el dominio "complicado" (procedimiento claro) frente a los que caen en el dominio "complejo" (requieren experimentación)?

- **Comentario (Mauro Snayder Sullca Mamani):** Los procesos complicados son los operativos e infraestructurales que cuentan con un procedimiento técnico claro y predecible —como el mantenimiento de hardware, el alta de inventario, la configuración de redes/impresoras o el control de acceso físico por código QR—, mientras que los procesos complejos son aquellos donde las necesidades cambian constantemente y requieren experimentar para encontrar la mejor solución, tales como la curaduría del catálogo de imágenes en Harbor, la automatización de actualizaciones de software sin romper proyectos activos, y el ajuste de políticas de seguridad al escalar del entorno universitario al empresarial.

- **Comentario (Rodrigo Estefanero):** Lo complicado suele ser lo netamente técnico pero predecible, como configurar la red híbrida o establecer los pipelines de despliegue iniciales. Lo complejo, en mi experiencia, recae en la adopción del producto y el soporte técnico; por ejemplo, entender por qué un grupo de estudiantes no adopta la plataforma o cómo reaccionar en tiempo real ante un incidente de seguridad crítico en un entorno corporativo, donde no hay manuales estrictos y toca adaptarse sobre la marcha.

- **Comentario (Christian Yana):** Buena distinción. Propongo añadir una frase breve que diferencie "complicado" (procedimiento reproducible) de "complejo" (requiere experimentación) y un checklist de 3 ítems para clasificar procesos en la práctica.

- **Comentario (Emanuel David Hilacondo Begazo):** Considero que un proceso "complicado" sería el modelado analítico para la asignación óptima de horarios y recursos físicos, ya que requiere conocimiento experto en investigación de operaciones, pero tiene una solución calculable. En contraste, un proceso "complejo" es el diseño de la interfaz de usuario; aunque apliquemos heurísticas de usabilidad estandarizadas, lograr que toda la comunidad adopte el sistema requiere prototipado constante, evaluación de los patrones de interacción y adaptación continua basada en el comportamiento real de los usuarios.
  
<br>

2. Si el proyecto creciera a 10 squads, ¿en qué punto convendría dividir el Tribe "Platform Lab" en dos tribes independientes?

- **Comentario (Mauro Snayder Sullca Mamani):** Considero que el punto de quiebre para dividir el Tribe ocurre cuando las dependencias entre los 10 squads comienzan a generar cuellos de botella y las reuniones de alineación se vuelven ineficientes, momento en el cual sugiero separar la organización en dos Tribes especializadas: una enfocada en la infraestructura y operación física del laboratorio ("Lab Operations & Infrastructure" para hardware, Proxmox y reservas) y otra dedicada exclusivamente al desarrollo de la plataforma de software y seguridad ("Developer Platform & Enterprise Security" para contenedores, pipelines CI/CD y políticas de compliance).

- **Comentario (Rodrigo Estefanero):** Yo dividiría la Tribu en el momento en que la carga cognitiva empiece a afectar la agilidad general y nuestro tiempo de entrega (Time-to-Market) se dispare por exceso de reuniones. En lugar de separarlo por capas de infraestructura, propondría una división basada en el flujo de valor: una Tribu enfocada al 100% en la experiencia y agilidad del entorno Universitario, y otra dedicada puramente a los SLAs, seguridad y requerimientos rígidos del entorno Corporativo (Enterprise).

- **Comentario (Christian Yana):** Propongo un umbral práctico: considerar dividir cuando haya más de 8 squads o cuando más del 20% de las historias impliquen dependencias cruzadas que aumenten la coordinación; priorizar la separación por flujo de valor (Académico vs. Empresarial).

- **Comentario (Emanuel David Hilacondo Begazo):** Desde mi perspectiva, el punto crítico se alcanza cuando la complejidad técnica frena la entrega de valor y el diseño de la plataforma pierde coherencia global. Al llegar a ese límite operativo, sugiero separar la organización en una Tribu enfocada estrictamente en la infraestructura y operaciones híbridas, y otra dedicada puramente al desarrollo de software, la experiencia de usuario y la automatización inteligente.
  
<br>

3. ¿Qué riesgos organizacionales aparecen si el rol de Process Owner dentro de cada squad no tiene tiempo protegido para documentar procesos?

- **Comentario (Mauro Snayder Sullca Mamani):** Si como Process Owner no cuento con tiempo protegido para la documentación, el principal riesgo es la acumulación de "deuda de procesos" (process debt), lo que provocaría que el equipo priorice solo el código y genere un conocimiento informal que vive únicamente en las mentes de los desarrolladores; esto generaría silos de información y provocaría un colapso en la transferencia del proyecto al finalizar el semestre, obligando a los nuevos estudiantes a perder tiempo intentando descifrar cómo funciona la plataforma.

- **Comentario (Rodrigo Estefanero):** El riesgo inmediato es perder la trazabilidad operativa y fallar en posibles auditorías de calidad. Desde un enfoque DevSecOps, un proceso no documentado es un proceso inauditable y un cuello de botella en potencia. Si no hay estándares escritos, no podremos automatizar tareas a futuro, lo que ralentizará dramáticamente nuestra capacidad de respuesta ante incidentes (MTTR) cuando el proyecto escale a empresas.

- **Comentario (Christian Yana):** Sugiero reservar 1 día a la semana (≈20% del tiempo) para que el Process Owner documente procesos y mantener un runbook mínimo por proceso; además, medir el % de procesos con runbook y owner asignado como KPI.

- **Comentario (Emanuel David Hilacondo Begazo):** El mayor riesgo es la acumulación de deuda técnica y la pérdida de la lógica fundacional del sistema. Si los equipos desarrollan flujos automatizados avanzados o scripts complejos en lenguajes como Python o C++ sin documentar sus parámetros y arquitectura, el código se vuelve inmanejable. Esto genera silos de información que bloquean por completo la transferencia de responsabilidades cuando ocurre la rotación natural de estudiantes al finalizar el semestre académico.
  
<br>

4. ¿Cómo mediría usted, con indicadores concretos, si el modelo está logrando el equilibrio entre autonomía y alineación?

- **Comentario (Mauro Snayder Sullca Mamani):** Para medir este equilibrio evaluaría, por un lado, la autonomía mediante el Cycle Time (logrando que un squad publique cambios en Harbor en menos de 48 horas sin bloqueos entre equipos) y, por otro lado, la alineación midiendo el índice de compliance (asegurando que el 100% de las imágenes cumpla con los estándares del Chapter mediante escaneos de Trivy sin vulnerabilidades críticas y firmas de Cosign), garantizando así que los squads avancen rápido pero bajo un mismo marco de calidad.

- **Comentario (Rodrigo Estefanero):** Me apoyaría directamente en las métricas DORA. La autonomía la evidenciaría con una alta Frecuencia de Despliegue (Deployment Frequency), comprobando que los equipos pueden lanzar valor a producción sin depender de otros. La alineación la controlaría con la Tasa de Fallos (Change Failure Rate); si los equipos son verdaderamente autónomos pero respetan los estándares técnicos definidos por su Chapter, la innovación será constante pero la tasa de errores se mantendrá al mínimo.

- **Comentario (Christian Yana):** Para empezar, propongo 3 KPIs sencillos: Cycle Time de publicación en Harbor, MTTR y % de imágenes con SBOM y firma. Revisar estas métricas trimestralmente y ajustar metas.

- **Comentario (Emanuel David Hilacondo Begazo):** Propongo utilizar métricas mixtas para tener una visión completa. La autonomía puede medirse por la velocidad con la que un Squad logra integrar una nueva funcionalidad en la plataforma de manera independiente. La alineación debe auditarse garantizando que todas las entregas cumplan con los criterios unificados de su respectivo Chapter, como aprobar estrictamente evaluaciones bajo estándares ISO o criterios de usabilidad de Nielsen, asegurando que la agilidad del equipo no comprometa la calidad ni la consistencia del ecosistema.
  


