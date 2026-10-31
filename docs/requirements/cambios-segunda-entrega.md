# Control de cambios de requisitos — Segunda entrega

**Origen de los cambios:** rediseño del flujo de registro en Figma — [Ven al Centro y Gana – Flujo de registro v2](https://www.figma.com/design/E6mFB3CTZQOtWvbkYIXpUk)
**Fecha de revisión:** 31 de octubre de 2026
**Alcance:** solo cambios visuales y de interacción en el frontend. Ningún cambio requiere modificar la base de datos ni el backend, salvo donde se indica expresamente.

Este documento registra, para fines de trazabilidad:
1. Los **requisitos nuevos** que surgieron del rediseño.
2. Los **requisitos existentes que se modifican** y su nueva redacción.
3. Las **discrepancias** entre el diseño y los requisitos que el equipo debe resolver.

---

## 1. Requisitos nuevos

### Funcionales

| ID | Nombre | Pantalla(s) en Figma |
|---|---|---|
| [RF-016](functional/RF-016.md) | Salida del registro con confirmación | Diálogo · Salir del registro |
| [RF-017](functional/RF-017.md) | Búsqueda de sucursal | 05b · Elegir sucursal |
| [RF-018](functional/RF-018.md) | Vista previa y repetición de la foto del ticket | 05d · Compra completa (foto tomada) |
| [RF-019](functional/RF-019.md) | Navegación entre preguntas de la trivia | 07 · Pregunta 1, 09 · Pregunta 3 |
| [RF-020](functional/RF-020.md) | Registrar otra compra desde el resultado | 10 · Resultado correctas, 10b · Resultado incorrectas |
| [RF-021](functional/RF-021.md) | Validación al avanzar y resumen de errores | 02b, 04b, 05c |

### No funcionales

| ID | Nombre | Tipo |
|---|---|---|
| [RNF-007](non-functional/RNF-007.md) | Indicador de progreso por etapas | Usabilidad |
| [RNF-008](non-functional/RNF-008.md) | Tamaños mínimos de controles y texto | Usabilidad |
| [RNF-009](non-functional/RNF-009.md) | Teclado y formato según el tipo de dato | Usabilidad |
| [RNF-010](non-functional/RNF-010.md) | Formato de los mensajes de error | Usabilidad |
| [RNF-011](non-functional/RNF-011.md) | Enmascaramiento de datos personales en pantalla | Seguridad |
| [RNF-012](non-functional/RNF-012.md) | Redacción clara y consistente en todo el flujo | Usabilidad |

---

## 2. Requisitos modificados

Cada entrada indica qué cambia y la redacción nueva de las secciones afectadas. Las secciones que no se mencionan quedan igual.

### RF-001 | Pantalla de inicio
**Cambio:** el indicador de desplazamiento pasa a ser un texto con flecha; los pasos se numeran; se agrega un recuadro con la compra mínima, y los enlaces cambian de nombre.
- **Descripción:** El sistema permite al concursante visualizar la información general de la campaña, los 3 pasos numerados para participar (registrar datos, tomar foto del ticket, responder 3 preguntas), un recuadro que destaca la compra mínima de $200, el indicador "Toca aquí para empezar" con una flecha hacia abajo y el botón "Comenzar".
- **Flujo principal, paso 2:** El sistema muestra la información de la campaña, los pasos numerados, el recuadro de compra mínima, el indicador "Toca aquí para empezar" con flecha y el botón "Comenzar".
- **Flujo alterno A1:** El usuario selecciona "Ver bases" o "Ver comercios"; el sistema abre el documento correspondiente en una pestaña externa.

### RF-002 | Lista de sucursales
**Cambio:** nombre del enlace y un nuevo punto de acceso.
- **Descripción:** El enlace se llama "Ver comercios" en la pantalla de inicio. También se accede desde el panel de búsqueda de sucursal con el enlace "lista de comercios participantes" (RF-017, A2).

### RF-003 | Bases oficiales
**Cambio:** nombre del enlace.
- **Descripción:** El enlace se llama "Ver bases".

### RF-004-A | Ingreso con número telefónico
**Cambio:** prefijo, contador de dígitos, mensajes que indican cómo corregir y validación al presionar "Siguiente". La casilla del aviso de privacidad ya no aparece en esta pantalla (ver RF-008).
- **Flujo principal, paso 1:** El sistema presenta el título "Ingresa tu número de celular", el campo "Número de celular" con el prefijo "+52", el ejemplo "Ej.: 999 413 6967" y un contador de dígitos (por ejemplo, "10/10").
- **Flujo alterno A2:** El sistema muestra: "El número es muy corto. Te faltan N dígitos.", donde N es el número de dígitos faltantes.
- **Flujo alterno A3:** El campo no permite capturar más de 10 dígitos. Si el número llega pegado con más dígitos, el sistema muestra "El número es muy largo".
- **Nueva regla:** El botón "Siguiente" permanece activo y la validación ocurre al presionarlo (RF-021).

### RF-004-B | Registro como usuario nuevo
**Cambio:** el enlace pasa a ser un botón; se corrige el alcance pendiente y se agrega el camino inverso.
- **Alcance (reemplaza el texto pendiente):** Botón "Registrarme por primera vez", debajo del separador "¿Es tu primera vez?", que lleva al formulario de registro de datos personales (RF-006) sin consultar el número.
- **Flujo principal, paso 2:** El concursante presiona el botón "Registrarme por primera vez".
- **Nuevo flujo alterno A2:** Desde el formulario de registro, el concursante presiona "¿Ya participaste antes? Ingresa con tu número" y el sistema lo regresa a la pantalla de ingreso con teléfono (RF-004-A).

### RF-005 | Ventana emergente de número no registrado
**Cambio:** nuevo texto, el botón "Ok" se reemplaza por dos acciones, y el usuario registrado ve una pantalla de bienvenida.
- **Flujo principal:**
  1. El sistema muestra la ventana emergente "Este número aún no está registrado" con el mensaje "No encontramos participaciones con el [número]. Vamos a registrar tus datos; solo toma un minuto."
  2. El concursante presiona "Registrar mis datos".
  3. El sistema muestra el formulario de registro (RF-006) con el número ya capturado.
- **Flujo alterno A1 (usuario ya registrado):** El sistema muestra la pantalla "¡Hola de nuevo, [nombre]!" con el número enmascarado (RNF-011) y el texto "Ya tenemos tus datos. Solo registra tu nueva compra." El concursante presiona "Continuar" y el sistema lo lleva a los datos de la compra (RF-009).
- **Nuevo flujo alterno A3:** El concursante presiona "Corregir mi número" y el sistema lo regresa a la pantalla de ingreso con teléfono, con el número capturado para editarlo.

### RF-006 | Registro de datos personales
**Cambio:** el celular viene prellenado, el mensaje de error del correo es más específico, se indica que todos los campos son obligatorios y se aplica la validación de RF-021.
- **Precondición:** El número de celular viene prellenado desde RF-004-A, con el texto de ayuda "Lo tomamos del paso anterior. Aquí te enviaremos tu folio."
- **Encabezado:** "Ingresa tus datos", con el subtítulo "Todos los campos son obligatorios."
- **Flujo alterno A4:** Si el correo no tiene el formato nombre@correo.com, el sistema muestra: "Falta la terminación del correo, por ejemplo: nombre@correo.com". Si el campo está vacío, muestra "Campo obligatorio".
- **Flujos alternos A1 a A6:** Se agrega el resumen de errores de RF-021.

### RF-007 | Ejemplos en los campos
**Cambio:** los ejemplos pasan a estar dentro del campo, como texto de ejemplo (*placeholder*), con el formato "Ej.: …".
- **Ejemplos:** Nombre(s) "Ej.: Pánfilo" · Primer apellido "Ej.: Palomo" · Segundo apellido "Ej.: Sánchez" · Número de celular "Ej.: 999 413 6967" · Correo electrónico "Ej.: nombre@correo.com" · Domicilio "Ej.: Calle 13 #256, Centro, Mérida".

### RF-008 | Aviso de privacidad
**Cambio:** la casilla aparece solo en el formulario de registro (antes también estaba en la pantalla del teléfono), se agrega un ícono de pestaña externa y el mensaje usa el trato de tú.
- **Alcance:** La casilla "He leído y acepto el aviso de privacidad" aparece solo en el formulario de registro de datos personales. El enlace muestra un ícono que indica que se abre en otra pestaña.
- **Flujo alterno A2:** El sistema muestra "Debes aceptar el aviso de privacidad".

### RF-009 | Selección de sucursal
**Cambio:** la selección se hace en un panel con buscador (RF-017).
- **Flujo principal:**
  1. El concursante toca el campo "Sucursal donde compraste" (con el texto de ejemplo "Elige una sucursal").
  2. El sistema despliega el panel de búsqueda (RF-017).
  3. El concursante elige su sucursal y el campo muestra su nombre y calle (por ejemplo, "Soriana Centro · Calle 60").

### RF-010 | Monto de la compra
**Cambio:** nueva etiqueta, prefijo y sufijo, y texto de ayuda visible desde antes del error.
- **Descripción:** El campo se llama "Total de tu ticket", con el prefijo "$", el sufijo "MXN" y el ejemplo "Ej.: 350.00". Debajo del campo aparece siempre el texto "La compra mínima es de $200."
- Los mensajes de error (A1 y A2) no cambian.

### RF-011 | Foto del ticket
**Cambio:** se agrega una instrucción, se ajusta el mensaje de error y se añade la vista previa (RF-018).
- **Flujo principal, paso 0:** Arriba del botón, el sistema muestra la instrucción "Usa buena luz y que se vean el total, la fecha y el nombre del comercio."
- **Flujo alterno A1:** El sistema muestra "Campo obligatorio: falta la foto".
- **Postcondición:** Se muestra la vista previa de la foto (RF-018).

### RF-012 | Instrucciones de la trivia
**Cambio:** las instrucciones se presentan como 3 reglas numeradas y se agrega un texto sobre el tiempo y los reintentos.
- **Contenido:** Título "Contesta la trivia". Reglas: 1. "Son 3 preguntas fáciles." 2. "Elige una respuesta en cada pregunta." 3. "Acierta las 3 y participa por un premio." Nota: "No hay límite de tiempo. Si fallas, puedes volver a intentarlo con otro ticket." Botón "Entendido".
- **Ubicación del botón "Regresar":** en la parte superior, debajo del encabezado (RNF-003).

### RF-013 | Trivia
**Cambio:** nombres de los botones y navegación entre preguntas (RF-019). También se corrige la trazabilidad.
- **Flujo principal:** Para avanzar se usa el botón "Siguiente pregunta"; en la tercera pregunta, el botón "Terminar trivia".
- **Corrección de trazabilidad:** Las postcondiciones y el flujo principal mencionan RF-008 y RF-009 como pantallas de resultado. Deben decir **RF-014** (éxito) y **RF-015** (intento fallido).

### RF-014 | Participación confirmada
**Cambio:** el folio **no** se muestra en pantalla, porque mostrarlo requeriría cambios en el backend; solo se informa su envío. Se agrega el botón "Registrar otra compra".
- **Flujo principal, paso 4:** El sistema muestra la pantalla "¡Participación confirmada!" con el texto "Respondiste bien las 3 preguntas. Ya estás participando en el sorteo." y la tarjeta "Revisa tu celular y tu correo: Te enviamos un mensaje de texto (SMS) al [número enmascarado] y un correo electrónico con los datos de tu participación."
- **Flujo principal, paso 5:** El concursante presiona "Finalizar" y el sistema concluye la sesión. Como alternativa, presiona "Registrar otra compra" (RF-020).

### RF-015 | Resultado con respuestas incorrectas
**Cambio:** nuevo texto, y el botón "Volver a participar" se reemplaza por "Finalizar" y "Registrar otra compra".
- **Alcance (reemplaza el texto actual, que menciona "No se completó el registro" y "Reintentar"):** Pantalla "¡Gracias por participar!" con el ícono de error, un mensaje y una tarjeta con instrucciones para volver a participar, más los botones "Finalizar" y "Registrar otra compra".
- **Flujo principal, paso 2:** El sistema muestra el mensaje "Esta vez no acertaste las 3 preguntas, intenta de nuevo registrando otro ticket." y la tarjeta "Puedes participar otra vez: Usa el mismo número telefónico, [número enmascarado], y registra un nuevo ticket de compra."
- **Flujo principal, paso 3:** El concursante presiona "Registrar otra compra" (RF-020).
- **Métrica:** Lograr que el 100 % de los concursantes que fallan la trivia identifiquen cómo volver a participar y presionen "Registrar otra compra" sin ayuda.

### RNF-002 | Ejemplos dentro de los campos
**Cambio:** se actualizan los valores de ejemplo para que coincidan con RF-007 (ver arriba). El criterio de colocarlos dentro de los campos no cambia.

### RNF-006 | Redacción y presentación de la trivia
**Cambio:** número de paso y estilo de selección.
- **Alcance:** La trivia corresponde al **Paso 3 de 4** (el paso 4 es el resultado). Hoy el texto dice "Paso 4 de 4", lo que contradice RF-012.
- **Estructura y presentación visual:** Cada opción es una tarjeta blanca con borde amarillo suave (#FDE49A) de 2 px. Al seleccionarla, el borde cambia a naranja (#FF6A00) de 3 px y el indicador circular se rellena de naranja.

---

## 3. Discrepancias que el equipo debe resolver

| # | Requisito | Discrepancia | Riesgo | Opciones |
|---|---|---|---|---|
| 1 | RNF-005 | La paleta del requisito (#F25A24 / #FF6B00 naranja, #FFC107 / #F8A81D amarillo, #1E2B58 azul marino en títulos) no coincide con el diseño (#FF6A00, #FB9410, #FFBB0B, títulos en #111827, sin azul marino). | El requisito no se cumple tal como está escrito. | Actualizar el RNF a la paleta del diseño, o ajustar el diseño. |
| 2 | RNF-005 | El criterio exige contraste de 4.5:1, pero el texto blanco sobre naranja #FF6A00 da 2.87:1, y sobre amarillo #FFBB0B, 1.70:1 (botones "Comenzar", "Entendido", header y botones principales). | **Incumplimiento de un criterio de aceptación de accesibilidad.** | Cambiar el color del texto o del fondo de esos botones (ver la guía de diseño, sección 2.3). Bajar el criterio no se recomienda. |
| 3 | RF-012 | El texto "No hay límite de tiempo" es una regla de la dinámica que no aparece en ningún requisito ni en las bases. | Se le promete algo al usuario sin respaldo. | Confirmarlo con CANACO SERVYTUR y con las bases oficiales, o quitar la frase. |
| 4 | RF-012 y RF-015 | "Puedes volver a intentarlo con otro ticket" implica que cada intento requiere un ticket nuevo. Las bases deben confirmarlo. | Se le promete algo al usuario sin respaldo. | Confirmarlo con las bases oficiales. |
| 5 | RF-015 (Figma) | Errata en la pantalla 10b: dice "intenta de nuevo **registrado** otro ticket" y debe decir "**registrando**". | Error de redacción visible. | Corregir el texto en Figma. |
| 6 | RNF-001 | La métrica está vacía. | Requisito incompleto. | Completar la métrica. |
| 7 | Historias de usuario | HU-015 usa el botón "Volver a participar", que ya no existe. Ninguna historia cubre RF-016 a RF-021. | Inconsistencia con RF-015 modificado. | Actualizar HU-015 y crear historias para RF-016 a RF-021. |
