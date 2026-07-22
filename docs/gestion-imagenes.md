# Gestión de Imágenes y Trazabilidad

## Flujo Principal

1. Solicitud de imagen (Proyecto o Curso)
2. Búsqueda automática en Harbor
3. Si no existe → Responsable revisa y aprueba creación
4. Escaneo de vulnerabilidades (Trivy)
5. Firma de imagen
6. Publicación con metadatos de trazabilidad
7. Estudiantes pueden descargar la imagen oficial

**Beneficio clave:** Los alumnos trabajan con el **mismo entorno** dentro y fuera del laboratorio.

**Comentario (Emanuel David Hilcondo Begazo):**  
El flujo de provisión de imágenes resuelve de raíz el clásico problema de inconsistencia de entornos ("funciona en mi máquina"). Al automatizar el escaneo de vulnerabilidades con Trivy y requerir firmas digitales antes de la publicación en Harbor, la plataforma impone un estándar de seguridad DevSecOps de nivel industrial. La asignación de metadatos de trazabilidad no solo facilita la auditoría del software utilizado en los cursos de Ingeniería de Sistemas cada semestre, sino que democratiza el acceso: permite a los alumnos replicar configuraciones complejas en sus equipos personales de forma segura e inmediata, optimizando el tiempo efectivo de programación en los laboratorios de la universidad.

**Comentario (Edson Fabricio Subia Huaicane):**  
El flujo cubre bien el ciclo seguro de las imágenes; le sumaría robustez operativa en dos puntos. Primero, manejo de fallos: si el escaneo (Trivy) o la firma no pasan, el proceso debería revertir a un estado consistente y notificar automáticamente, evitando imágenes a medio publicar en Harbor. Segundo, ciclo de vida: definiría una política de retención y limpieza de versiones antiguas para que el registry no crezca sin control, y expondría cada imagen por *digest* además del *tag*, de forma que la trazabilidad sea inmutable. Con eso, el paso 2 (búsqueda automática en Harbor) siempre resuelve a una versión exacta y reproducible, y no a un tag que pudo cambiar.

