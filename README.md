# Ven al Centro y Gana — Rediseño del registro de participantes

Rediseño de la experiencia de usuario del registro de participantes de la aplicación web [Ven al Centro y Gana](https://venalcentroygana.com/), una dinámica de **CANACO SERVYTUR Mérida** para impulsar las compras en el centro de la ciudad.

Proyecto integrador de la materia **Fundamentos de Ingeniería de Software**.

## Contenido

- [Contexto](#contexto)
- [Problema](#problema)
- [Solución propuesta](#solución-propuesta)
- [Alcance](#alcance)
- [Estado del proyecto](#estado-del-proyecto)
- [Documentación](#documentación)
- [Estructura del repositorio](#estructura-del-repositorio)
- [Flujo de trabajo](#flujo-de-trabajo)
- [Equipo](#equipo)
- [Licencia](#licencia)

## Contexto

*Ven al Centro y Gana* es una dinámica en la que los clientes registran sus compras de $200 o más en comercios participantes del centro de Mérida y responden una trivia para entrar al sorteo de premios. El registro se hace desde una aplicación web, a la que se accede por URL o código QR.

## Problema

En la prueba de campo, los concursantes tuvieron dificultades para usar la aplicación actual:

- Personas de 60 a 70 años no encontraban el botón para comenzar el registro.
- El formulario de datos personales no era intuitivo, sobre todo para personas mayores de 50 años.
- Hubo demoras al seleccionar la sucursal de compra y fallas al capturar la foto del ticket.
- En celulares pequeños, los toques accidentales obligaban a reiniciar el registro.

Estas barreras hacen que algunos clientes desistan de participar antes de terminar.

## Solución propuesta

Rediseñar el flujo de registro de participantes con una interfaz mejor estructurada, instrucciones más claras y validaciones que orienten al concursante paso a paso, sin modificar la base de datos ni el backend del sistema actual.

## Alcance

El rediseño cubre el **Módulo de registro de participantes**, en 4 etapas:

| Etapa | Pantallas |
|---|---|
| 1. Registro | Inicio, ingreso con número telefónico, aviso de número no registrado, bienvenida de usuario registrado, registro de datos personales |
| 2. Datos de la compra | Selección de sucursal con buscador, monto de la compra, foto del ticket con vista previa |
| 3. Trivia | Instrucciones y 3 preguntas de opción múltiple |
| 4. Resultado | Participación confirmada o respuestas incorrectas |

**Fuera del alcance:** el panel de administración, el backend y la base de datos.

## Estado del proyecto

**Segunda entrega:** definición de requisitos (versión 2.0) y diseño de interfaces.

| Entregable | Estado |
|---|---|
| Requisitos funcionales (RF-001 a RF-021) | Versión 2.0 |
| Requisitos no funcionales (RNF-001 a RNF-012) | Versión 2.0 |
| Historias de usuario (HU-001 a HU-021) | Versión 2.0 |
| Diagrama de casos de uso | Versión 2.0 |
| Prototipo de interfaces en Figma | Versión 2.0 |
| Validación del diseño con el cliente | Aprobada por el cliente (falta documentar la evidencia) |
| Implementación | No iniciada |

## Documentación

| Documento | Descripción |
|---|---|
| [Propuesta](docs/propuesta.md) | Problemática, propuesta de solución, usuarios y alcance |
| [Requisitos funcionales](docs/requirements/functional) | RF-001 a RF-021 |
| [Requisitos no funcionales](docs/requirements/non-functional) | RNF-001 a RNF-012 |
| [Priorización de requisitos](docs/requirements/priorizacion-requisitos.md) | Priorización MoSCoW y orden de implementación |
| [Control de cambios de requisitos](docs/requirements/cambios-segunda-entrega.md) | Requisitos nuevos, modificados y discrepancias de la segunda entrega |
| [Historias de usuario](docs/user-stories) | HU-001 a HU-021, con criterios de aceptación |
| [Diagrama de casos de uso](docs/UML) | Versión 2.0 (PlantUML) y versión 1.0 (PDF) |
| [Diseño de interfaces](docs/design) | Enlace al prototipo en Figma, pantallas y guía de diseño |
| [Proceso](docs/process) | Metodología, evidencias y métrica de contribución individual |
| [Competencias](docs/competencies) | Competencias genéricas y específicas |
| [Comentarios y feedback](docs/comentarios-y-feedback/feedback-cesar-rodriguez.md) | Observaciones del revisor y correcciones aplicadas |
| [Referencias](docs/bibliography/Referencias.md) | Bibliografía consultada |
| [Video](docs/video) | Enlace al video de la entrega |

## Estructura del repositorio

```
.
├── .github/
│   ├── ISSUE_TEMPLATE/               # Plantilla de issues para tareas
│   ├── workflows/                    # Revisión automática de marcadores de conflicto
│   └── pull_request_template.md
├── docs/
│   ├── UML/                          # Diagrama de casos de uso v2 (PlantUML, PNG, SVG) y v1 (PDF)
│   ├── bibliography/                 # Referencias
│   ├── comentarios-y-feedback/       # Feedback del revisor y correcciones aplicadas
│   ├── competencies/
│   │   ├── generic-competencies/     # Competencias genéricas
│   │   └── specific-competencies/    # Competencias específicas
│   ├── design/
│   │   ├── screens/                  # Capturas de las pantallas del prototipo
│   │   ├── design-guide.md           # Guía de diseño (colores, tipografía, componentes)
│   │   └── screens.md                # Flujo y matriz de pantallas
│   ├── process/                      # Evidencias, pendientes y métrica de contribución individual
│   ├── requirements/
│   │   ├── functional/               # RF-001 a RF-021
│   │   ├── non-functional/           # RNF-001 a RNF-012
│   │   ├── cambios-segunda-entrega.md   # Control de cambios de requisitos
│   │   └── priorizacion-requisitos.md   # Priorización MoSCoW
│   ├── user-stories/                 # HU-001 a HU-021
│   ├── video/                        # Enlace al video
│   └── propuesta.md                  # Problemática, solución y alcance
├── process/
│   ├── agreements/                   # Acuerdos del equipo (ACU-###)
│   ├── logs/                         # Bitácoras de reuniones
│   └── tasks/
│       ├── active/                   # Tareas en curso (TAR-###)
│       └── completed/                # Tareas terminadas
├── templates/                        # Plantillas de acuerdo, bitácora y tarea
└── README.md
```

## Flujo de trabajo

### Ramas

| Rama | Uso |
|---|---|
| `main` | Versión estable entregada |
| `segunda-entrega` | Trabajo de la segunda entrega |

Los cambios se integran a `main` mediante pull request. El workflow de GitHub Actions revisa que no queden marcadores de conflicto sin resolver.

### Convención de commits

Se usa [Conventional Commits](https://www.conventionalcommits.org/es/v1.0.0/):

```
<tipo>(<alcance opcional>): <descripción en minúsculas>
```

| Tipo | Uso |
|---|---|
| `feat` | Nueva funcionalidad o nuevo artefacto |
| `fix` | Corrección de un error |
| `docs` | Cambios en la documentación |
| `refactor` | Reorganización sin cambio de contenido |
| `chore` | Mantenimiento (configuración, plantillas, limpieza) |

Ejemplo: `docs(requirements): agregar priorización de requisitos con MoSCoW`

### Tareas y reuniones

- Cada tarea se registra como issue con la [plantilla de tarea](.github/ISSUE_TEMPLATE/tarea.md), con responsable y fecha límite.
- Los acuerdos y las bitácoras de reunión se documentan en `process/`, con las plantillas de `templates/`.

## Equipo

| Integrante | Rol |
|---|---|
| Hermen Steven Diaz Euan | Líder del proyecto · Orquestador de agentes de IA |
| Jacqueline Alessandra Ac Yam | Integrante |
| Adriana Esmeralda Arguelles Pool | Integrante |
| Erick Eduardo Bolaños Gonzáles | Integrante · AI Manager |
| Manuel Emiliano Canche Pacheco | Integrante |
| Andrew Abimael Gonzalez Kantun | Integrante |
| Eduardo Alberto Peniche Moreno | Integrante · Chief of Agents |

**Cliente:** CANACO SERVYTUR Mérida.

### Participación individual (segunda entrega)

Tareas asignadas desde el issue [#38](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/38) "Arreglar requisitos" (19 de octubre de 2026) a la fecha. El detalle está en la [métrica de contribución individual](docs/process/metricas.md).

| Integrante | % de participación |
| :--- | :---: |
| Hermen Steven Diaz Euan | 16.67 % |
| Erick Eduardo Bolaños Gonzáles | 16.67 % |
| Andrew Abimael Gonzalez Kantun | 16.67 % |
| Manuel Emiliano Canche Pacheco | 16.67 % |
| Eduardo Alberto Peniche Moreno | 16.67 % |
| Jacqueline Alessandra Ac Yam | 16.67 % |
| Adriana Esmeralda Arguelles Pool | 0 % |
| **Total** | **100 %** |

## Licencia

Proyecto académico sin licencia de uso definida. La marca y los materiales de la campaña *Ven al Centro y Gana* pertenecen a sus titulares.
