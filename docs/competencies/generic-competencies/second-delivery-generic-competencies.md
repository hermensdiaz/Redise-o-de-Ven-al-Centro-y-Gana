# Generic Competencies — Second Delivery

**Competencias genéricas desarrolladas en la segunda entrega**

Las siguientes competencias transversales se fortalecieron durante la segunda entrega del proyecto **«Ven al Centro y Gana»**. Para cada una se argumenta **cómo se promovió** mediante actividades específicas del desarrollo del producto y **dónde está la evidencia** en el repositorio.

> Las competencias de la primera entrega se conservan en [competencias genéricas.md](<competencias genéricas.md>).

---

## 1. Uso de la inteligencia artificial para automatizar el proceso de ingeniería

**Descripción:** Capacidad de integrar una herramienta de inteligencia artificial (IA) como asistente dentro del proceso de ingeniería de software, para automatizar tareas repetitivas o extensas, manteniendo el criterio y la decisión final en el equipo.

**Cómo se promovió:**
- **Auditoría del repositorio contra la rúbrica:** la IA revisó los archivos de la rama `segunda-entrega` y los comparó con la lista de cotejo de la entrega. Así el equipo identificó qué faltaba (bitácoras, validación con el cliente, métricas) y priorizó el trabajo.
- **Redacción asistida de artefactos:** la IA generó los borradores de los requisitos nuevos (RF-016 a RF-021, RNF-007 a RNF-012), la actualización a la versión 2.0 de RF-001 a RF-015, las historias de usuario HU-016 a HU-021 y la priorización MoSCoW, siguiendo el formato que el equipo ya usaba.
- **Prototipado automatizado:** mediante la conexión con Figma, la IA construyó las 17 pantallas del flujo v2 a partir de los requisitos, con los colores y tipografías definidos por el equipo, y después extrajo las capturas para la documentación.
- **Diagramas como código:** el diagrama de casos de uso v2 se generó en PlantUML, un formato de texto que se puede versionar y regenerar.
- **Detección de inconsistencias:** la IA midió el contraste de colores (WCAG) y encontró errores de trazabilidad heredados de la primera entrega, como RF-013, que apuntaba a RF-008 y RF-009 en lugar de RF-014 y RF-015.

**Supervisión humana (lo que aprendimos):** la IA no sustituyó las decisiones del equipo:
- El equipo **corrigió el contenido generado** cuando no era adecuado. Por ejemplo, el commit `fix: incorrect information` retiró una sección de la priorización.
- El equipo **tomó las decisiones de producto**, como no mostrar el folio en pantalla porque requería cambios en el backend.
- El equipo **editó el diseño en Figma** directamente después de la propuesta de la IA.
- El equipo **revisó cada documento antes de subirlo**, sobre todo los que tienen implicaciones legales.

También aprendimos los **límites prácticos** de la herramienta: los límites de uso del plan gratuito de Figma, la necesidad de verificar cada dato generado y la conveniencia de documentar qué se generó de forma automática.

**Evidencia:**
- Historial de commits de la rama `segunda-entrega`, firmados como coautoría con la IA.
- [Control de cambios de requisitos](../../requirements/cambios-segunda-entrega.md).
- [Diagrama de casos de uso v2 (fuente PlantUML)](../../UML/casos-de-uso-v2.puml).
- [Capturas del diseño v2](../../design/screens.md).

---

## 2. Pensamiento crítico y toma de decisiones

**Descripción:** Capacidad de evaluar alternativas, cuestionar propuestas (incluidas las generadas por IA) y tomar decisiones justificadas.

**Cómo se promovió:**
- **Priorización con criterios explícitos:** se clasificaron los 22 requisitos funcionales y los 12 no funcionales con el método MoSCoW, según cinco criterios: objetivo del producto, evidencia de campo, obligación legal, dependencias y esfuerzo.
- **Decisiones de alcance:** se decidió no mostrar el folio en pantalla (RF-014) para no modificar el backend, y se documentó el motivo.
- **Registro de discrepancias:** en lugar de ocultar los problemas, se documentaron las discrepancias entre el diseño y los requisitos (contraste de RNF-005, reglas de la trivia sin confirmar en las bases) para resolverlas con el cliente.

**Evidencia:** [Priorización de requisitos](../../requirements/priorizacion-requisitos.md) · [Control de cambios, sección 3](../../requirements/cambios-segunda-entrega.md).

---

## 3. Trabajo en equipo y colaboración con control de versiones

**Descripción:** Capacidad de coordinar el trabajo de varias personas sobre los mismos artefactos sin perder información.

**Cómo se promovió:**
- **Rama dedicada:** se trabajó en `segunda-entrega`, separada de `main`.
- **Convención de commits:** se adoptó Conventional Commits (`feat`, `fix`, `docs`, `refactor`, `chore`) para que el historial sea legible.
- **Sincronización constante:** antes de subir cambios se actualizó la rama, para no sobrescribir el trabajo de otros integrantes; los cambios manuales del equipo, como la corrección de la priorización, se respetaron.
- **Revisión automática:** el workflow de GitHub Actions revisa que no queden marcadores de conflicto en los pull requests.

**Evidencia:** [README, sección Flujo de trabajo](../../../README.md#flujo-de-trabajo) · historial de commits de `segunda-entrega`.

---

## 4. Gestión de la información y trazabilidad

**Descripción:** Capacidad de organizar la información del proyecto para que cualquier cambio se pueda rastrear hasta su origen.

**Cómo se promovió:**
- **Historial de cambios en cada artefacto:** cada RF, RNF e historia de usuario modificado incluye una tabla con la versión anterior, la fecha y el cambio realizado.
- **Matriz de trazabilidad:** relaciona cada pantalla del diseño con sus RF, HU y RNF.
- **Conservación de versiones anteriores:** el diagrama de casos de uso v1 (PDF) se conserva junto al v2 como evidencia de la evolución.

**Evidencia:** [Matriz de pantallas](../../design/screens.md) · [Diagramas UML](../../UML/README.md) · tablas "Historial de cambios" en `docs/requirements` y `docs/user-stories`.

---

## 5. Comunicación escrita clara

**Descripción:** Capacidad de redactar textos comprensibles para públicos distintos: usuarios finales, cliente y equipo técnico.

**Cómo se promovió:**
- **Redacción para el usuario final:** los textos de la interfaz se escribieron en lectura fácil, con trato de "tú" y botones con verbos de acción. Este criterio quedó formalizado en RNF-012.
- **Redacción técnica:** los requisitos siguen una estructura estándar (objetivo, alcance, precondiciones, flujos, trazabilidad, métrica), y los criterios de aceptación usan el formato Dado / Cuando / Entonces.
- **README con formato profesional:** se reestructuró la página principal del repositorio para que cualquier persona entienda el proyecto en pocos minutos.

**Evidencia:** [RNF-012](../../requirements/non-functional/RNF-012.md) · [Historias de usuario](../../user-stories/README.md) · [README](../../../README.md).

---

## 6. Ética y responsabilidad en el manejo de datos

**Descripción:** Capacidad de considerar el impacto legal y ético de las decisiones de diseño sobre las personas usuarias.

**Cómo se promovió:**
- **Protección de datos personales:** se definió un requisito de seguridad para mostrar el número telefónico parcialmente oculto en pantallas públicas (RNF-011).
- **Transparencia:** el aviso de privacidad se acepta solo en el formulario donde se capturan los datos (RF-008), y el acceso a las bases oficiales se mantiene visible (RF-003).
- **Trazabilidad con fines legales:** cada cambio de requisito quedó documentado con su origen.
- **Uso responsable de la IA:** se dejó constancia de qué partes fueron asistidas por IA y de que todas fueron revisadas por el equipo.

**Evidencia:** [RNF-011](../../requirements/non-functional/RNF-011.md) · [RF-008](../../requirements/functional/RF-008.md) · [Control de cambios](../../requirements/cambios-segunda-entrega.md).
