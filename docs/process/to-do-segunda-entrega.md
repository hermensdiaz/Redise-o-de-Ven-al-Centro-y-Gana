# To do · Segunda entrega

Lista de todo el trabajo de la segunda entrega: las tareas asignadas como issues, lo que se hizo con Claude (agente de IA) y lo que todavía está pendiente.

**Rama:** `segunda-entrega` · **Periodo:** del 18/10/2026 al 31/10/2026

**Simbología:** `[x]` terminado · `[ ]` pendiente

---

## 1. Issues asignados

Tareas registradas como issues desde el issue #38 "Arreglar requisitos". Todas están cerradas.

| Estado | Issue | Tarea | Responsable | Apoyo | Cierre |
|---|---|---|---|---|---|
| [x] | [#38](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/38) | Arreglar requisitos (RF, RNF y casos de uso; métricas cuantificables) | Erick | Hermen | 22/10/2026 |
| [x] | [#41](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/41) | Corregir los RF-001, RF-004, RF-008, RF-009, RF-013 y RF-015 | Hermen | — | 22/10/2026 |
| [x] | [#45](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/45) | TAR-002 · Correcciones en Figma de RF-001, RF-002 y RF-003 | Erick | — | 29/10/2026 |
| [x] | [#48](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/48) | TAR-003 · Correcciones en Figma de RF-004-A y RF-004-B | Manuel | — | 31/10/2026 |
| [x] | [#49](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/49) | TAR-004 · Correcciones en Figma de RF-005 | Manuel | — | 31/10/2026 |
| [x] | [#50](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/50) | TAR-005 · Correcciones en Figma de RF-006, RF-007 y RF-008 | Hermen | — | 31/10/2026 |
| [x] | [#51](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/51) | TAR-006 · Correcciones en Figma de RF-009, RF-010 y RF-011 | Alessandra | — | 30/10/2026 |
| [x] | [#52](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/52) | TAR-007 · Correcciones en Figma de RF-012 | Eduardo | — | 31/10/2026 |
| [x] | [#53](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/53) | TAR-008 · Correcciones en Figma de RF-013 | Eduardo | — | 31/10/2026 |
| [x] | [#54](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/54) | TAR-009 · Correcciones en Figma de RF-014 | Andrew | — | 31/10/2026 |
| [x] | [#55](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/55) | TAR-010 · Correcciones en Figma de RF-015 | Andrew | — | 31/10/2026 |
| [x] | [#61](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/61) | TAR-11 · Grabar el vídeo | Sin asignar | — | 31/10/2026 |
| [x] | [#62](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/62) | TAR-12 · Editar el vídeo | Sin asignar | — | 31/10/2026 |

> Los issues #61 y #62 no tienen responsable asignado en GitHub. Conviene asignarlos para que cuenten en la [métrica individual](metricas.md).

---

## 2. Trabajo realizado con Claude

Cada tarea enlaza al prompt original en el [registro de prompts](../prompts/README.md). Las que no generaron commit fueron consultas, revisiones o trabajo en Figma.

### 2.1 Chat «Historias de usuario»

| Estado | Hora | Tarea | Categoría | Commit |
|---|---|---|---|---|
| [x] | 09:46 | [Estructura para redactar historias de usuario](../prompts/33-estructura-de-historias-de-usuario.md) | Consulta | Sin commit |
| [x] | 09:55 | [Historias de usuario a partir de los requisitos funcionales](../prompts/34-historias-de-usuario-desde-los-rf.md) | Requisitos | Sin commit |
| [x] | 09:56 | [Cómo dar acceso al repositorio](../prompts/35-acceso-al-repositorio.md) | Consulta | Sin commit |
| [x] | 09:57 | [Conexión de la carpeta local](../prompts/36-conexion-de-la-carpeta-local.md) | Requisitos | Sin commit |
| [x] | 10:11 | [Cambio a la rama segunda-entrega](../prompts/37-cambio-a-la-rama-segunda-entrega.md) | Control de versiones | Sin commit |
| [x] | 10:12 | [Historias de usuario en la rama segunda-entrega](../prompts/38-historias-en-segunda-entrega.md) | Requisitos | [e8e5eeb](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/e8e5eeb) |

### 2.2 Chat «Renombrar carpetas a inglés»

| Estado | Hora | Tarea | Categoría | Commit |
|---|---|---|---|---|
| [x] | 09:47 | [Renombrar las carpetas del repositorio a inglés](../prompts/30-carpetas-en-ingles.md) | Organización del repositorio | [PR #59](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/pull/59) |
| [x] | 09:50 | [Renombrar las carpetas de la rama segunda-entrega a inglés](../prompts/31-carpetas-en-ingles-segunda-entrega.md) | Organización del repositorio | [PR #60](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/pull/60) |
| [x] | 09:51 | [Mensaje interrumpido](../prompts/32-mensaje-interrumpido.md) | Sin categoría | Sin commit |

### 2.3 Chat «Revisión y rediseño de la segunda entrega»

| Estado | Hora | Tarea | Categoría | Commit |
|---|---|---|---|---|
| [x] | 10:22 | [Acceso a la rama segunda-entrega](../prompts/06-acceso-a-la-rama-segunda-entrega.md) | Consulta | Sin commit |
| [x] | 10:23 | [Acceso a los repositorios remotos](../prompts/07-acceso-a-repositorios-remotos.md) | Consulta | Sin commit |
| [x] | 10:23 | [Acceso a los archivos de la rama](../prompts/08-acceso-a-los-archivos-de-la-rama.md) | Consulta | Sin commit |
| [x] | 10:24 | [Revisión del repositorio contra la lista de cotejo](../prompts/09-revision-contra-la-lista-de-cotejo.md) | Revisión | Sin commit |
| [x] | 10:36 | [Carpeta de diseño, enlace a Figma y guía de diseño](../prompts/10-carpeta-de-diseno-y-guia.md) | Diseño | [a921d34](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/a921d34) |
| [x] | 10:48 | [Ajustes de usabilidad al diseño](../prompts/11-ajustes-de-usabilidad-al-diseno.md) | Diseño | Sin commit |
| [x] | 11:11 | [Subir el diseño a Figma](../prompts/12-subir-el-diseno-a-figma.md) | Diseño | Sin commit |
| [x] | 11:12 | [Vincular otra cuenta de Figma](../prompts/13-vincular-otra-cuenta-de-figma.md) | Consulta | Sin commit |
| [x] | 11:15 | [Construir el diseño en otra cuenta de Figma](../prompts/14-diseno-en-otra-cuenta-de-figma.md) | Diseño | Sin commit |
| [x] | 11:54 | [Pantallas de resultado en Figma](../prompts/15-pantallas-de-resultado-en-figma.md) | Diseño | Sin commit |
| [x] | 12:12 | [Requisitos nuevos y modificados a partir del diseño](../prompts/16-requisitos-a-partir-del-diseno.md) | Requisitos | [c7fa2bd](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/c7fa2bd) |
| [x] | 12:22 | [Subir los requisitos a la rama](../prompts/17-subir-los-requisitos.md) | Control de versiones | [c7fa2bd](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/c7fa2bd) |
| [x] | 12:24 | [Casos de uso e historias de usuario](../prompts/18-casos-de-uso-e-historias-de-usuario.md) | Requisitos | [b9232c6](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/b9232c6) |
| [x] | 12:43 | [Priorización de requisitos (interrumpido)](../prompts/19-priorizacion-de-requisitos-interrumpido.md) | Requisitos | Sin commit |
| [x] | 12:44 | [Priorización de requisitos y convención de commits](../prompts/20-priorizacion-de-requisitos.md) | Requisitos | [2791d91](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/2791d91) |
| [x] | 12:56 | [Faltantes según la lista de cotejo](../prompts/21-faltantes-segun-la-lista-de-cotejo.md) | Revisión | Sin commit |
| [x] | 13:39 | [README con formato de proyecto real](../prompts/22-readme-con-formato-de-proyecto-real.md) | Documentación | [30025d6](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/30025d6) |
| [x] | 13:41 | [Capturas del diseño v2](../prompts/23-capturas-del-diseno-v2.md) | Diseño | [aadc84c](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/aadc84c) |
| [x] | 13:54 | [Competencias de la segunda entrega](../prompts/24-competencias-de-la-segunda-entrega.md) | Documentación | [8fc4f21](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/8fc4f21) |
| [x] | 14:03 | [Faltantes tras la validación del cliente](../prompts/25-faltantes-tras-la-validacion-del-cliente.md) | Revisión | Sin commit |
| [x] | 14:05 | [Corrección de la propuesta y de la guía de diseño](../prompts/26-correccion-de-propuesta-y-guia-de-diseno.md) | Documentación | [30a3b06](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/30a3b06) |
| [x] | 16:29 | [Guion y diapositivas de la presentación](../prompts/27-guion-y-diapositivas.md) | Presentación | Sin commit |
| [x] | 16:42 | [Guion para tres integrantes](../prompts/28-guion-para-tres-integrantes.md) | Presentación | Sin commit |
| [x] | 16:44 | [Consulta sobre el requisito del teléfono](../prompts/29-consulta-requisito-del-telefono.md) | Consulta | Sin commit |

### 2.4 Chat «Comentarios y feedback»

| Estado | Hora | Tarea | Categoría | Commit |
|---|---|---|---|---|
| [x] | 19:27 | [Carpeta de comentarios y feedback](../prompts/01-feedback-cesar-rodriguez.md) | Documentación | [6150af6](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/6150af6) |
| [x] | 19:40 | [Métrica individual y roles en el README](../prompts/02-metrica-individual-y-roles.md) | Gestión del equipo | [b3e280b](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/b3e280b) |
| [x] | 19:48 | [Métrica desde el issue "Arreglar requisitos"](../prompts/03-metrica-desde-arreglar-requisitos.md) | Gestión del equipo | [7c7e888](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/7c7e888) |
| [x] | 19:51 | [Estructura del repositorio en el README](../prompts/04-estructura-del-repositorio.md) | Documentación | [afafc62](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/afafc62) |
| [x] | 19:54 | [Registro de prompts](../prompts/05-registro-de-prompts.md) | Documentación | [Historial](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commits/segunda-entrega/docs/prompts) |
| [x] | 20:00 | [Prompt para registrar los otros chats](../prompts/39-prompt-para-registrar-otros-chats.md) | Consulta | Sin commit |
| [x] | 20:23 | [Contraste entre entregas y to do de la segunda entrega](../prompts/40-contraste-y-to-do-segunda-entrega.md) | Documentación | [Historial](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commits/segunda-entrega/docs/process) |

**Total:** 40 prompts en 4 chats; 18 de ellos produjeron un commit o pull request.

---

## 3. Pendientes

### 3.1 Redacción de requisitos (feedback de César Rodríguez)
Detalle en [Comentarios y feedback](../comentarios-y-feedback/feedback-cesar-rodriguez.md).

- [ ] Quitar "lograr" de las métricas de RF-009 y RF-015.
- [ ] Argumentar la métrica de RF-008 con un *health check* que respalde el 100 %.
- [ ] Reemplazar "debe" y "puede" por afirmaciones en RF-004-A, RF-007, RF-008, RF-009, RF-010, RF-013 y RF-015.
- [ ] Iniciar RF-007 y RF-008 con "El sistema permite…".

### 3.2 Discrepancias del rediseño
Detalle en el [control de cambios](../requirements/cambios-segunda-entrega.md), sección 3.

- [ ] RNF-005: alinear la paleta de colores del requisito con la del diseño.
- [ ] RNF-005: corregir el contraste del texto blanco sobre naranja y amarillo (mínimo 4.5:1).
- [ ] RF-012: confirmar con CANACO SERVYTUR y con las bases que "No hay límite de tiempo".
- [ ] RF-012 y RF-015: confirmar en las bases que cada intento requiere un ticket nuevo.
- [ ] RF-015 (Figma): corregir "registrado" por "registrando" en la pantalla 10b.
- [ ] RNF-001: completar la métrica.

### 3.3 Proceso
- [ ] Documentar la evidencia de la validación del diseño con el cliente.
- [ ] Asignar responsables a los issues #61 y #62.
- [ ] Integrar `segunda-entrega` a `main` mediante pull request al cerrar la entrega.

---

Ver también: [Contraste entre la primera y la segunda entrega](contraste-primera-segunda-entrega.md)
