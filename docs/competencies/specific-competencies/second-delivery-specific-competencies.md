# Specific Competencies — Second Delivery

**Competencias específicas desarrolladas en la segunda entrega**

Las siguientes competencias técnicas y metodológicas de la ingeniería de software se fortalecieron durante la segunda entrega del proyecto **«Ven al Centro y Gana»**. Para cada una se argumenta **cómo se promovió** mediante actividades específicas del desarrollo del producto y **dónde está la evidencia**.

> Las competencias de la primera entrega se conservan en [competencias especificas.md](<competencias especificas.md>).

---

## 1. Ingeniería de requisitos: evolución, control de cambios y priorización

**Descripción:** Capacidad de mantener un conjunto de requisitos vivo, que evoluciona con el producto sin perder su trazabilidad.

**Cómo se promovió:**
- **Requisitos nuevos:** se derivaron 6 RF (RF-016 a RF-021) y 6 RNF (RNF-007 a RNF-012) a partir del rediseño de las interfaces.
- **Versión 2.0 de los requisitos existentes:** se actualizaron RF-001 a RF-015, RNF-002 y RNF-006, con flujos principales y alternos completos.
- **Corrección de errores heredados:** se corrigieron referencias de trazabilidad erróneas, un alcance pendiente (RF-004-B) y una métrica faltante (RF-007).
- **Priorización MoSCoW:** con un orden de implementación en tres iteraciones.

**Evidencia:** [Requisitos funcionales](../../requirements/functional) · [Requisitos no funcionales](../../requirements/non-functional) · [Control de cambios](../../requirements/cambios-segunda-entrega.md) · [Priorización](../../requirements/priorizacion-requisitos.md).

---

## 2. Especificación con historias de usuario y criterios de aceptación

**Descripción:** Capacidad de traducir los requisitos en historias de usuario verificables.

**Cómo se promovió:**
- **Historias actualizadas y nuevas:** se actualizaron 16 historias a la versión 2.0 y se crearon 6 nuevas (HU-016 a HU-021), una por cada RF nuevo.
- **Criterios verificables:** cada historia tiene criterios de aceptación en formato Dado / Cuando / Entonces, que incluyen los casos de error (excepciones).
- **Estimación:** cada historia está estimada en puntos (60 en total) y priorizada de forma consistente con los requisitos.

**Evidencia:** [Historias de usuario](../../user-stories/README.md).

---

## 3. Modelado de sistemas con UML

**Descripción:** Capacidad de representar el comportamiento del sistema mediante diagramas UML.

**Cómo se promovió:**
- **Diagrama de casos de uso v2:** se construyó con las relaciones `<<include>>` y `<<extend>>`, un actor secundario (servicio de mensajería) y los casos nuevos resaltados.
- **Diagrama como código:** se modeló en PlantUML, de modo que se puede versionar, revisar y regenerar.
- **Depuración del modelo:** se retiraron dos casos de uso que no tenían un requisito que los respaldara.

**Evidencia:** [Diagramas UML](../../UML/README.md).

---

## 4. Diseño y prototipado de interfaces (UX/UI)

**Descripción:** Capacidad de diseñar interfaces centradas en el usuario a partir de requisitos y evidencia de campo.

**Cómo se promovió:**
- **Prototipo en Figma:** 17 pantallas para móvil (360 px), con estados de error, diálogos y un panel de búsqueda.
- **Sistema visual consistente:** variables de color, estilos de texto y componentes documentados en una guía de diseño.
- **Patrones de usabilidad:** validación con resumen de errores, indicador de progreso por etapas, confirmación antes de acciones destructivas y vista previa de la foto.
- **Iteración documentada:** una tabla comparativa muestra cómo cambió cada aspecto de la versión 1 a la versión 2.

**Evidencia:** [Diseño de interfaces](../../design/README.md) · [Pantallas y comparación v1 → v2](../../design/screens.md) · [Guía de diseño](../../design/design-guide.md).

---

## 5. Trazabilidad entre requisitos y diseño

**Descripción:** Capacidad de verificar que el diseño cubre todos los requisitos y que cada elemento del diseño está justificado.

**Cómo se promovió:**
- **Matriz de correspondencia:** relaciona las 17 pantallas con los 22 RF, las historias de usuario y los RNF. Se verificó que no quedara ningún RF sin pantalla.
- **Requisitos derivados del diseño:** cada funcionalidad nueva del prototipo que no estaba en los requisitos se redactó como RF o RNF antes de darla por válida.

**Evidencia:** [Matriz de correspondencia](../../design/screens.md#matriz-de-correspondencia-pantalla--requisito).

---

## 6. Evaluación de usabilidad y accesibilidad

**Descripción:** Capacidad de evaluar un diseño con criterios objetivos de usabilidad y accesibilidad.

**Cómo se promovió:**
- **Contraste medido con WCAG 2.1 AA:** se midió el contraste de cada combinación de colores. Se encontró que algunos botones no cumplen el mínimo de 4.5:1 que exige RNF-005, y se propusieron alternativas que sí lo cumplen.
- **Requisitos medibles de accesibilidad:** se definieron tamaños mínimos de áreas táctiles (44 px) y de texto en campos (16 px) en RNF-008.
- **Errores no dependientes del color:** los mensajes de error combinan color, ícono y texto (RNF-010).

**Evidencia:** [Guía de diseño, sección 2.3](../../design/design-guide.md) · [RNF-008](../../requirements/non-functional/RNF-008.md) · [RNF-010](../../requirements/non-functional/RNF-010.md).

---

## 7. Automatización del proceso de ingeniería con herramientas de IA

**Descripción:** Capacidad técnica de integrar herramientas de IA en el ciclo de vida del software, conectándolas con las herramientas del equipo (GitHub, Figma) y validando sus resultados.

**Cómo se promovió:**
- **Conexión con las herramientas del equipo:** la IA se conectó con el repositorio de GitHub y con Figma, lo que permitió automatizar el análisis del repositorio, la generación de documentación, la construcción del prototipo y la extracción de capturas.
- **Generación reproducible:** los artefactos generados (diagrama en PlantUML, capturas recortadas por coordenadas, matriz verificada con scripts) se pueden regenerar o comprobar.
- **Validación de resultados:** se verificaron con scripts las referencias cruzadas entre RF, RNF y HU (que no hubiera identificadores inexistentes) y las sumas de puntos de la priorización.

**Evidencia:** historial de commits de `segunda-entrega` · [Diagrama de casos de uso v2](../../UML/casos-de-uso-v2.puml) · [Competencias genéricas, sección 1](../generic-competencies/second-delivery-generic-competencies.md).
