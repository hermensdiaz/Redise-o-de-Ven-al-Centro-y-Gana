# Diseño de interfaces — Ven al Centro y Gana

## 🔗 Enlace al diseño en Figma

**[Ven al Centro y Gana – Flujo de registro (Figma)](https://www.figma.com/design/sVxsBw6xtnTPWCtjMJrPL7/Ven-al-Centro-y-Gana-%E2%80%93-Flujo-de-registro?node-id=0-1&t=DLfkUYIZnpshV6pP-0)**

- **Herramienta:** Figma
- **Página del archivo:** `Pantallas`
- **Tipo de prototipo:** media fidelidad, enfocado en móvil (360 × 800 px)
- **Entrega:** Segunda entrega (rama `segunda-entrega`)

---

## ¿Qué se hizo?

A partir de los requisitos funcionales (RF-001 a RF-015) y no funcionales (RNF-001 a RNF-006), el equipo rediseñó en Figma el **flujo completo de registro de participantes** de la aplicación web *Ven al Centro y Gana* de CANACO SERVYTUR. El objetivo fue resolver los problemas de usabilidad detectados en la prueba de campo: el botón "Comenzar" difícil de encontrar, los formularios confusos, el registro del ticket y la trivia.

El trabajo se organizó en tres partes:

### 1. Sistema de diseño (sección `Componentes`)
Se construyó una biblioteca de componentes reutilizables con variantes, para que todas las pantallas sean consistentes:

| Componente | Variantes |
|---|---|
| Íconos | home, receipt, camera, camera-white, quiz, arrow-right, arrow-left, chevron-down, check, x |
| Header | Barra superior naranja con ícono de inicio y título |
| Indicador de paso | Paso 1, 2, 3 y 4 de 4 (barra de progreso) |
| Botón | Primario, Destacado, Deshabilitado, Destacado deshabilitado |
| Botón pequeño | "Regresar" |
| Botón con ícono | "Tomar foto del ticket" |
| Campo de formulario | Texto con placeholder, texto con valor, selector |
| Aceptar aviso de privacidad | Marcado / No marcado |
| Opción de trivia | Seleccionada / No seleccionada |
| Paso de participación | Ícono + texto (pantalla de inicio) |
| Logo | Logotipo de la campaña |

Además se definieron **variables de color y estilos de texto** (tokens). Están documentados en la [guía de diseño](design-guide.md).

### 2. Pantallas del flujo (versión 2)
A partir de los requisitos versión 2.0 (RF-001 a RF-021 y RNF-001 a RNF-012), el diseño se amplió a **17 pantallas**, organizadas en las 4 etapas del flujo:

| Etapa | Pantallas |
|---|---|
| 1. Inicio e identificación | 01 · Inicio, 02 · Ingreso con teléfono, 02b · Teléfono con error, 03 · Número no registrado, 03b · Usuario ya registrado, Diálogo · Salir del registro |
| 2. Registro de datos | 04 · Registro de nuevo participante, 04b · Registro con errores |
| 3. Datos de la compra | 05 · Datos de la compra, 05b · Elegir sucursal, 05c · Compra con errores, 05d · Compra completa (foto tomada) |
| 4. Trivia y resultado | 06 · Instrucciones, 07 · Pregunta 1, 09 · Pregunta 3, 10 · Respuestas correctas, 10b · Respuestas incorrectas |

El detalle de cada pantalla, su correspondencia con los requisitos y la comparación con la versión 1 están en **[screens.md](screens.md)**.

### 3. Guía de diseño
Se documentaron los fundamentos visuales del rediseño: color, tipografía, espaciado, componentes, accesibilidad y redacción. Ver **[design-guide.md](design-guide.md)**.

---

## Contenido de esta carpeta

| Archivo | Descripción |
|---|---|
| [`README.md`](README.md) | Este documento: enlace al diseño y resumen del trabajo |
| [`screens.md`](screens.md) | Inventario de pantallas, flujo de navegación y correspondencia con RF/HU |
| [`design-guide.md`](design-guide.md) | Guía de diseño (tokens, componentes, accesibilidad, UX writing) |
| [`components.png`](components.png) | Captura de la biblioteca de componentes (versión 1) |
| [`screens/`](screens) | Capturas de las 17 pantallas de la versión 2, exportadas desde Figma |
