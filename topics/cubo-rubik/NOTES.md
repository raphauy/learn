# NOTES — Cubo de Rubik (plan del tema)

Notas específicas de ESTE tema. Las preferencias de la persona (español, dato/evidencia, RON por
minuto) están en el `NOTES.md` global de la raíz.

## Perfil del aprendiz en este tema
- **Nivel: cero absoluto.** Nunca armó el cubo. No dar por sabido NADA (ni siquiera girar sin
  desarmar mentalmente lo hecho).
- **Tiene cubo 3x3 físico** → cada lección puede y debe pedir práctica en mano con feedback inmediato.
- **Misión:** armarlo **siempre, de memoria**; entender el porqué; arco largo hacia **CFOP/velocidad**.

## Estrategia de enseñanza
- El norte es un método **capa por capa** confiable (fuente: J Perm 3x3), enseñado **una etapa por
  lección** con win tangible y auto-verificable cada vez.
- Pelearle a la memorización loro: en cada algoritmo, dar el **por qué** (qué pieza mueve, por qué
  no rompe lo hecho). Eso sirve a "entenderlo" y prepara la migración a CFOP.
- Cerrar cada etapa con un mini-check en mano y, al completar el método, una **hoja de referencia**
  (`reference/`) con todos los algoritmos para consulta rápida.

## Roadmap tentativo (capa por capa → CFOP)
1. ✅ **0001 — Anatomía + notación** (mental model: 20 piezas, centros fijos; idioma R U F…; sexy move).
2. ✅ **0002 — La cruz blanca** (método margarita/daisy; cruz EMPAREJADA con centros; usa F2 y U).
3. ✅ **0003 — Primera capa: esquinas** (trigger R U R' U' repetido; posicionar por brújula; "confiar en el algoritmo").
4. ✅ **0004 — Segunda capa: aristas** (regla "sin amarillo"; T invertida; algoritmos espejo der `U R U' R' U' F' U F` / izq `U' L' U L U F U' F'`; caso arista atascada).
5. ✅ **0005 — Cruz amarilla** (orientar aristas ULT: `F R U R' U' F'` = sexy en sándwich; leer punto/L/línea; ignorar esquinas; aún NO empareja con centros).
6. ✅ **0006 — Emparejar la cruz amarilla** (permutar aristas ULT: girar U p/ 2 coincidan; `R U R' U R U2 R' U` = Sune, con emparejadas atrás+derecha; casos adyacentes/opuestas/ninguna).
7. ✅ **0007 — Ubicar esquinas** (permutar esquinas ULT: reconocer esquina en su vértice s/importar giro; ancla en frente-derecha + `U R U' L' U R' U' L` cicla las otras 3; caso 0 correctas; queda "caótico" pero ubicado).
8. ✅ **0008 — Orientar esquinas / resolver** (`R' D' R D` 2 o 4 veces s/esquina en frente-derecha-arriba, amarillo arriba; solo `U` entre esquinas; máximo acto de fe; verificado: orden 6, rota 120° cada 2 pasadas). **MÉTODO COMPLETO.**
9. ✅ **Hoja de referencia** creada: `reference/metodo-principiante.html` (los 7 algoritmos en una página). Registrada en `index.html` (refs).
10. **Hito pendiente:** que resuelva el cubo **entero de memoria** varias veces, fluido, sin la hoja. Recién ahí cronometrar sin presión.
11. **Puente a CFOP:** finger tricks, F2L intuitivo, luego OLL/PLL de a poco (fuente: J Perm CFOP). No arrancar hasta que el método de memoria esté sólido (J Perm: no apurar cosas nuevas).

## Fricciones observadas
- **0007 (ubicar esquinas):** el aprendiz se trabó ("lo hice 3 veces y no anda"). Causa dupla, no bug de la
  lección (algoritmo `U R U' L' U R' U' L` verificado por simulación: fija UFR, cicla las otras 3, orden 3):
  (a) el **orden 3** — aplicarlo 3× con el mismo agarre vuelve al inicio; (b) la **cara `L`** casi no se usó
  antes y `L/L'` al revés desordena todo. Reforzado en la lección con dos avisos. **Para 0008 y futuras:**
  cuando un algoritmo use `L`/`B` o tenga orden bajo, avisar explícitamente de ambas trampas.

## Pendientes / ideas
- Buscar una fuente en español de alta confianza para citar (ver Gaps en RESOURCES.md).
- Cuando llegue F2L, considerar una `reference/` visual de casos.
- Confirmar tipo/estado del cubo si en algún momento aparece fricción de velocidad (¿es de núcleo
  moderno o uno viejo duro?). No urgente: para armar de memoria cualquier cubo sirve.
