# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

- **Hablá siempre en español** con el usuario (chat, lecciones, explicaciones).
- Esto **no es un proyecto de código**: es un workspace de aprendizaje manejado por el skill `/teach`. No hay build, tests ni lint.
- El manual operativo es `.agents/skills/teach/SKILL.md`. Seguilo. Los formatos de cada archivo de estado están en los `*-FORMAT.md` de esa misma carpeta; leé el que corresponda antes de escribir.
- **Es multi-tema.** El workspace es un hub que puede tener varios temas independientes (incluso no relacionados entre sí). Cada tema es una carpeta autocontenida en `topics/<slug>/` con su PROPIO estado; no se comparte estado entre temas.
- **Estructura:**
  - Raíz: `index.html` (la HOME: tarjetas por tema con nº de lecciones; su array `TOPICS` es la fuente de verdad, mantenelo al día), `NOTES.md` (preferencias GLOBALES del aprendiz, valen para todos los temas).
  - Por tema (`topics/<slug>/`): `MISSION.md` (el porqué de ESE tema; brújula), `RESOURCES.md` (fuentes), `GLOSSARY.md` (terminología), `NOTES.md` (plan del tema), `learning-records/NNNN-slug.md`, `lessons/NNNN-slug.html`, `reference/*.html`.
  - **Numeración por tema:** lecciones y learning-records arrancan en `0001` dentro de cada tema. La primera lección de un tema nuevo es la 1, no continúa la de otro tema.
- Primer paso ante un pedido: definí a qué **tema** pertenece (existente o nuevo). Tema nuevo → preguntá el porqué (misión) ANTES de crear lecciones, creá `topics/<slug>/`, registralo en `index.html` y recién ahí hacé la lección `0001`.
- Principios clave: anclá todo a la `MISSION.md` del tema (si falta o es vaga, preguntá el porqué antes de crear lecciones); no confíes en tu conocimiento de memoria, sacá el contenido de la `RESOURCES.md` del tema con citas; cada lección enseña UNA cosa y es un HTML autocontenido; enseñá en la zona de desarrollo próximo (leé los `learning-records/` del tema); al crear/borrar temas o lecciones, actualizá el array `TOPICS` de `index.html`.
