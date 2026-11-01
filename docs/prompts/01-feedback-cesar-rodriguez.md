# Prompt 01 · Carpeta de comentarios y feedback

| Campo | Detalle |
|---|---|
| **Fecha y hora** | 31/10/2026, 19:27 (hora de Mérida) |
| **Categoría** | Documentación |
| **Rama** | `segunda-entrega` |
| **Commit** | [6150af6](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/6150af6) |
| **Archivos** | [docs/comentarios-y-feedback/feedback-cesar-rodriguez.md](../comentarios-y-feedback/feedback-cesar-rodriguez.md) |

## Prompt

```text
En el apartado de docs/ añade un carpeta que diga comentarios y feedback, la persona que revisa nuestro proyecto llamada César Rodríguez, estuvo dándonos constante feedback de todo lo que necesitábamos cambiar e hicimos esas correcciones, crea un archivo markdown con el feedback y evidentemente con las correcciones que hicimos, puedes anexar los enlaces en donde están las correcciones


algunas de sus observaciones fueron:

En los RF, en lugar de (cliente...)
Poner: Usuario que es el concursante que realiza la trivia

Respecto al Flujo principal, en la práctica se separa cada "punto"

La métrica es un dato certero, el 95% de las personas que...

Lograr requiere que nosotros hagamos algo, no use la palabra "lograr"

En lugar de poner 
Ingresar un dato incorrecto? 

Sí ingresa una letra..., corregir En el flujo alterno rf-004


"Encale" | cambiar la ortografía

En métrica del RF-008, argumentar con un Health check, así podemos decir: El 100% de todas la veces...

Rf-009 no pusimos métrica 

Usa: El sistema va a permitir...

RF-010 
"Verification si el monto es correcto"? cambiar la ortografía

En el RF-013, La métrica es cualitativa, debemos hacerlo de una forma cuantitativa

No usar puede o debe, debemos usar afirmaciones

En el RF-014, Quitar la tabla

Solucionaron el problema del "click accidental" que llevaba a los usuarios a salir a mitad del registro, regresar a la pantalla principal y perder su progreso, fue buena idea agregar una advertencia en el ícono de regresar
Me agrada que hayan dejado mas compacto la pantalla principal
Les quedó muy bien, ¿alguna corrección? Ninguna
```

## Resultado

- Se creó la carpeta `docs/comentarios-y-feedback/` con el archivo `feedback-cesar-rodriguez.md`.
- Cada observación quedó documentada con la corrección aplicada y los enlaces al RF, al commit y al issue correspondiente (#38, #39, #40, #41).
- Cuatro observaciones quedaron como **parciales** (🟡) porque todavía hay casos sin corregir: "lograr", el *health check* de RF-008, "debe/puede" y "El sistema permite…".
- El commit se rehizo con el autor verificado (de `8bf6fbe` a `6150af6`) sin cambiar el contenido.
