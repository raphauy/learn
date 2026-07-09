# Ubica las esquinas de la última capa (y aprende a depurar un algoritmo)

El 2026-07-08 el aprendiz completó la Lección 0007: tiene **las 4 esquinas en su vértice**, quedan 2
torcidas (estado esperado, previo al paso final). Evidencia: reporte propio ("ahora tengo los 4
vértices en su lugar, hay 2 que están rotados").

**Fricción y cómo se resolvió (importante):** primero se trabó ("lo hice 3 veces y no anda"). El
algoritmo y el hold eran correctos (verificado por simulación con pycuber: `U R U' L' U R' U' L` fija
UFR y cicla las otras 3, orden 3). Causa real: **estaba ejecutando mal la `L`** (cara casi no usada
antes). Lo diagnosticó y corrigió él tras el refuerzo de la lección.

**Qué quedó demostrado:**
- Permuta las esquinas de la última capa: reconoce la esquina en su vértice (3 colores, sin importar
  giro), ancla en frente-derecha y aplica el ciclo.
- **Aprendió a depurar**: entendió la trampa del "orden 3" (repetir vuelve al inicio) y afinó la
  ejecución de una cara nueva. Skill transversal valioso para armar de memoria.

**Por qué importa:** está a **un paso** del cubo resuelto. Piso nuevo: listo para la última etapa,
**orientar esquinas (0008, `R' D' R D`)**, tras la cual completa el método. Ojo: ese paso es el de
mayor "acto de fe" (el cubo parece destruirse); anticiparlo. Ver [[MISSION.md]].
