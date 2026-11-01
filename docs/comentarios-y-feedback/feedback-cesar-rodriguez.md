# Comentarios y feedback — César Rodríguez

**Revisor:** César Rodríguez
**Proyecto:** Rediseño de Ven al Centro y Gana
**Documentos revisados:** Requisitos funcionales (RF) y diseño de pantallas en Figma

Este documento concentra las observaciones que nos dio César Rodríguez durante la revisión del proyecto y las correcciones que hicimos para atender cada una. Cada corrección incluye el enlace al archivo donde se aplicó y, cuando existe, al commit o issue que la registra.

> **Nota sobre las ramas:** las correcciones vigentes están en la rama [`segunda-entrega`](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/tree/segunda-entrega), donde los requisitos están en `docs/requirements/`. En `main`, el PR [#46](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/pull/46) se revirtió con el PR [#57](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/pull/57), por lo que algunos archivos de `main` todavía muestran la versión anterior.

**Simbología del estado:**
- ✅ Aplicada: la corrección está en el repositorio.
- 🟡 Parcial: se corrigió en algunos requisitos, pero aún quedan casos por ajustar.

---

## Resumen

| # | Observación | Requisito(s) | Estado |
|---|---|---|---|
| 1 | Cambiar "Cliente" por "Usuario" en Actores | Todos los RF | ✅ |
| 2 | Separar cada punto del Flujo principal | Todos los RF | ✅ |
| 3 | La métrica es un dato certero | RF-001 | ✅ |
| 4 | No usar la palabra "lograr" | RF-001, RF-009, RF-015 | 🟡 |
| 5 | Cambiar "Ingresar un dato incorrecto" por "Si ingresa una letra…" | RF-004 | ✅ |
| 6 | Ortografía: "Encale" | RF-008 | ✅ |
| 7 | Argumentar la métrica con un *health check* | RF-008 | 🟡 |
| 8 | Falta la métrica | RF-009 | ✅ |
| 9 | Usar "El sistema va a permitir…" | Todos los RF | 🟡 |
| 10 | Ortografía: "Verification si el monto es correcto" | RF-010 | ✅ |
| 11 | La métrica debe ser cuantitativa | RF-013 | ✅ |
| 12 | No usar "puede" o "debe"; usar afirmaciones | Todos los RF | 🟡 |
| 13 | Quitar la tabla | RF-014 | ✅ |
| 14 | Problema del "clic accidental" (comentario positivo) | RF-016, RNF-003 | ✅ |
| 15 | Pantalla principal más compacta (comentario positivo) | RF-001 | ✅ |
| 16 | ¿Alguna corrección? Ninguna | Diseño v2 | ✅ |

---

## 1. Observaciones sobre los requisitos funcionales

### 1.1 Actores: "Usuario" en lugar de "Cliente"
**Feedback:** En los RF, en lugar de "(Cliente…)", poner: Usuario que es el concursante que realiza la trivia.

**Corrección:** En la sección **Actores** de todos los RF se reemplazó "Cliente que participa en la dinámica" por **"El Concursante (Usuario que participa en la dinámica)"**. El último caso pendiente, RF-015, se corrigió en la versión 2.0.

**Evidencia:**
- Commits [96a1548](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/96a1548) (PR [#39](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/pull/39)) y [09b5004](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/09b5004) (PR [#40](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/pull/40))
- Ejemplo: [RF-015](../requirements/functional/RF-015.md)

### 1.2 Flujo principal separado por puntos
**Feedback:** Respecto al Flujo principal, en la práctica se separa cada "punto".

**Corrección:** Los pasos del **Flujo principal** y de los **Flujos alternos** quedaron como listas numeradas (1, 2, 3…), un paso por línea.

**Evidencia:**
- Commits [96a1548](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/96a1548) y [09b5004](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/09b5004)
- Ejemplos: [RF-002](../requirements/functional/RF-002.md), [RF-004-A](../requirements/functional/RF-004-A.md), [RF-010](../requirements/functional/RF-010.md)

### 1.3 La métrica es un dato certero
**Feedback:** La métrica es un dato certero: "el 95 % de las personas que…".

**Corrección:** La métrica de RF-001 se redactó con un porcentaje concreto: **"El sistema permite que el 95 % de las personas encuentren el botón 'Comenzar' completamente solas."**

**Evidencia:**
- Commit [96a1548](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/96a1548)
- Archivo: [RF-001](../requirements/functional/RF-001.md)

### 1.4 No usar la palabra "lograr" 🟡
**Feedback:** "Lograr" requiere que nosotros hagamos algo; no usar la palabra "lograr".

**Corrección:** En RF-001 se cambió "Lograr que el 95 % de las personas…" por "El sistema permite que el 95 % de las personas…".

**Evidencia:**
- Commit [96a1548](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/96a1548)
- Archivo: [RF-001](../requirements/functional/RF-001.md)

**Pendiente:** la palabra todavía aparece en la métrica de [RF-009](../requirements/functional/RF-009.md) ("debe lograr seleccionar…") y de [RF-015](../requirements/functional/RF-015.md) ("Lograr que el 100 %…").

### 1.5 RF-004: "Si ingresa una letra…" en el flujo alterno
**Feedback:** En lugar de poner "¿Ingresar un dato incorrecto?", poner "Si ingresa una letra…". Corregir en el flujo alterno de RF-004.

**Corrección:** Se separaron los casos de error del número telefónico en flujos alternos específicos, incluido el caso de las letras:
- A2. El concursante ingresa un número inferior a 10 dígitos → "El número es muy corto".
- A3. El concursante ingresa un número superior a 10 dígitos → "El número es muy largo".
- **A4. El concursante ingresa caracteres no numéricos → "Solo se permiten caracteres numéricos".**

**Evidencia:**
- Issue [#41](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/41) y commit [fb85312](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/fb85312)
- Archivo: [RF-004-A](../requirements/functional/RF-004-A.md) (RF-004 se dividió después en RF-004-A y RF-004-B)

### 1.6 RF-008: ortografía de "Encale"
**Feedback:** "Encale": cambiar la ortografía.

**Corrección:** En el flujo principal se corrigió a **"El concursante presiona el enlace 'avisos de privacidad'"**.

**Evidencia:**
- Issue [#41](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/41) y commit [fb85312](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/fb85312)
- Archivo: [RF-008](../requirements/functional/RF-008.md)

### 1.7 RF-008: métrica argumentada con un *health check* 🟡
**Feedback:** En la métrica de RF-008, argumentar con un *health check*; así podemos decir: "El 100 % de todas las veces…".

**Corrección:** La métrica cambió de "Los nuevos concursantes pueden acceder al documento…" a **"El 100 % de los nuevos concursantes debe poder acceder al aviso de privacidad antes de completar su registro."**

**Evidencia:**
- Issue [#41](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/41) y commit [fb85312](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/fb85312)
- Archivo: [RF-008](../requirements/functional/RF-008.md)

**Pendiente:** la métrica todavía no menciona el *health check* que respalda el 100 % (por ejemplo, una verificación periódica de que el enlace del aviso responde), y conserva la forma "debe poder" (ver 1.12).

### 1.8 RF-009: faltaba la métrica
**Feedback:** En RF-009 no pusimos métrica.

**Corrección:** La métrica pasó de "El sistema permite seleccionar la sucursal participante" (que no se podía medir) a **"El 95 % de los concursantes selecciona la sucursal de compra en el primer intento, sin que se muestre el mensaje 'Campo obligatorio'"**.

**Evidencia:**
- Issue [#41](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/41) y commit [fb85312](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/fb85312)
- Archivo: [RF-009](../requirements/functional/RF-009.md)

### 1.9 Usar "El sistema va a permitir…" 🟡
**Feedback:** Usa: "El sistema va a permitir…".

**Corrección:** Las descripciones de los requisitos inician con el sistema como sujeto ("El sistema permite…", "El sistema muestra…"). Ejemplos: [RF-002](../requirements/functional/RF-002.md), [RF-004-A](../requirements/functional/RF-004-A.md), [RF-009](../requirements/functional/RF-009.md), [RF-010](../requirements/functional/RF-010.md), [RF-011](../requirements/functional/RF-011.md).

**Evidencia:**
- Commit [b9232c6](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/b9232c6) (versión 2.0 de los RF)

**Pendiente:** [RF-007](../requirements/functional/RF-007.md) inicia con "En los campos de RF-006 se deben especificar…" y [RF-008](../requirements/functional/RF-008.md) con "El sistema debe permitir…".

### 1.10 RF-010: ortografía de "Verification si el monto es correcto"
**Feedback:** "Verification si el monto es correcto": cambiar la ortografía.

**Corrección:** Se eliminó la palabra en inglés y se reescribió el requisito en español. La descripción quedó como **"El sistema permite ingresar el monto mostrado en el ticket de compra…"**, y la validación del monto se describe en los flujos alternos A1 (monto menor a $200) y A2 (campo vacío).

**Evidencia:**
- Archivo: [RF-010](../requirements/functional/RF-010.md)

### 1.11 RF-013: métrica cuantitativa
**Feedback:** En RF-013 la métrica es cualitativa; debemos hacerla cuantitativa.

**Corrección:** La métrica pasó de "La página debe mostrar las 3 preguntas, registrando cuánto es la tasa de éxito…" a **"Al menos el 95 % de los concursantes que inician la trivia responde las 3 preguntas y presiona 'Terminar trivia' sin abandonar la pantalla."**

**Evidencia:**
- Issue [#41](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/41) y commit [fb85312](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/fb85312)
- Archivo: [RF-013](../requirements/functional/RF-013.md)

### 1.12 No usar "puede" o "debe"; usar afirmaciones 🟡
**Feedback:** No usar "puede" o "debe"; debemos usar afirmaciones.

**Corrección:** Los flujos principales y alternos se redactaron en forma afirmativa ("El sistema detecta…", "El sistema muestra…"), y en RF-001 y RF-009 las métricas pasaron de describir una posibilidad a un dato medible.

**Evidencia:**
- Commits [fb85312](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/fb85312) y [b9232c6](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/b9232c6)

**Pendiente:** todavía hay "debe" o "puede" en la descripción o la métrica de [RF-004-A](../requirements/functional/RF-004-A.md), [RF-007](../requirements/functional/RF-007.md), [RF-008](../requirements/functional/RF-008.md), [RF-009](../requirements/functional/RF-009.md), [RF-010](../requirements/functional/RF-010.md), [RF-013](../requirements/functional/RF-013.md) y [RF-015](../requirements/functional/RF-015.md).

### 1.13 RF-014: quitar la tabla
**Feedback:** En RF-014, quitar la tabla.

**Corrección:** Se eliminó la tabla "Campo | Detalles" y su contenido se reorganizó en secciones con encabezados (Objetivo, Alcance, Actores, Precondiciones, Postcondiciones, Trazabilidad, Flujo principal), igual que el resto de los RF.

**Evidencia:**
- Commit [09b5004](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/09b5004) (PR [#40](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/pull/40))
- Archivo: [RF-014](../requirements/functional/RF-014.md)

> La única tabla que tiene RF-014 ahora es el **Historial de cambios** al final del archivo, que se agregó a todos los RF en la versión 2.0 para la trazabilidad.

---

## 2. Comentarios sobre el diseño (Figma)

### 2.1 Solución al "clic accidental"
**Feedback:** Solucionaron el problema del "clic accidental" que llevaba a los usuarios a salir a mitad del registro, regresar a la pantalla principal y perder su progreso. Fue buena idea agregar una advertencia en el ícono de regresar.

**Qué hicimos:** Al tocar el ícono de inicio durante el registro, aparece la ventana emergente **"¿Quieres salir del registro?"** con el mensaje "Si sales ahora, se borrarán los datos que ya escribiste." y las opciones "Seguir con mi registro" y "Salir al inicio". Además, el botón "Regresar" pasó a ser un enlace de texto en la parte superior, separado del botón principal, para reducir los toques accidentales.

**Evidencia:**
- Requisito nuevo: [RF-016 · Salida del registro con confirmación](../requirements/functional/RF-016.md)
- Requisito relacionado: [RNF-003](../requirements/non-functional/RNF-003.md)
- Pantalla: [Diálogo · Salir del registro](../design/screens.md)
- Commit [c7fa2bd](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/c7fa2bd)

### 2.2 Pantalla principal más compacta
**Feedback:** Me agrada que hayan dejado más compacta la pantalla principal.

**Qué hicimos:** La pantalla de inicio se reorganizó en 3 pasos numerados, un recuadro con la compra mínima de $200, el indicador "Toca aquí para empezar" con flecha, el botón "Comenzar" y los enlaces "Ver bases" y "Ver comercios".

**Evidencia:**
- Requisito: [RF-001 · Pantalla de inicio](../requirements/functional/RF-001.md)
- Pantalla: [01 · Inicio](../design/screens.md)
- Control de cambios: [cambios-segunda-entrega.md](../requirements/cambios-segunda-entrega.md)

### 2.3 Valoración general
**Feedback:** Les quedó muy bien. ¿Alguna corrección? Ninguna.

**Qué hicimos:** No se requirieron cambios adicionales en el diseño.

---

## 3. Referencias

- Control de cambios de la segunda entrega: [cambios-segunda-entrega.md](../requirements/cambios-segunda-entrega.md)
- Issue de correcciones de RF: [#41](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/41)
- Issue de corrección de requisitos: [#38](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/issues/38)
- Diseño en Figma: [Ven al Centro y Gana – Flujo de registro v2](https://www.figma.com/design/E6mFB3CTZQOtWvbkYIXpUk)
