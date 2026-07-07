# Mi taller de aprendizaje

Workspace personal de aprendizaje manejado con el skill [`/teach`](.agents/skills/teach/SKILL.md)
de Claude Code. **No es un proyecto de código** (no hay build, tests ni lint): es un hub de temas,
cada uno con sus lecciones interactivas en HTML autocontenido.

## Cómo usarlo

Abrí la home en el navegador y elegí el tema del día:

```bash
xdg-open index.html      # Linux
# open index.html        # macOS
```

La home muestra una tarjeta por tema (con su cantidad de lecciones); entrás a un tema y elegís
la lección. Cada lección se abre directamente en el navegador.

## Estructura

- `index.html` — la **home**: hub con las tarjetas de cada tema. Su array `TOPICS` es la fuente
  de verdad de lo que se muestra.
- `NOTES.md` — preferencias globales del aprendiz (valen para todos los temas).
- `topics/<tema>/` — cada tema es **autocontenido**, con su propio:
  - `MISSION.md` (el porqué), `RESOURCES.md` (fuentes), `GLOSSARY.md` (terminología), `NOTES.md`
    (plan del tema)
  - `lessons/NNNN-*.html` — las lecciones (numeradas desde `0001` **dentro de cada tema**)
  - `learning-records/NNNN-*.md` — qué se fue aprendiendo
  - `reference/*.html` — chuletas / material de consulta rápida

## Temas actuales

| Tema | Carpeta |
|---|---|
| 🏋️ Preparación física / lesiones en tenis | `topics/tenis-lesiones/` |
| 🧠 Táctica de partido | `topics/tenis-tactica/` |

Para agregar un tema o una lección, se lo pido al agente con `/teach` — mantiene las carpetas
y la home al día.
