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
  Resolvemos primero $(z + x') = (0 + 1) = 1$             <br>
  Luego resolvemos $y \cdot 1 = 1 \cdot 1 = 1$            <br>
  Por último $x + 1 = 1$, luego el resultado final es 1.  <br>

  b) $[x y z] = [1 1 0]$, <br>
  Resolvemos primero $(z + x') = (1 + 1) = 1$             <br>
  Luego resolvemos $y \cdot 1 = 1 \cdot 1 = 1$            <br>
  Por último $x + 1 = 1$, luego el resultado final es 1.  <br>

  c) $[x y z] = [0 1 1]$, <br>
  Resolvemos primero $(z + x') = (0 + 0) = 0$                     <br>
  Luego resolvemos $y \cdot 0 = 1 \cdot 0 = 0$                    <br>
  Por último $x + 0 = 0 + 0 = 0$, luego el resultado final es 0.  <br>


### 1.3 Representación de funciones lógicas