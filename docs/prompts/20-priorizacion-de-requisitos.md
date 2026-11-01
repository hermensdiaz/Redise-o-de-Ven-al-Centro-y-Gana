# Prompt 20 · Priorización de requisitos y convención de commits

| Campo | Detalle |
|---|---|
| **Fecha y hora** | 31/10/2026, 12:44 (hora de Mérida) |
| **Categoría** | Requisitos |
| **Rama** | `segunda-entrega` |
| **Commit** | [2791d91](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/2791d91) |
| **Archivos** | [docs/requirements/priorizacion-requisitos.md](../requirements/priorizacion-requisitos.md) · [README.md](../../README.md) |

## Prompt

```text
Ahora has una lista de priorización de requisitos, es decir una lista de los requisitos que son prioritarios, es un archivo md, agrégalo en la rama segunda-entrega en docs/requeriments

otra cosa, cuando hagas el commit hazlo con convenciones como fix, feat, docs, etc.
```

## Resultado

- Se creó la priorización con el método MoSCoW: 12 requisitos funcionales "Debe" (42 puntos), 8 "Debería" (13) y 2 "Podría" (5), más la priorización de los 12 RNF y un orden de implementación en 3 iteraciones.
- La prioridad de cada RF coincide con la de su historia de usuario.
- El archivo se guardó en `docs/requirements/`, la carpeta existente, en lugar de crear `docs/requeriments`.
- Se agregó el enlace en el README principal.
- Desde este prompt, los commits siguen Conventional Commits: `docs(requirements): agregar priorización de requisitos con MoSCoW`.
- Después, el usuario ajustó el archivo en el commit [92fac3e](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/92fac3e) (`fix: incorrect information`).
