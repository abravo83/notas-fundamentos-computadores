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
La segunda es verdadera sólo si una de las dos es verdadera pero no ambas.
La tercera es verdadera si su frase de entrada es falsa.

Por eso a la función $g_{1}$ se le denomina AND, a $g_{7}$ OR y a $f_{2}$ NOT.

Entonces, los circuitos lógicos se contruyen a partir de los mimos fundamentos de la lógica y, por tanto, vamos a estudiarlos.

**1.2 Álgebra de Boole**

