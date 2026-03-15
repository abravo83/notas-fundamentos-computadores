# Tema 3: Los circuitos lógicos combinacionales

## Introducción

Los computadores son máquinas que se construyen a partir de dispositivos electrónicos básicos interconectados de una forma concreta. Estos dispositivos constituyen los ladrillos con los que se contruye el computador.

En este tema vamos a estudiar los dispositivos electrónicos básicos: **las puertas lógicas** y los **bloques lógicos**. Juntos forman los **circuitos lógicos**. Estos manipulan señales electrónicas que les llegan y como resultado dan salida a otras señales electrónicas.

Entre los **circuitos lógicos** podemos distiguir dos tipos:

1) **Circuitos combinacionales**: el valor de salida depende del valor de las señales de entrada de ese mismo momento.
2) **Circuitos secuenciales**: el valor de salida depende de los valores que llegaron a la entrada en otro momento. Por eso, un requisito de este tipo en contar con capacidad de memoria.

En este tema vamos a ver los **circuitos combinaciones** además de las puertas lógicas y los bloques lógicos básicos.

## 1. Fundamentos de la electrónica digital

### 1.1. Circuitos, señales y  funciones lógicas.

Circuito: Sistema formado por un cierto número de señales de entrada, de un conjunto de dispositivos electrónicos que realizan operaciones sobre esas señales de entrada y como resultado generan un determinado número de señales de salida.

Podemos por tanto entender a esas señales de salida como funciones de las señales de entrada, y decimos que los componentes electrónicos computan estas funciones.

Tenemos en los circuitos electrónicos dos valores de tensión posibles: tensión alta o de alimentación y tensión baja, que vamos a identificar respectivamente con los símbolos 1 y 0 respectivamente.

A las señales que pueden tomar valores 0 y 1 exclusivamente las denominamos **señales lógicas o binarias**. 

Las funciones que computan un circuito lógica las denominamos **funciones lógicas**.

Si imaginamos un circuito con una señal de entrada (que llamaremos *x*), un dispositivo electrónico y una señal de salida (que llamaremos *z*) solo tenemos cuatro dispositivos diferentes que pueden interconectar x y z:

* Un dispositivo que haga que la salida *z* siempre valga 0.
* Un dispositivo que haga que la salida *z* siempre valga lo que valga *x*.
* Un dispositivo que haga que la salida *z* siempre valga lo contrario que *x*
* Un dispositivo que haga que la salida *z* siempre valga 1.

Por tanto decimos que sólo hay 4 funciones lógicas cuando hay una sóla variable de entrada:

$z = f_{0}(x) = 0$ : función constante 0.<br/>
$z = f_{1}(x) = x$ : función identidad.<br/>
$z = f_{2}(x) = x^{'}$ : función contrario.<br/>
$z = f_{3}(x) = 1$ : función constante 1.<br/>

Si ahora imaginamos otro circuito que contenga dos señales de entrada (a los que llamaremos *x* y *y*) y una señal de salida (a la que llamaremos *z*), tenemos en este caso diecisies funciones diferentes:

| Función lógica    | $x=0, y=0$     | $x=0, y=1$ | $x=1, y=0$ | $x=1, y=1$ |
| :---------------- | :------------: | :--------: | :--------: | :--------: |
| $z = g_{0}(x,y)$  | 0              | 0          | 0          | 0          |
| $z = g_{1}(x,y)$  | 0              | 0          | 0          | 1          |
| $z = g_{2}(x,y)$  | 0              | 0          | 1          | 0          |
| $z = g_{3}(x,y)$  | 0              | 0          | 1          | 1          |
| $z = g_{4}(x,y)$  | 0              | 1          | 0          | 0          |
| $z = g_{5}(x,y)$  | 0              | 1          | 0          | 1          |
| $z = g_{6}(x,y)$  | 0              | 1          | 1          | 0          |
| $z = g_{7}(x,y)$  | 0              | 1          | 1          | 1          |
| $z = g_{8}(x,y)$  | 1              | 0          | 0          | 0          |
| $z = g_{9}(x,y)$  | 1              | 0          | 0          | 1          |
| $z = g_{10}(x,y)$ | 1              | 0          | 1          | 0          |
| $z = g_{11}(x,y)$ | 1              | 0          | 1          | 1          |
| $z = g_{12}(x,y)$ | 1              | 1          | 0          | 0          |
| $z = g_{13}(x,y)$ | 1              | 1          | 0          | 1          |
| $z = g_{14}(x,y)$ | 1              | 1          | 1          | 0          |
| $z = g_{15}(x,y)$ | 1              | 1          | 1          | 1          |

Por tanto, tenemos disponibles 4 + 16 dispositivos electrónicos con una o dos entradas, pero, en la práctica sólo se contruyen 3, porque los demás se pueden derivar de esos tres: $f_{2}$, $g_{1}$ y $g_{7}$

Ya estamos viendo que: 
> hay una correspondencia entre los elementos de un circuito lógico y la lógica intuitiva. Es por esta razón por lo que denominamos a estos circuitos como "circuitos lógicos".

| Lógica       | Circuitos lógicos |
| :----:       | :---------------: |
| falso        | 0                 |
| verdadero    | 1                 |
| conjunción y | función $g_{1}$   |
| conjunción o | función $g_{7}$   |
| partícula no | función $f_{2}$   |

Podemos decir que si tenemos dos frases (las señales de entrada): "Juan estudia química", "María estudia filosofía", podemos construir las siguiente frases:

Juan estudia química **y** María estudia filosofía.
Juan estudia química **o** María estudia filosofía.
Juan **no** estudia química.

La primera sólo es verdadera si ambas frases de entrada son verdaderas.
La segunda es verdadera si cualquiera de las dos es verdadera (o ambas).
La tercera es verdadera si su frase de entrada es falsa.

Por eso a la función $g_{1}$ se le denomina AND, a $g_{7}$ OR y a $f_{2}$ NOT.

Entonces, los circuitos lógicos se contruyen a partir de los mismos fundamentos de la lógica y, por tanto, vamos a estudiarlos.

**1.2 Álgebra de Boole**

> Es una entidad matemática formada por un conjunto que contien dos elementos (verdadero y falso), operaciones básicas sobre estos elementos y una lista de axiomas que definen las propiedades que cumplen las operaciones.

Las operaciones booleanas lógicas son:

> La **negación o complementación o NOT**: Se corresponde con la partícula *no* y se representa con una comilla tras una variable o conjunto de ellas. Con $x'$ representamos la negación de $x$, y lo leemos como "no $x$".

| x   | x'  |
| :-: | :-: |
| 0   | 1   |
| 1   | 0   |

> El **producto lógico o AND**, se corresponde con la conjunción (*y*) y se representa con el símbolo $\cdot$.

| x , y | x $\cdot$ y |
| :-:   | :---------: |
| 0 , 0 | 0           |
| 0 , 1 | 0           |
| 1 , 0 | 0           |
| 1 , 1 | 1           |

> La **suma lógica u OR**, que corresponde a la conjunción *o* y se representa con el símbolo (+). La expresión "x + y" denota *la suma lógica* de las variables x e y, y se lee "x o y".


| x , y | x + y       |
| :-:   | :---------: |
| 0 , 0 | 0           |
| 0 , 1 | 1           |
| 1 , 0 | 1           |
| 1 , 1 | 1           |

> **AXIOMAS DE LAS OPERACIONES BOOLEANAS**
> 
> Siendo x, y y z variables lógicas. Se cumple que:

> a) Propiedad conmutativa                        <br>
> $x + y = y + x$                                 <br>
> $x \cdot y = y \cdot x$                         <br>
                                                  <br>
                                                  <br>
> b) Propiedad asociativa                         <br>
>$x + (y + z) = (x + y) + z$                      <br>
>$x \cdot (y \cdot z) = (x \cdot y) \cdot z$      <br>
                                                  <br>
                                                  <br>
> c) Propiedad distributiva:
>$x \cdot (y + z) = x \cdot y + x \cdot z$        <br>
>$x + (y \cdot z) = (x + y) \cdot (x + z)$        <br>
                                                  <br>
                                                  <br>

> d) Elementos neutros                            <br>
> $x + 0  = x$                                    <br>
> $x \cdot 1 = x$                                 <br>
                                                  <br>
                                                  <br>
> e) Complementación. Para cualquier x se cumple  <br>
> $x + x' = 1$                                    <br>
> $x \cdot x' = 0$                                <br>
                                                  <br>
                                                  <br>
A partir de esto axiomas podemos demostrar una serie de leyes o teoremas que son muy útiles a la hora de trabajar con expresiones algebraicas booleanas.

**Teoremas del álgebra de boole**

Siendo x, y y z variables lógicas, se cumplen las siguientes leyes:

1) **Principio de dualidad**

Toda identidad deducida a partir de los axiomas continua siendo cierta si las operaciones $+$ y $\cdot$ y los elementos 0 y 1 se intercambian en toda la expresión.

2) **Ley de idempotencia**

$x + x = x$     <br>
$x \cdot x = x$ <br>

3) **Ley de absorción**

$x + x \cdot y = x$       <br>
$x \cdot (x \cdot y) = x$ <br>

4) **Ley de dominancia**

$x + 1 = 1$
$x \cdot 0 = 0$

5) **Ley de involución**

$(x')' = x$

6) **Leyes de Morgan**

$(x + y)' = x' \cdot y'$ <br> 
$(x \cdot y)' = x' + y'$ <br>

La inversa de la suma lógica es el producto de las inversas.
La inversa del producto lógico es la suma de las inversas.

#### Actividades

1. Evaluad el valor de la expresión $x + y \cdot (z + x')$ para: <br>
  
  a) $[x y z] = [0 1 0]$, <br>
  Resolvemos primero $(z + x') = (0 + 1) = 1$                     <br>
  Luego resolvemos $y \cdot 1 = 1 \cdot 1 = 1$                    <br>
  Por último $x + 1 = 0 + 1 = 0$, luego el resultado final es 0.  <br>

  b) $[x y z] = [1 1 0]$, <br>
  Resolvemos primero $(z + x') = (1 + 1) = 1$                     <br>
  Luego resolvemos $y \cdot 1 = 1 \cdot 1 = 1$                    <br>
  Por último $x + 1 = 1 + 1 =1$, luego el resultado final es 1.  <br>

  c) $[x y z] = [0 1 1]$, <br>
  Resolvemos primero $(z + x') = (0 + 0) = 0$                     <br>
  Luego resolvemos $y \cdot 0 = 1 \cdot 0 = 0$                    <br>
  Por último $x + 0 = 0 + 0 = 0$, luego el resultado final es 0.  <br>


### 1.3 Representación de funciones lógicas

Hay varias formas de representar funciones lógicas. Nosotros vamos a usar dos: las **expresiones algebraicas** y las **tablas de verdad**.

#### 1.3.1 Expresiones algebraicas

> Se componen de variables lógicas; de elementos 0's y 1's; de operadores producto $(\cdot)$, suma $(+)$ y negación $(')$; y de los símbolos $(,)$ e $(=)$.

Con esos elementos podemos expresar cualquier función lógica:

$g_{4}(x,y) = x' \cdot y$

**Expresiones algebraicas equivalentes**: Decimos que dos expresiones algebraicas son equivalentes (expresan la misma función) si de una podemos derivar a la otra usando los axiomas y las leyes del álgebra de Boole.

> Al usar el operador $\cdot$, lo podemos omitir escribiendo el nombre de dos variables seguidas. Entonces se sobreentiende que ente ellas se da el producto lógico

$x_{1}' \cdot x_{0} + x_{2} \cdot x_{1}' \cdot x_{0}' = x_{1}' x_{0} + x_{2}  x_{1}' x_{0}'$

##### Actividades

4. Encontrad una expresión algebraica para las funciones $g_{1}, g_{3}, g_{6}, g_{7}$ y $g_{10}$ de la fig. 2

a)  
$g_{1}(x,y) = 0$ si $(x=0, y=0)$, <br>
$g_{1}(x,y) = 0$ si $(x=0, y=1)$, <br>
$g_{1}(x,y) = 0$ si $(x=1, y=0)$, <br>
$g_{1}(x,y) = 1$ si $(x=1, y=1)$, <br>

Una expresión algebraica equivalente es: $g_{1}(x,y) = xy$ <br> 

b)
$g_{3}(x,y) = 0$ si $(x=0, y=0)$, <br>
$g_{3}(x,y) = 0$ si $(x=0, y=1)$, <br>
$g_{3}(x,y) = 1$ si $(x=1, y=0)$, <br>
$g_{3}(x,y) = 1$ si $(x=1, y=1)$, <br>

Una expresión algebraica equivalente sería: xy + xy' = x

c)
$g_{6}(x,y) = 0$ si $(x=0, y=0)$, <br>
$g_{6}(x,y) = 1$ si $(x=0, y=1)$, <br>
$g_{6}(x,y) = 1$ si $(x=1, y=0)$, <br>
$g_{6}(x,y) = 0$ si $(x=1, y=1)$, <br>

Una expresión algebraica equivalente sería: $(x' + y) + (x + y')'$ <br>

d)
$g_{10}(x,y) = 1$ si $(x=0, y=0)$, <br>
$g_{10}(x,y) = 0$ si $(x=0, y=1)$, <br>
$g_{10}(x,y) = 1$ si $(x=1, y=0)$, <br>
$g_{10}(x,y) = 0$ si $(x=1, y=1)$, <br>

Una expresión algebraica equivalente sería: $(x' + y') + (x + y') = y'$ <br>

5. Encontrad una expresión más sencilla para esta función: $f = wx + xy’ + yz + xz’ + xy$. <br>

Entre los operadores podemos simplificar: xy' + xy = x(y' + y) = x por complementación de y' con y.

Quedando la expresión
$f = wx + yz + xz’ + x$.

Luego, como también se debe cumplir que $wx + x$, por la ley de absorción:
$wx + x = x$

Quedando la expresión después de esta simplificación:
$f = yz + xz’ + x$.

Si tenemos ahora en cuenta $xz’ + x$, por absorción $xz’ + x = x$

Quedando la expresión finalmente como:
$f = yz + x$.

6. Sea una función de tres variables x, y y z. Encontrad una expresión algebraica de la misma suponiendo que la función debe valer 1 cuando se cumpla alguna de las siguientes condiciones:

+ x = 1 o y = 0,
+ x = 0 y z = 1,
+ las tres variables valen 1.
- Para la primera condición: $(x + y')$
- Para la segunda condicón: $(x'z)$ 
- Para la tercera condición: $(xyz)$        

+ Combinando las tres: $(x + y') + (x'z) + (xyz)$   

7. Se dispone de dos cajas fuertes electrónicas, A y B. Cada una de éstas tiene una señal asociada, $x_{A}$ y $x_{B}$ respectivamente, que vale 1 cuando la caja está abierta y 0 cuando está cerrada. Se tiene también un interruptor general que tiene una señal asociada $i_{g}$, que vale 0 si el interruptor está cerrado y 1 si no lo está. Se quiere construir un sistema de alarma antirrobos, que generará una señal de salida s. Esta señal tiene que valer 1 cuando alguna caja fuerte esté abierta y el interruptor esté cerrado. Escribid la expresión algebraica de la función $s = f(x_{A}, x_{B}, i_{g})$.

- La señal vale 1 cuando $x_{A}$ o $x_{B}$ valen 1 y $i_{g}$ vale 0: s = $(x_{A} + x_{B}) \cdot i_{g}'$      <br>

8. Juan se ha examinado de tres asignaturas. Sus amigos han visto los resultados de los exámenes y le han comentado lo siguiente:– Has aprobado matemáticas o física, dice el primero.– Has suspendido química o matemáticas, dice el segundo.– Has aprobado sólo dos asignaturas, dice el tercero. Entendemos que la “o” de estas frases es exclusiva. Es decir, la primera frase se podría sustituir por “o bien has aprobado matemáticas y has suspendido física, o bien has suspendido matemáticas y has aprobado física”, y de manera similar con la segunda frase. 

- a) Escribid las expresiones algebraicas de las afirmaciones de cada uno de los amigos. 
- Si matemáticas es m, física es f y química es q:
- 1er amigo:  (mf' + m'f)
- 2o amigo:   (qm' + q'm)
- er amigo:   (mfq' + mf'q + m'fq)

- b) Utilizando los axiomas y teoremas del álgebra de Boole, deducid qué asignaturas ha aprobado Juan y cuál ha suspendido.

> Los 5 axiomas son:
> Propiedad conmutativa: $x + y = y + x$ junto con $xy = yx$
> Propiedad asociativa: $x + (y + z) = (x + y) + z$ junto con $x(yz) = (xy)z$
> Propiedad distributiva: $x(y + z) = xy + xz$ junto con $x + (yz) = (x + y)(x + z)$
> Elemento neutro: $x + 0 = x$ junto con $x \cdot 1 = x$
> Complementación: $x + x' = 1$ junto con $x \cdot x' = 0$

> Las 6 leyes o teoremas del álgebra de Boole son:
> 1) Principio o ley de dualidad:
> Cualquier identidad, deducida a partir de los axiomas, continúa siendo cierta si las operaciones + y $\cdot$ junto con los elementos 1 y 0 se intercambian en toda la expresión.

> 2) Principio o ley de idempotencia:
> $x + x = x$
> $x \cdot x = x$
> "El producto lógico o la suma lógica entre una variable y si misma es igual a esa variable"

> 3) Ley de absorción
> $x + x \cdot y = x$
> $x \cdot (x + y) = x$

> 4) Principio o ley de dominancia
> $x + 1 = 1$
> $x \cdot 0 = 0$

> 5) Ley de involución
> $(x')' = x$

> 6) Leyes de Morgan
> $(x + y)' = x' \cdot y'$
> $(xy)' = x' + y'$

De lo que dicen los tres amigos sabemos que: Se han aprobado dos, se ha suspendido o química o matemáticas combinando 2 y 3:

- 1er amigo:  (mf' + m'f)
- 2o amigo:   (qm' + q'm)
- er amigo:   (mfq' + mf'q + m'fq)

Si se han aprobado dos asignaturas y se ha suspendido matemáticas o química, significa que física se ha aprobado y de la primera deducimos haber suspendido matemáticas, luego también si se han aprobado dos y se ha aprobado matemáticas o física, significa que se ha suspendido matemáticas y aprobado química.

(qm' + q'm)(mfq' + mf'q + m'fq) =
(qm')(mfq' + mf'q + m'fq) + q'm(mfq' + mf'q + m'fq) =
(qm'mfq' + qm'mf'q + qm'm'fq) + (q'mmfq' + q'mmf'q + q'mm'fq) =
(0 + 0 + qm'f) + (q'mf + 0 + 0) =
qm'f + q'mf

Si combinamos el resultado con la expresión del primer amigo:

(mf' + m'f)(qm'f + q'mf) =
mf'(qm'f + q'mf) + m'f(qm'f + q'mf) =
(mf'qm'f) + (mf'q'mf) + (m'fqm'f) + (m'fq'mf) =
0         +   0       + (m'fq)    + 0         =
m'fq

Luego el resultado es que Matemáticas está suspensa y física y química están aprobadas.

#### 1.3.2 Tablas de verdad

> Una tabla de verdad expresa una función lógica especificando el valor que tiene la función para cada posible combinación de valores de las variables de entrada.

Tenemos a la izquierda una lista con todas las posibles combinaciones de valores que pueden tomar las variables de entrada y a la derecha el valor de la función para esa función y esos valores de entrada.

Cuando tenemos una función con $n$ variables de entrada, dado que una variable sólo puede tomar como valores 0 ó 1, las entradas pueden tomar $2^n$ combinaciones de valores diferentes. Es por eso que una tabla de verdad tendrá $n$ columnas y $n^2$ filas, mientras que a la derecha tendremos una columna con $2^n$ filas.

La convención a la hora de escribir los valores es usar *orden lexicográfico*, comenzando por los valores que son todo ceros e ir creciendo en el orden de los números naturales.

A la hora de colocar las variables en cada columna también tenemos algunas convenciones. La primera es que, cuando usamos una misma letra pero con subíndices para las diferentes variables, coloquemos la de mayor subíndice a la izquierda del todo y las restantes a su derecha:

$x_{2}, x_{1}, x_{0}$ <br>

Decimos entonces que esa variable es la **variable de más peso** mientras que la que se encuentra a la derecha del todo es la **variable de menos peso**.

Podemos usar una única tabla para el resultado de varias funciones lógicas. En ese caso se suele denominar a cada función con f y un subíndice, y el orden de colocación no está establecido. Se puede usar este y otro cualquiera

$f_{0}, f_{1}, f_{2}, ...$ <br>

