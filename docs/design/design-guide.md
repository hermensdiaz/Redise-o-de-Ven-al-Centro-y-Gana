# Guía de diseño — Ven al Centro y Gana

**Versión:** 2.0 · Segunda entrega
**Fuente:** [Archivo de Figma — Flujo de registro](https://www.figma.com/design/sVxsBw6xtnTPWCtjMJrPL7/Ven-al-Centro-y-Gana-%E2%80%93-Flujo-de-registro?node-id=0-1&t=DLfkUYIZnpshV6pP-0) (página `Pantallas`, sección `Componentes`)
**Alcance:** flujo de registro de participantes en móvil (inicio, registro, datos de la compra, trivia y resultado)

Esta guía documenta las decisiones visuales y de interacción del rediseño, para que cualquier pantalla nueva sea consistente con las existentes y para que el equipo de desarrollo implemente el diseño sin ambigüedades. Las medidas corresponden al diseño **versión 2** (17 pantallas, ver [screens.md](screens.md)).

---

## 1. Principios de diseño

Los principios salen directamente de los hallazgos de la prueba de campo y de los requisitos.

| Principio | Qué significa | Cómo se aplica | Requisito |
|---|---|---|---|
| **Una acción clara por pantalla** | El usuario siempre sabe qué hacer después | Un solo botón principal a ancho completo, al final del contenido | RF-001, RNF-005 |
| **Saber dónde estoy** | El usuario conoce su avance en el proceso | Indicador "Paso X de 4" con barra de 4 etapas con nombre | RNF-007 |
| **Prevenir antes que corregir** | Evitar errores en lugar de castigarlos | Ejemplos dentro de cada campo, teclado adecuado, ayuda visible antes del error | RF-007, RF-010, RNF-009 |
| **Explicar cómo corregir** | Si hay un error, el usuario sabe qué hacer | Validación al presionar "Siguiente", resumen de errores y mensaje específico por campo | RF-021, RNF-010 |
| **No perder el trabajo** | Un toque accidental no borra lo capturado | Confirmación antes de salir, "Regresar" conserva los datos | RF-016, RNF-003 |
| **Lectura fácil** | Cualquier persona, incluidos adultos mayores, entiende el texto | Frases cortas, sujeto + verbo + predicado, trato de "tú" | RNF-006, RNF-012 |
| **Móvil primero** | La mayoría participa desde el celular, en la calle | Diseño en 360 px de ancho, una sola columna, áreas táctiles grandes | RNF-001, RNF-008 |

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
| Error (mensajes de validación) | `#DC3545` (contraste 4.53:1, definido en RNF-005) |
| Overlay de diálogo | `texto/principal` (#111827) al 60 % de opacidad |

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
| `texto/principal` sobre `acento/amarillo` | 10.45:1 | ✅ | ✅ |

**Ajustes recomendados** para cumplir RNF-005 sin perder la identidad de la marca:

| Elemento | Cambio | Contraste resultante |
|---|---|---|
| Botón destacado amarillo | Texto `#111827` en lugar de blanco | 10.45:1 ✅ |
| Header y botones naranjas | Fondo `#C2410C` (naranja oscuro) con texto blanco | 5.18:1 ✅ |
| Header y botones naranjas (alternativa) | Mantener `#FF6A00` con texto `#111827` | 6.18:1 ✅ |
| Enlaces | `#B45309` (ámbar oscuro), subrayado | 5.02:1 ✅ |
| Placeholder | `#4B5563` | 6.86:1 ✅ |

Además, en los requisitos la paleta oficial aparece como `#F25A24 / #FFC107 / #1E2B58` (RNF-005), mientras que el prototipo usa `#FF6A00 / #FFBB0B / #111827`. Hay que **alinear ambos documentos**: actualizar el RNF o los tokens, según lo que confirme el cliente.

**Color de error:** el diseño versión 2 usa `#DC3545` (definido en RNF-005), con un contraste de 4.53:1 sobre blanco. Siempre va acompañado de un ícono y un texto (RNF-010).

---

## 3. Tipografía

Se usan dos familias de Google Fonts:
- **Poppins:** títulos, botones, preguntas y opciones de la trivia. Es geométrica y amigable, y combina con el estilo del logotipo.
- **Noto Sans:** texto de lectura, etiquetas y campos. Es muy legible en tamaños pequeños.

| Uso | Familia | Peso | Tamaño | Interlineado |
|---|---|---|---|---|
| Título del header | Poppins | SemiBold 600 | 20 px | 130 % |
| Título de pantalla (formularios) | Poppins | SemiBold 600 | 22 px | 130 % |
| Título de inicio | Poppins | SemiBold 600 | 24 px | 125 % |
| Pregunta de la trivia | Poppins | SemiBold 600 | 24 px | 130 % |
| Título de resultado | Poppins | SemiBold 600 | 26 px | 125 % |
| Título de instrucciones de la trivia | Poppins | SemiBold 600 | 28 px | 130 % |
| Botón principal | Poppins | SemiBold 600 | 20 px (18 px en diálogos) | 130 % |
| Botón destacado ("Comenzar", "Entendido") | Poppins | SemiBold 600 | 24 px / 22 px | 130 % |
| Enlaces de acción y "Regresar" | Poppins | SemiBold 600 | 15 px | 130 % |
| Opción de la trivia | Poppins | Regular 400 (Medium 500 seleccionada) | 17 px | 140 % |
| Texto dentro de los campos | Noto Sans | Regular 400 | **16 px** | 150 % |
| Etiqueta de campo, "Paso X de 4" | Noto Sans | Medium 500 | 14 px | 150 % |
| Párrafos y subtítulos | Noto Sans | Regular 400 | 14–15 px | 145–150 % |
| Ayudas y mensajes de error | Noto Sans | Regular 400 | 13 px | 140 % |
| Etiquetas de las etapas del indicador | Noto Sans | Regular 400 (SemiBold 600 la actual) | 12 px | 150 % |

El texto dentro de los campos mide 16 px (RNF-008): en iOS, un campo con texto menor provoca un zoom automático al enfocarlo, y el texto pequeño dificulta la lectura a los adultos mayores.

---

## 4. Espaciado y retícula

| Elemento | Medida |
|---|---|
| Ancho de la pantalla base | 360 px |
| Margen lateral | **24 px** (RNF-005) |
| Ancho del contenido | **312 px** (una sola columna) |
| Altura del header | **52 px** |
| Espacio entre el header y el contenido | 8 px (16 px en pantallas sin "Regresar") |
| Separación entre bloques (indicador, título, formulario, botón) | 20 px (16–18 px en datos de la compra) |
| Separación entre campos de formulario | 20 px (RNF-005 exige al menos 16 px) |
| Separación entre etiqueta, campo y ayuda | 6 px |
| Separación entre opciones de la trivia | 14 px |

**Escala de espaciado:** múltiplos de 2 y 4 (4, 6, 8, 12, 14, 16, 20, 24).

---

## 5. Componentes

En el archivo de Figma versión 2, cada elemento está construido con **auto-layout** y tiene un nombre descriptivo (por ejemplo, "Campo · Nombre(s)", "Botón · Siguiente" u "Opción de trivia · Seleccionada"). Convertirlos en componentes reutilizables de Figma está pendiente (ver sección 9).

### 5.1 Header
- Barra naranja (`primario/naranja`) de **52 px**, con el título de la etapa centrado ("Registro", "Datos de la compra", "Trivia", "Resultado").
- El ícono `home` (24 px) a la izquierda tiene un área táctil de 44 × 44 px y abre el diálogo de salida (RF-016).
- La pantalla de inicio y las de resultado no muestran el ícono.

### 5.2 Indicador de paso
- Texto "Paso X de 4" (Noto Sans Medium 14 px).
- Debajo, **4 segmentos** de 8 px de alto, con esquinas de 4 px y 6 px de separación, cada uno con su etiqueta: Registro, Compra, Trivia, Resultado.
- Los segmentos completados y el actual van en `primario/progreso`; los pendientes, en `neutro/track`.
- Las etapas completadas llevan "✓" y la actual va en negritas (RNF-007).

### 5.3 Botones

| Tipo | Medidas | Estilo | Cuándo usarlo |
|---|---|---|---|
| **Principal** | 312 × 52 px, esquinas de 8 px | Fondo `primario/naranja`, texto blanco 20 px, flecha `arrow-right` si avanza | "Siguiente", "Continuar", "Finalizar", "Terminar trivia" |
| **Destacado** | 312 × 56 px, esquinas de 10 px | Fondo `acento/amarillo`, texto blanco 22–24 px | Una sola vez por pantalla: "Comenzar", "Entendido" |
| **Con ícono** | 312 × 52 px, esquinas de 8 px | Fondo `primario/progreso`, ícono `camera` | "Tomar foto del ticket" |
| **Secundario con borde** | 312 × 52 px, borde de 2 px | Fondo blanco, borde y texto `primario/naranja` | "Registrarme por primera vez" |
| **Enlace de acción** | Alto de 44 px | Texto `primario/naranja` (o rojo `#DC3545` si es destructivo), Poppins 15 px | "Corregir mi número", "Registrar otra compra", "Salir al inicio" |
| **Regresar** | Alto de 44 px, alineado a la izquierda | Texto `primario/naranja` con flecha `arrow-left` | Arriba del contenido, separado del botón principal (RNF-003) |

**Reglas:**
- El botón "Siguiente" **siempre está activo**; la validación ocurre al presionarlo (RF-021). El color gris `neutro/deshabilitado` se reserva para casos excepcionales.
- Los botones principales ocupan todo el ancho del contenido y empiezan con un verbo.

### 5.4 Campo de formulario
- Etiqueta arriba (Noto Sans Medium 14 px) y campo de **312 × 52 px**, con fondo `superficie/input`, borde de 1 px `borde/input` y esquinas de 8 px.
- El **ejemplo** va dentro del campo, con el formato "Ej.: …" (RF-007, RNF-002).
- Prefijos y sufijos: "+52" en el celular; "$" y "MXN" en el monto (RNF-009).
- Texto de ayuda opcional debajo (13 px, `texto/secundario`), por ejemplo "La compra mínima es de $200." o el contador "10/10".
- **Estado con foco o válido:** borde de 2 px `primario/naranja`, con palomita opcional.
- **Estado de error:** borde de 2 px `#DC3545` y, debajo, un ícono de alerta de 16 px con el mensaje en rojo (RNF-010).
- **Selector:** igual que un campo, con `chevron-down` a la derecha; al tocarlo abre el panel inferior (5.9).

### 5.5 Resumen de errores
- Recuadro de ancho completo con borde de 1 px `#DC3545`, esquinas de 10 px y relleno de 12 × 14 px.
- Ícono de alerta de 20 px y el texto "**Revisa N datos** marcados en rojo para continuar." (RF-021).
- Se coloca arriba del título del formulario.

### 5.6 Aceptar aviso de privacidad
- Casilla de 24 px (borde de 2 px `texto/secundario`, esquinas de 4 px) dentro de una fila de 44 px de alto, que es su área táctil.
- Texto: "He leído y acepto el **aviso de privacidad**", con el enlace en `texto/enlace` y un ícono de pestaña externa.
- Solo aparece en el formulario de registro (RF-008).

### 5.7 Opción de la trivia
- Tarjeta de 312 × 60 px, fondo blanco, esquinas de 12 px y borde de 2 px `acento/amarillo-deshabilitado` (#FDE49A).
- Indicador circular de 24 px y texto Poppins 17 px. Toda la tarjeta es tocable.
- **Seleccionada:** borde de 3 px `primario/naranja`, indicador relleno y texto en Medium (RNF-006).
- Arriba de la pregunta: el contador "Pregunta X de 3" con 3 puntos de avance (el actual mide 24 px de ancho).

### 5.8 Diálogo
- Tarjeta blanca de 312 px de ancho, esquinas de 16 px, relleno de 24 px, sombra suave, centrada vertical y horizontalmente.
- Overlay `texto/principal` al 60 % de opacidad.
- Contenido: ícono en un círculo de 56 px, título (Poppins 21 px), mensaje, botón principal y un enlace de acción secundaria.
- Se usa en "Número no registrado" (RF-005) y "Salir del registro" (RF-016).

### 5.9 Panel inferior (*bottom sheet*)
- Panel de 360 px de ancho que sube desde la parte inferior, con esquinas superiores de 20 px y una agarradera gris de 40 × 4 px.
- Título, botón de cerrar (✕), buscador con borde naranja y lista de elementos de 64 px separados por una línea.
- Se usa para elegir la sucursal (RF-017).

### 5.10 Tarjeta informativa
- Fondo `superficie/icono`, esquinas de 14 px y relleno de 16 px.
- Ícono de 24 px a la izquierda, título en Poppins SemiBold 16 px y texto de 15 px.
- Se usa en los resultados: "Revisa tu celular y tu correo" y "Puedes participar otra vez".

### 5.11 Iconografía
- Íconos de línea de 24 × 24 px (trazo de 2 px, extremos redondeados): `home`, `receipt`, `camera`, `quiz`, `arrow-right`, `arrow-left`, `chevron-down`, `check`, `x`, `alert`, `search`, `pin`, `user`, `mail`, `refresh`, `external-link`.
- Los íconos de los pasos de inicio van en contenedores de 44 px con esquinas de 10 px.
- Los íconos de resultado van a 40 px dentro de un círculo de 80 px: `check` blanco sobre naranja (éxito) y `x` rojo sobre `superficie/icono` (intento fallido).
- Los íconos siempre acompañan a un texto; nunca son el único indicador de una acción.

---

## 6. Patrones de interacción

| Patrón | Comportamiento | Requisito |
|---|---|---|
| **Avance lineal** | El flujo avanza con "Siguiente". "Regresar" vuelve a la pantalla anterior sin perder los datos | RNF-003 |
| **Validación al avanzar** | Al presionar "Siguiente" se muestran el resumen de errores y el mensaje de cada campo | RF-021 |
| **Usuario nuevo o registrado** | El número decide el camino; también se puede ir directo con "Registrarme por primera vez" o regresar con "¿Ya participaste antes?" | RF-004-A, RF-004-B, RF-005 |
| **Confirmación de acciones destructivas** | Salir del registro pide confirmación | RF-016 |
| **Revisar antes de confirmar** | Vista previa de la foto; "Pregunta anterior" antes de terminar la trivia | RF-018, RF-019 |
| **Resultado sin culpa** | Si se falla la trivia, el mensaje agradece, explica y ofrece registrar otra compra | RF-015, RF-020 |
| **Datos personales protegidos** | El número se muestra parcialmente oculto en bienvenida y resultados | RNF-011 |

---

## 7. Redacción (UX writing)

1. **Lectura fácil** (RNF-006 y RNF-012): frases cortas, de una idea, con estructura sujeto + verbo + predicado.
2. **Trato de "tú"** en todo el flujo: "Ingresa", "Registra", "Revisa".
3. **Botones con verbos de acción:** "Comenzar", "Siguiente", "Registrar mis datos", "Tomar foto del ticket", "Terminar trivia".
4. **Errores que dicen cómo corregir:** "El número es muy corto. Te faltan 2 dígitos." o "Falta la terminación del correo, por ejemplo: nombre@correo.com".
5. **Ejemplos con el formato "Ej.: …"** dentro de los campos.

---

## 8. Accesibilidad (resumen)

| Criterio | Estado en la versión 2 |
|---|---|
| Contraste de texto ≥ 4.5:1 | ⚠️ Pendiente en los botones naranjas y amarillos (sección 2.3) |
| Áreas táctiles ≥ 44 px | ✅ Botones de 52 px; casilla, "Regresar" e ícono de inicio con área de 44 px |
| No depender solo del color | ✅ Errores con ícono y texto; etapas con nombre y ✓ |
| Texto de los campos ≥ 16 px | ✅ |
| Diseño en 360 px sin scroll horizontal | ✅ (RNF-001) |
| Etiquetas visibles en todos los campos | ✅ |

---

## 9. Pendientes de diseño

- [ ] Ajustar los colores para cumplir el contraste AA (sección 2.3) y alinear la paleta con RNF-005.
- [ ] Corregir la errata de la pantalla 10b: "registrado" → "registrando".
- [ ] Convertir en componentes de Figma los elementos repetidos (header, indicador de paso, botones, campo, opción de trivia, diálogo).
- [ ] Enlazar las pantallas en Figma como prototipo navegable.

### Resueltos en la versión 2
- [x] Flecha "Toca aquí para empezar" en la pantalla de inicio (RF-001).
- [x] Estado de foto del ticket tomada, con vista previa y opción de repetir (RF-018).
- [x] Folio: se decidió **no** mostrarlo en pantalla porque requeriría cambios en el backend; se informa su envío por SMS y correo (RF-014).
- [x] Diálogo y estado de error de los campos diseñados de forma consistente.
- [x] Botones de 52 px y texto de los campos de 16 px.
- [x] Trato de "tú" unificado y ortografía corregida.
- [x] Validación del prototipo con el cliente (CANACO SERVYTUR).
