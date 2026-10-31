# Priorización de requisitos — Ven al Centro y Gana

**Versión:** 1.0 · Segunda entrega
**Fecha:** 31 de octubre de 2026
**Alcance:** RF-001 a RF-021 y RNF-001 a RNF-012 (versión 2.0)

---

## 1. Método

Se usa el método **MoSCoW**:

| Nivel | Significado | Regla para este proyecto |
|---|---|---|
| **Debe** (*Must*) | Sin este requisito, el concursante no puede completar su participación, o el sistema incumple una obligación legal. | Indispensable para la primera versión funcional. |
| **Debería** (*Should*) | Mejora de forma importante la usabilidad o atiende un problema observado en campo, pero existe una alternativa temporal. | Se incluye si no compromete a los requisitos "Debe". |
| **Podría** (*Could*) | Aporta comodidad o consistencia; su ausencia no bloquea ni confunde al concursante. | Se incluye si queda capacidad en el sprint. |
| **No en esta entrega** (*Won't*) | Fuera del alcance acordado. | Se documenta para entregas futuras. |

### Criterios de evaluación
Cada requisito se evaluó según cinco criterios:
1. **Objetivo del producto:** ¿es indispensable para que el concursante registre su participación de principio a fin?
2. **Evidencia de campo:** ¿atiende un problema observado en la prueba de campo?
3. **Obligación legal o de privacidad:** ¿protege datos personales o da acceso a las reglas de la dinámica?
4. **Dependencias:** ¿otros requisitos dependen de él?
5. **Esfuerzo:** puntos sugeridos en su historia de usuario.

La prioridad de los RF coincide con la de sus historias de usuario: **Alta = Debe** y **Media = Debería o Podría**.

---

## 2. Lista priorizada de requisitos funcionales

El orden dentro de cada nivel sigue el flujo del concursante y sus dependencias: lo primero de la lista es lo primero que se debe construir.

### 🔴 Debe (Must)

| # | ID | Requisito | HU | Pts | Justificación de la prioridad |
|---|---|---|---|---|---|
| 1 | [RF-001](functional/RF-001.md) | Pantalla de inicio | HU-001 | 2 | Punto de entrada. En campo, las personas de 60 a 70 años no encontraban "Comenzar". |
| 2 | [RF-004-A](functional/RF-004-A.md) | Ingreso con número telefónico | HU-004-A | 5 | Identifica al concursante; de él dependen RF-005 a RF-011. |
| 3 | [RF-005](functional/RF-005.md) | Ventana emergente de número no registrado | HU-005 | 3 | Decide entre el registro y la compra. Reduce el inicio de 1.5 min a menos de 10 s para recurrentes. |
| 4 | [RF-006](functional/RF-006.md) | Registro de datos personales | HU-006 | 5 | Sin estos datos no se puede contactar al ganador. |
| 5 | [RF-008](functional/RF-008.md) | Aviso de privacidad | HU-008 | 2 | **Obligación legal:** no se pueden tratar datos personales sin aceptar el aviso. |
| 6 | [RF-021](functional/RF-021.md) | Validación al avanzar y resumen de errores | HU-021 | 3 | Valida todos los formularios; sin él se registran datos incompletos. |
| 7 | [RF-009](functional/RF-009.md) | Selección de sucursal | HU-009 | 2 | Liga la compra a un comercio participante; requisito para la trivia. |
| 8 | [RF-017](functional/RF-017.md) | Búsqueda de sucursal | HU-017 | 3 | Es el mecanismo con el que se cumple RF-009; en campo hubo demoras al elegir la sucursal. |
| 9 | [RF-010](functional/RF-010.md) | Monto de la compra | HU-010 | 2 | Valida la regla de compra mínima de $200. |
| 10 | [RF-011](functional/RF-011.md) | Foto del ticket | HU-011 | 5 | Evidencia de la compra; evita tickets reutilizados o editados. |
| 11 | [RF-013](functional/RF-013.md) | Trivia | HU-013 | 5 | Núcleo de la dinámica: sin ella no hay participación válida. |
| 12 | [RF-014](functional/RF-014.md) | Participación confirmada | HU-014 | 5 | Genera y envía el folio; es la prueba de participación del concursante. |

**Subtotal:** 12 requisitos · 42 puntos.

### 🟠 Debería (Should)

| # | ID | Requisito | HU | Pts | Justificación de la prioridad |
|---|---|---|---|---|---|
| 13 | [RF-003](functional/RF-003.md) | Bases oficiales | HU-003 | 1 | Transparencia legal de la dinámica. Esfuerzo mínimo, por lo que conviene implementarlo junto con RF-001. |
| 14 | [RF-015](functional/RF-015.md) | Resultado con respuestas incorrectas | HU-015 | 2 | Sin él, quien falla no sabe cómo volver a participar; se puede sustituir temporalmente con un mensaje simple. |
| 15 | [RF-012](functional/RF-012.md) | Instrucciones de la trivia | HU-012 | 2 | Reduce errores en la trivia; existe la alternativa de un texto breve sobre la pregunta 1. |
| 16 | [RF-007](functional/RF-007.md) | Ejemplos en los campos de registro | HU-007 | 1 | Atiende la dificultad observada en mayores de 50 años; esfuerzo mínimo. |
| 17 | [RF-018](functional/RF-018.md) | Vista previa y repetición de la foto | HU-018 | 3 | En campo hubo fallas al capturar el ticket; evita fotos ilegibles. |
| 18 | [RF-004-B](functional/RF-004-B.md) | Registro directo como usuario nuevo | HU-004-B | 1 | Atajo para usuarios nuevos; RF-004-A + RF-005 ya llevan al registro. |
| 19 | [RF-020](functional/RF-020.md) | Registrar otra compra desde el resultado | HU-020 | 2 | Facilita volver a participar; la alternativa es regresar al inicio. |
| 20 | [RF-002](functional/RF-002.md) | Lista de comercios participantes | HU-002 | 1 | Informativo; ayuda cuando el concursante no encuentra su sucursal. |

**Subtotal:** 8 requisitos · 13 puntos.

### 🟡 Podría (Could)

| # | ID | Requisito | HU | Pts | Justificación de la prioridad |
|---|---|---|---|---|---|
| 21 | [RF-016](functional/RF-016.md) | Salida del registro con confirmación | HU-016 | 2 | Previene pérdidas por toques accidentales, pero el flujo funciona sin él. |
| 22 | [RF-019](functional/RF-019.md) | Navegación entre preguntas de la trivia | HU-019 | 3 | Comodidad: permite corregir una respuesta antes de terminar. |

**Subtotal:** 2 requisitos · 5 puntos.

### ⚪ No en esta entrega (Won't)

| Elemento | Motivo |
|---|---|
| Mostrar el folio en la pantalla de confirmación | Requiere modificar el backend (decisión del equipo; ver RF-014). El folio se envía por SMS y correo. |
| "Brindar el correo de un conocido" y "Revisar cuál es su correo" | Aparecían en el diagrama de casos de uso v1, pero no tienen un requisito que los respalde. |

---

## 3. Lista priorizada de requisitos no funcionales

| # | ID | Requisito | Prioridad | Justificación de la prioridad |
|---|---|---|---|---|
| 1 | [RNF-001](non-functional/RNF-001.md) | Portabilidad (diseño responsivo de 360 a 1024 px) | 🔴 Debe | La mayoría participa desde el celular; sin esto, la interfaz se distorsiona en pantallas pequeñas. |
| 2 | [RNF-011](non-functional/RNF-011.md) | Enmascaramiento de datos personales | 🔴 Debe | Protección de datos personales en lugares públicos (obligación de privacidad). |
| 3 | [RNF-005](non-functional/RNF-005.md) | Interfaz estandarizada y de alto contraste | 🔴 Debe | Accesibilidad mínima (contraste de 4.5:1). **Hoy el diseño no lo cumple** en botones naranjas y amarillos (ver control de cambios). |
| 4 | [RNF-004](non-functional/RNF-004.md) | Carga de sucursales en menos de 2 s | 🔴 Debe | Condición para que RF-009 y RF-017 sean usables. |
| 5 | [RNF-008](non-functional/RNF-008.md) | Tamaños mínimos de controles y texto | 🟠 Debería | Atiende los toques accidentales y los problemas de lectura observados en campo. |
| 6 | [RNF-010](non-functional/RNF-010.md) | Formato de los mensajes de error | 🟠 Debería | Complementa a RF-021; los errores no dependen solo del color. |
| 7 | [RNF-003](non-functional/RNF-003.md) | Botones de navegación con menor énfasis | 🟠 Debería | Evita regresos involuntarios (meta: 0 toques accidentales). |
| 8 | [RNF-002](non-functional/RNF-002.md) | Ejemplos dentro de los campos | 🟠 Debería | Criterio de calidad de RF-007. |
| 9 | [RNF-006](non-functional/RNF-006.md) | Redacción y presentación de la trivia | 🟠 Debería | Reduce los fallos en la trivia por preguntas confusas. |
| 10 | [RNF-009](non-functional/RNF-009.md) | Teclado y formato según el tipo de dato | 🟡 Podría | Reduce errores de captura; los formularios funcionan sin él. |
| 11 | [RNF-007](non-functional/RNF-007.md) | Indicador de progreso por etapas | 🟡 Podría | Orientación adicional; ya existe un indicador básico "Paso X de 4". |
| 12 | [RNF-012](non-functional/RNF-012.md) | Redacción clara y consistente | 🟡 Podría | Calidad de los textos; se puede corregir de forma continua. |

---

## 4. Orden de implementación sugerido

| Iteración | Requisitos | Resultado |
|---|---|---|
| **1. Flujo mínimo completo** | RF-001, RF-004-A, RF-005, RF-006, RF-008, RF-021, RF-009, RF-017, RF-010, RF-011, RF-013, RF-014 + RNF-001, RNF-004, RNF-005, RNF-011 | Un concursante puede registrarse, subir su ticket, contestar la trivia y recibir su folio. |
| **2. Usabilidad y apoyo** | RF-003, RF-015, RF-012, RF-007, RF-018, RF-004-B, RF-020, RF-002 + RNF-008, RNF-010, RNF-003, RNF-002, RNF-006 | Se atienden los problemas observados en campo y los casos de error. |
| **3. Refinamiento** | RF-016, RF-019 + RNF-009, RNF-007, RNF-012 | Comodidad y consistencia. |

---

## 5. Resumen

| Nivel | RF | RNF | Puntos (RF) |
|---|---|---|---|
| 🔴 Debe | 12 | 4 | 42 |
| 🟠 Debería | 8 | 5 | 13 |
| 🟡 Podría | 2 | 3 | 5 |
| **Total** | **22** | **12** | **60** |

> **Pendiente:** validar esta priorización con el cliente (CANACO SERVYTUR), sobre todo la ubicación de RF-003 (bases oficiales). Si el cliente considera obligatorio el acceso a las bases desde el lanzamiento, sube a "Debe".
