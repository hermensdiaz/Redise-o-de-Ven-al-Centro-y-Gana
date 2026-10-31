# Guía de diseño — Ven al Centro y Gana

**Versión:** 1.0 · Segunda entrega
**Fuente:** [Archivo de Figma — Flujo de registro](https://www.figma.com/design/sVxsBw6xtnTPWCtjMJrPL7/Ven-al-Centro-y-Gana-%E2%80%93-Flujo-de-registro?node-id=0-1&t=DLfkUYIZnpshV6pP-0) (página `Pantallas`, sección `Componentes`)
**Alcance:** flujo de registro de participantes en móvil (inicio, registro, datos de la compra, trivia y resultado)

Esta guía documenta las decisiones visuales y de interacción del rediseño, para que cualquier pantalla nueva sea consistente con las existentes y para que el equipo de desarrollo implemente el diseño sin ambigüedades.

---

## 1. Principios de diseño

Los principios salen directamente de los hallazgos de la prueba de campo y de los requisitos no funcionales.

| Principio | Qué significa | Cómo se aplica | Requisito |
|---|---|---|---|
| **Una acción clara por pantalla** | El usuario siempre sabe qué hacer después | Un solo botón principal a ancho completo, al final del contenido | RF-001, RNF-005 |
| **Saber dónde estoy** | El usuario conoce su avance en el proceso | Indicador "Paso X de 4" con barra de progreso en cada etapa | RNF-002 |
| **Prevenir antes que corregir** | Evitar errores en lugar de castigarlos | Ejemplos en cada campo, botón deshabilitado hasta completar, validación en línea | RF-007, RF-010 |
| **Lectura fácil** | Cualquier persona, incluidos adultos mayores, entiende el texto | Frases cortas, sujeto + verbo + predicado, sin tecnicismos | RNF-006 |
| **Móvil primero** | La mayoría participa desde el celular, en la calle | Diseño en 360 px de ancho, una sola columna, áreas táctiles grandes | RNF-001, RNF-003 |

---

## 2. Color

### 2.1 Tokens

Los colores están definidos como **variables en Figma**. En el código se deben usar con el mismo nombre; no hay que copiar el valor hexadecimal suelto.

**Marca** (logotipo e ilustraciones)

| Token | Valor | Uso |
|---|---|---|
| `marca/naranja` | `#FF8A00` | Logotipo |
| `marca/amarillo` | `#FFB400` | Logotipo |
| `marca/amarillo-claro` | `#FFD54A` | Detalles del logotipo |
| `marca/rojo` | `#F2541B` | Acentos del logotipo |

**Interfaz**

| Token | Valor | Uso |
|---|---|---|
| `primario/naranja` | `#FF6A00` | Header, botones primarios, casillas marcadas, radio seleccionado |
| `primario/progreso` | `#FB9410` | Relleno de la barra de progreso |
| `acento/amarillo` | `#FFBB0B` | Botón destacado ("Comenzar", "Entendido") |
| `acento/amarillo-deshabilitado` | `#FDE49A` | Botón destacado deshabilitado |
| `neutro/track` | `#E2E6EA` | Fondo de la barra de progreso |
| `neutro/deshabilitado` | `#CDD3D9` | Botón primario deshabilitado |

**Texto**

| Token | Valor | Uso |
|---|---|---|
| `texto/principal` | `#111827` | Títulos y cuerpo de texto |
| `texto/secundario` | `#4B5563` | Texto de apoyo |
| `texto/placeholder` | `#6B7280` | Texto de ejemplo dentro de los campos |
| `texto/enlace` | `#E99A1C` | Enlaces (bases, comercios, aviso de privacidad) |
| `texto/inverso` | `#FFFFFF` | Texto sobre fondos de color |

**Superficies**

| Token | Valor | Uso |
|---|---|---|
| `superficie/blanco` | `#FFFFFF` | Fondo de pantalla |
| `superficie/input` | `#F1F4F9` | Fondo de los campos de formulario |
| `borde/input` | `#E3E8EF` | Borde de los campos |
| `superficie/icono` | `#F2F4F8` | Contenedor de los íconos de los pasos |

**Estados** (usados en las pantallas, aún sin variable en Figma)

| Uso | Valor sugerido |
|---|---|
| Error (mensajes de validación) | Rojo, por ejemplo `#DC2626` (contraste 4.83:1) |
| Overlay de diálogo | Negro al ~40 % de opacidad |

### 2.2 Reglas de uso
- **Naranja = acción y marca.** Se usa en el header, en los botones primarios y en los controles seleccionados.
- **Amarillo = llamada principal.** Se reserva para el botón más importante de la pantalla ("Comenzar", "Entendido"). Usarlo una sola vez por pantalla.
- **El rojo solo comunica errores.** No se usa como decoración en la interfaz.
- El fondo de pantalla es siempre blanco, para mantener al menos un 40 % de área libre (RNF-005).

### 2.3 Contraste y accesibilidad ⚠️

RNF-005 exige un contraste mínimo de **4.5:1** (WCAG 2.1 AA) para todo el texto. Al medir las combinaciones actuales del diseño, el resultado fue este:

| Combinación | Contraste | AA texto normal (4.5:1) | AA texto grande (3:1) |
|---|---|---|---|
| `texto/principal` sobre blanco | 17.74:1 | ✅ | ✅ |
| `texto/secundario` sobre blanco | 7.56:1 | ✅ | ✅ |
| `texto/placeholder` sobre `superficie/input` | 4.39:1 | ❌ (por poco) | ✅ |
| Blanco sobre `primario/naranja` (header, botones) | 2.87:1 | ❌ | ❌ |
| Blanco sobre `acento/amarillo` ("Comenzar") | 1.70:1 | ❌ | ❌ |
| `texto/enlace` sobre blanco | 2.31:1 | ❌ | ❌ |
| Ejemplos de campo ("Ej.: Juan Carlos") sobre blanco | muy bajo | ❌ | ❌ |
| `texto/principal` sobre `acento/amarillo` | 10.45:1 | ✅ | ✅ |

**Ajustes recomendados** para cumplir RNF-005 sin perder la identidad de la marca:

| Elemento | Cambio | Contraste resultante |
|---|---|---|
| Botón destacado amarillo | Texto `#111827` en lugar de blanco | 10.45:1 ✅ |
| Header y botones naranjas | Fondo `#C2410C` (naranja oscuro) con texto blanco | 5.18:1 ✅ |
| Header y botones naranjas (alternativa) | Mantener `#FF6A00` con texto `#111827` | 6.18:1 ✅ |
| Enlaces | `#B45309` (ámbar oscuro), subrayado | 5.02:1 ✅ |
| Placeholder | `#4B5563` | 6.86:1 ✅ |
| Ejemplos de campo | Usar `texto/secundario` en lugar del gris claro | 7.56:1 ✅ |

Además, en los requisitos la paleta oficial aparece como `#F25A24 / #FFC107 / #1E2B58` (RNF-005), mientras que el prototipo usa `#FF6A00 / #FFBB0B / #111827`. Hay que **alinear ambos documentos**: actualizar el RNF o los tokens, según lo que confirme el cliente.

---

## 3. Tipografía

Se usan dos familias de Google Fonts:
- **Poppins:** títulos, botones y preguntas. Es geométrica y amigable, y combina con el estilo del logotipo.
- **Noto Sans:** texto de lectura, etiquetas y campos. Es muy legible en tamaños pequeños.

| Estilo | Familia | Peso | Tamaño | Interlineado | Uso |
|---|---|---|---|---|---|
| `Header/Título` | Poppins | SemiBold 600 | 20 px | 130 % | Título del header |
| `Botón/Grande` | Poppins | SemiBold 600 | 20 px | 130 % | Botones principales |
| `Botón/Pequeño` | Poppins | SemiBold 600 | 14 px | 130 % | "Regresar" |
| `Trivia/Opción` | Poppins | Regular 400 | 17 px | 140 % | Opciones de respuesta |
| `Body/Poppins` | Poppins | Regular 400 | 12 px | 150 % | Texto de los pasos de participación |
| `Paso/Etiqueta` | Noto Sans | Regular 400 | 14 px | 150 % | "Paso 1 de 4", etiquetas de campo |
| `Body/Noto` | Noto Sans | Regular 400 | 13 px | 150 % | Párrafos |
| `Campo/Valor` | Noto Sans | Regular 400 | 12 px | 150 % | Texto dentro de los campos |

**Títulos de pantalla:** Poppins SemiBold de 18 a 28 px, según la pantalla (por ejemplo, "Contesta la Trivia" o las preguntas de la trivia).

**Recomendaciones:**
- Subir `Campo/Valor` y `Body/Poppins` a **16 px como mínimo**. En iOS, un campo con texto menor a 16 px provoca un zoom automático al enfocarlo, y el texto pequeño dificulta la lectura a los adultos mayores, que son un grupo clave según la prueba de campo.
- Crear estilos de texto en Figma para los títulos de pantalla, que hoy no tienen uno.

---

## 4. Espaciado y retícula

| Elemento | Medida |
|---|---|
| Ancho de la pantalla base | 360 px |
| Margen lateral | 16 px |
| Ancho del contenido | 328 px (una sola columna) |
| Altura del header | 44 px |
| Separación entre bloques (indicador, encabezado, formulario) | 24 px |
| Separación entre campos de formulario | 20–24 px |
| Separación entre opciones de trivia | 28 px |

**Escala de espaciado recomendada:** múltiplos de 4 (4, 8, 12, 16, 20, 24, 32). En el diseño casi todas las medidas ya cumplen esta escala.

---

## 5. Componentes

Todos los componentes viven en la sección **`Componentes`** del archivo de Figma. Las pantallas deben construirse **solo con instancias de estos componentes**, sin desacoplarlos (*detach*).

### 5.1 Header
- Barra naranja de 44 px con el ícono `home` a la izquierda y el título de la etapa centrado ("Registro", "Datos de la Compra", "Trivia").
- El ícono de inicio permite abandonar el flujo en cualquier momento.

### 5.2 Indicador de paso
- Texto "Paso X de 4" y barra de progreso (track `neutro/track`, relleno `primario/progreso`).
- Variantes: `Paso=1`, `Paso=2`, `Paso=3` y `Paso=4`.
- Etapas: 1 Registro · 2 Datos de la compra · 3 Trivia · 4 Resultado.

### 5.3 Botones

| Variante | Fondo | Cuándo usarla |
|---|---|---|
| `Primario` | `primario/naranja` | Avanzar dentro del flujo ("Siguiente") |
| `Destacado` | `acento/amarillo` | La acción más importante de la pantalla ("Comenzar", "Entendido") |
| `Deshabilitado` | `neutro/deshabilitado` | Primario cuando faltan datos obligatorios |
| `Destacado deshabilitado` | `acento/amarillo-deshabilitado` | Destacado cuando faltan datos |
| `Botón pequeño` | `primario/naranja` | Acciones secundarias ("Regresar") |
| `Botón con ícono` | `primario/progreso` | Acciones con un objeto concreto ("Tomar foto del ticket") |

**Reglas:**
- Altura mínima de **44 px** para todos los botones principales (RNF-003); hoy el primario mide 40 px y hay que subirlo.
- Los botones principales ocupan el ancho completo del contenido (328 px).
- Siempre llevan un verbo y, si avanzan, la flecha `arrow-right`.
- Mientras el formulario esté incompleto, el botón se muestra **deshabilitado**, no oculto.

### 5.4 Campo de formulario
- Etiqueta arriba (Noto Sans 14 px) y campo de 44 px con fondo `superficie/input` y borde `borde/input`.
- El **ejemplo** va junto a la etiqueta ("Ej.: Juan Carlos") y el **placeholder** dentro del campo indica la acción ("Ingrese su…").
- Variantes: `Texto / Placeholder`, `Texto / Valor` y `Selector / Placeholder` (con `chevron-down`).
- **Estado de error:** mensaje en rojo debajo del campo, con espacio propio para no tapar el siguiente campo. Ejemplos: "Campo obligatorio" y "El monto mínimo para participar es de $200".
- **Tipo de teclado:** numérico para teléfono y monto, de correo para el correo electrónico.

**Recomendación:** convertir el estado de error en una variante del componente (`Estado=Error`, con borde rojo). Hoy es un texto suelto en las pantallas.

### 5.5 Aceptar aviso de privacidad
- Casilla de 20 px con el texto "He leído y aceptado los **avisos de privacidad**".
- El enlace abre el documento en una pestaña nueva (RF-008).
- Variantes: `Marcado=No` y `Marcado=Sí` (relleno naranja con check blanco).
- **Recomendación:** ampliar el área táctil a 44 × 44 px aunque la casilla visible mida 20 px.

### 5.6 Opción de trivia
- Radio con texto en `Trivia/Opción` (17 px), altura de 48 px y toda la fila es pulsable.
- Variantes: `Seleccionado=No` y `Seleccionado=Sí` (círculo naranja relleno).
- Si el texto ocupa dos líneas, la opción crece hasta 72 px.

### 5.7 Paso de participación
- Ícono en un contenedor `superficie/icono` y texto descriptivo a la derecha.
- Se usa en la pantalla de inicio para explicar los 3 pasos con íconos: `receipt` (registrar datos), `camera` (foto del ticket) y `quiz` (trivia).

### 5.8 Diálogo
- Tarjeta blanca de 288 px de ancho, centrada, sobre un overlay oscuro.
- Lleva título, mensaje y una sola acción de texto ("Ok").
- **Recomendación:** crearlo como componente, porque hoy está dibujado directamente en la pantalla 03.

### 5.9 Iconografía
- Diez íconos de 24 × 24 px con estilo sólido y redondeado: `home`, `receipt`, `camera`, `camera-white`, `quiz`, `arrow-right`, `arrow-left`, `chevron-down`, `check` y `x`.
- Los íconos de resultado (`check` y `x`) se usan a 48 px dentro de un círculo de 80 px.
- Los íconos siempre acompañan a un texto; nunca deben ser el único indicador de una acción.

---

## 6. Patrones de interacción

| Patrón | Comportamiento |
|---|---|
| **Avance lineal** | El flujo va siempre hacia adelante con "Siguiente". "Regresar" vuelve a la pantalla anterior sin perder los datos capturados |
| **Validación en línea** | Los errores aparecen junto al campo correspondiente, no en una alerta al final |
| **Usuario nuevo o registrado** | Desde las pantallas 02 y 04 se puede cambiar de camino con un enlace ("¿Primera vez participando?" / "¿Ya ha participado antes?") |
| **Diálogo solo cuando se interrumpe el flujo** | Se usa únicamente cuando el sistema cambia la ruta del usuario (número no registrado) |
| **Resultado sin culpa** | Si se falla la trivia, el mensaje agradece, explica y ofrece reintentar |

---

## 7. Redacción (UX writing)

1. **Lectura fácil** (RNF-006): frases cortas, de una idea, con estructura sujeto + verbo + predicado.
2. **Botones con verbos de acción:** "Comenzar", "Siguiente", "Tomar foto del ticket", "Entendido".
3. **Errores que dicen cómo corregir:** "El monto mínimo para participar es de $200" en lugar de "Monto inválido".
4. **Trato consistente.** Hoy se mezclan "Ingresa" (tú) y "Ingrese" / "Presione" (usted). Recomendación: usar **tú** en todo el flujo, porque es más cercano y coincide con el tono de la campaña.
5. **Ortografía.** Hay que corregir en Figma: *número*, *telefónico*, *aquí* y *participando* (en minúscula).

---

## 8. Accesibilidad (resumen)

| Criterio | Estado |
|---|---|
| Contraste de texto ≥ 4.5:1 | ⚠️ Ver sección 2.3 |
| Áreas táctiles ≥ 44 px | ⚠️ Botón primario (40 px) y casilla (20 px) |
| No depender solo del color | ✅ Errores con texto, pasos con número |
| Tamaño de texto legible | ⚠️ Campos de 12–13 px; recomendado 16 px |
| Diseño en 360 px sin scroll horizontal | ✅ (RNF-001) |
| Etiquetas visibles en todos los campos | ✅ |

---

## 9. Pendientes de diseño

- [ ] Ajustar los colores para cumplir el contraste AA (sección 2.3) y alinear la paleta con RNF-005.
- [ ] Agregar la flecha de *scroll down* en la pantalla de inicio (RF-001).
- [ ] Diseñar el estado de **foto del ticket tomada** (vista previa con opción de repetir).
- [ ] Mostrar el **folio** en la pantalla de participación confirmada (RF-014).
- [ ] Convertir el diálogo y el estado de error del campo en componentes.
- [ ] Subir los botones primarios a 44 px y el texto de los campos a 16 px.
- [ ] Unificar el trato (tú/usted) y corregir la ortografía.
- [ ] Validar el prototipo con el cliente (CANACO SERVYTUR) y registrar sus comentarios.
