# Prompt 30 · Renombrar las carpetas del repositorio a inglés

| Campo | Detalle |
|---|---|
| **Fecha y hora** | 31/10/2026, 09:47 (hora de Mérida) |
| **Categoría** | Organización del repositorio |
| **Rama** | `rename-folders-english` (PR hacia `main`; la rama ya se eliminó) |
| **Commit** | [496a437](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/commit/496a437) · PR [#59](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/pull/59) (cerrado sin fusionar) |
| **Archivos** | [README.md](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/blob/496a437/README.md) y las carpetas `plantillas/`, `proceso/` (con `acuerdos/`, `bitacoras/`, `tareas/activas/`, `tareas/completadas/`), `docs/Vídeo/`, `docs/bibliografia/`, `docs/competencias/` (con sus dos subcarpetas), `docs/proceso/` y `docs/requisitos/` (con `RF/` y `RNF/`) |

## Prompt

```text
cambiale el nombre a todas las carpetas del repo, cambiales los nombres a Inglés
```

## Resultado

- Se tomó como repositorio `hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana` y se trabajó sobre `main` en la rama nueva `rename-folders-english`.
- Se renombraron 16 carpetas con `git mv` para conservar el historial de los archivos: `plantillas` → `templates`, `proceso` → `process` (`acuerdos` → `agreements`, `bitacoras` → `logs`, `tareas/activas` → `tasks/active`, `tareas/completadas` → `tasks/completed`), `docs/Vídeo` → `docs/video`, `docs/bibliografia` → `docs/bibliography`, `docs/competencias` → `docs/competencies` (`specific-competencies`, `generic-competencies`), `docs/proceso` → `docs/process` y `docs/requisitos` → `docs/requirements` (`RF` → `functional`, `RNF` → `non-functional`).
- No se cambiaron `docs/`, `docs/UML/` ni `.github/`, porque ya estaban en inglés o GitHub necesita esos nombres. Los archivos conservaron sus nombres en español.
- Se corrigieron dos enlaces del README que apuntaban a archivos de requisitos inexistentes.
- Se abrió el PR [#59](https://github.com/hermensdiaz/Redise-o-de-Ven-al-Centro-y-Gana/pull/59) hacia `main`, que después se cerró sin fusionar.
