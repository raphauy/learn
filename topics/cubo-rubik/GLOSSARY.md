# Cubo de Rubik (3x3) — Glossary

Terminología canónica para armar el 3x3. Todas las lecciones del tema usan estos términos.
Crece a medida que el aprendiz demuestra que domina cada concepto.

## Anatomía

**Pieza (cubie)**:
Cada bloque físico del cubo. Un 3x3 tiene 26 piezas, pero solo **20 se mueven**: lo que gira
son piezas enteras, no stickers ni caras sueltas.
_Avoid_: sticker, cuadradito, color suelto

**Centro**:
Pieza de **1 solo sticker**, una por cara (6 en total). **No se mueve nunca** respecto a las
otras: define el color de esa cara y es la brújula para leer el cubo.
_Avoid_: cara

**Arista (edge)**:
Pieza de **2 stickers** (12 en total), en el medio de cada borde. Vive entre dos centros.
_Avoid_: lado, borde

**Esquina (corner)**:
Pieza de **3 stickers** (8 en total), en los vértices del cubo.
_Avoid_: punta, vértice

**Cara**:
Una de las 6 vistas del cubo (la que mirás de frente). El color de una cara resuelta lo dicta su
centro. No confundir con "pieza".

## Notación

**Notación**:
El idioma para escribir instrucciones de giro. Las 6 letras base son **U** (Up/arriba),
**D** (Down/abajo), **R** (Right/derecha), **L** (Left/izquierda), **F** (Front/frente),
**B** (Back/atrás). Una letra sola = girar **esa cara 90° en sentido horario**, mirándola de frente.
_Avoid_: fórmula, código

**Prime ( ' )**:
El apóstrofo tras una letra invierte el giro: **antihorario** (90° en sentido contrario).
Ej.: `R'` = derecha antihorario. Se lee "prime".
_Avoid_: invertido, al revés, la comita

**Doble ( 2 )**:
El número 2 tras una letra = **media vuelta** (180°). Ej.: `U2`. Da igual para qué lado.
_Avoid_: dos veces

**Algoritmo**:
Una secuencia fija de giros, escrita en notación, que produce un efecto conocido y **repetible**
en el cubo. La base del "de memoria": el cubo es determinista, no azar.
_Avoid_: truco, movida, combo

**Sexy move**:
El algoritmo más usado del método: **R U R' U'**. Repetido 6 veces devuelve el cubo a como estaba
(demuestra que los algoritmos son cíclicos y deterministas).
_Avoid_: el movimiento ese

## Primera capa

**Emparejar (una pieza con su centro)**:
Ubicar una pieza de modo que su(s) color(es) de costado coincidan con el/los **centro(s)** de esa(s)
cara(s). Es "usar la brújula": el criterio de que una pieza está en su casa.
_Avoid_: alinear a ojo, que quede lindo

**Cruz blanca**:
Las 4 aristas blancas puestas alrededor del centro blanco y **emparejadas** con los centros
laterales. Primer paso real del método. Una cruz blanca NO emparejada no cuenta.
_Avoid_: cruz (a secas)

**Margarita (daisy)**:
Técnica de principiante para la cruz: se arman los 4 pétalos blancos alrededor del centro **amarillo**
(arriba) y se bajan de a uno con una vuelta doble (`F2`), emparejando con cada centro.
_Avoid_: la flor

## Método (para más adelante)

**Método principiante (capa por capa / LBL)**:
Resolver el cubo en capas: primera capa → segunda capa → última capa. El método con el que
arrancamos. _Avoid_: método fácil

**CFOP**:
Método avanzado de velocidad (Cross, F2L, OLL, PLL) — el destino del tema. Se introduce recién
cuando la resolución de memoria esté sólida.
