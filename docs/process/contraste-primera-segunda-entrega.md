# Contraste entre la primera y la segunda entrega

Este documento compara el estado del proyecto al cierre de cada entrega: qué se entregó, cómo se trabajó y qué cambió en la calidad de los artefactos.

| | Primera entrega | Segunda entrega |
|---|---|---|
| **Periodo** | 29/09/2026 al 05/10/2026 | 18/10/2026 al 31/10/2026 |
| **Punto de referencia** | Commit [23193bd](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/23193bd) en `main` | Rama [`segunda-entrega`](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/tree/segunda-entrega) |
| **Enfoque** | Definir el problema y la primera versión de los requisitos | Corregir los requisitos con el feedback, diseñar las interfaces y validar con el cliente |

---

## 1. Entregables

| Entregable | Primera entrega | Segunda entrega |
|---|---|---|
| Propuesta | Problemática y propuesta de solución | Corregida y alineada con el diseño v2 |
| Requisitos funcionales | 15 (RF-001 a RF-015) | 22 (RF-001 a RF-021; RF-004 se dividió en A y B), versión 2.0 |
| Requisitos no funcionales | 6 (RNF-001 a RNF-006) | 12 (RNF-001 a RNF-012), versión 2.0 |
| Historias de usuario | No había | 22 (HU-001 a HU-021, con HU-004-A y HU-004-B), con criterios de aceptación |
| Diagrama de casos de uso | Versión 1.0 en PDF | Versión 2.0 en PlantUML, PNG y SVG (la v1 se conserva) |
| Priorización de requisitos | No había | Priorización MoSCoW y orden de implementación |
| Control de cambios | No había | Registro de requisitos nuevos y modificados |
| Diseño de interfaces | No había | Prototipo en Figma (v2), guía de diseño y 17 capturas de pantallas |
| Validación con el cliente | No se realizó | Diseño aprobado por el cliente |
| Feedback del revisor | No se documentó | [Comentarios y feedback](../comentarios-y-feedback/feedback-cesar-rodriguez.md) de César Rodríguez, con las correcciones enlazadas |
| Competencias | Genéricas y específicas | Se agregaron las de la segunda entrega |
| Métrica individual | Por contribuciones asignadas (todos al 100 %) | Por participación en el periodo, a partir del issue #38 |
| Registro de prompts de IA | No había | [40 prompts](../prompts/README.md) documentados con su resultado |
| Video | Guion, edición y subtítulos | Guion y diapositivas de la presentación |

---

## 2. Calidad de los requisitos

En la primera entrega, los requisitos tenían problemas de forma y de contenido que el revisor señaló. En la segunda se corrigieron siguiendo su feedback.

| Aspecto | Primera entrega | Segunda entrega |
|---|---|---|
| Actor | "El concursante (cliente que participa en la dinámica)" | "El Concursante (Usuario que participa en la dinámica)" |
| Flujo principal | Pasos en párrafos sueltos, sin numerar | Pasos numerados, uno por línea |
| Flujos alternos | Casos generales ("Número inválido") | Un flujo por caso, con su mensaje (por ejemplo, RF-004-A, A4: caracteres no numéricos) |
| Formato | Algunos RF en tabla (RF-014) y encabezados inconsistentes | Misma estructura de secciones en todos los RF |
| Métricas | Varias cualitativas o ausentes (RF-009, RF-013) | Cuantitativas, con porcentajes y condiciones medibles |
| Títulos | Varios RF se llamaban igual ("Registro de participación", "Trivia") | Cada título describe su función |
| Ortografía | Errores como "encale" o "scroll down indicator" | Corregidos |
| Trazabilidad | Algunas referencias incorrectas (RF-013 apuntaba a RF-008 y RF-009) | Corregidas; cada RF tiene una tabla de **Historial de cambios** |

**Ejemplo, métrica de RF-013:**
- Primera entrega: "La página debe mostrar las 3 preguntas, registrando cuánto es la tasa de éxito de las personas que registran sus tickets."
- Segunda entrega: "Al menos el 95 % de los concursantes que inician la trivia debe responder las 3 preguntas y presionar 'Terminar trivia' sin abandonar la pantalla."

---

## 3. Organización del repositorio

| Aspecto | Primera entrega | Segunda entrega |
|---|---|---|
| Nombres de carpetas | En español (`requisitos/`, `proceso/`, `bibliografia/`) | En inglés (`requirements/`, `process/`, `bibliography/`) |
| README | Decorativo (banners animados e insignias), con poca información del proyecto | Formato de proyecto real: contexto, problema, alcance, estado, documentación, estructura, flujo de trabajo y equipo |
| Plantillas | No había | Plantillas de issue, de pull request, de acuerdo, de bitácora y de tarea |
| Automatización | No había | Workflow de GitHub Actions que revisa marcadores de conflicto |
| Registro del proceso | Evidencias (fotos de la prueba de campo) | Además: bitácoras de reunión, acuerdos y tareas (`process/`) |
| Convención de commits | Mensajes libres ("Create RF-014.md", "Update evidencias.md") | [Conventional Commits](https://www.conventionalcommits.org/es/v1.0.0/) (`docs(...)`, `fix(...)`) |
| Ramas | Ramas por integrante (`Feature-Andrew`, `feature-Erick`) | `main` estable y `segunda-entrega` para el trabajo en curso |

---

## 4. Gestión del trabajo

| Aspecto | Primera entrega | Segunda entrega |
|---|---|---|
| Issues | 21 (#1 a #21), uno por bloque de trabajo | 13 (#38 a #62), con plantilla: origen, responsable, fechas, criterios de aceptación y prioridad |
| Asignación | Varios issues con muchos responsables (por ejemplo, #1 y #2) | Un responsable por tarea (TAR-002 a TAR-010) |
| Commits | 81 | 29 en la rama `segunda-entrega` |
| Pull requests | Fusiones directas por integrante | Pull requests con plantilla; dos reversiones (#56 y #57) para conservar `main` estable |
| Métrica individual | Contribuciones completadas ÷ asignadas | Participación en el periodo, respaldada por issues resueltos |

---

## 5. Uso de inteligencia artificial

| Aspecto | Primera entrega | Segunda entrega |
|---|---|---|
| Uso | No se documentó | Claude como agente para revisar, diseñar, redactar y subir cambios al repositorio |
| Roles del equipo | Líder e integrantes | Se agregaron roles de IA: orquestador de agentes de IA (Hermen), AI Manager (Erick) y Chief of Agents (Eduardo) |
| Trazabilidad | — | Cada prompt queda registrado en [docs/prompts](../prompts/README.md) con su commit |

---

## 6. Conclusión

La primera entrega estableció el problema y una primera versión de los requisitos. La segunda convirtió esa base en un proyecto verificable: requisitos medibles y trazables, historias de usuario, un diseño validado con el cliente y un repositorio organizado con un proceso documentado. Los pendientes que quedan son principalmente de redacción y de confirmación con el cliente, y se listan en el [to do de la segunda entrega](to-do-segunda-entrega.md).
