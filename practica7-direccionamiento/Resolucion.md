<h1>Ejercicio 1</h1>
<h3>¿Qué servicios presta la capa de red? ¿Cuál es la PDU en esta capa? ¿Qué dispositivo
es considerado sólo de la capa de red?</h3>

La capa de red de internet es responsable de trasladar los paquetes de la capa de red, conocidos como datagramas, de un host a otro.
La capa de transporte de un host origen pasa a un segmento de la capa de transporte y una dirección de destino a la capa de red, luego esta capa suministra el segmento al destino.
Esta capa incluye al conocido protocolo IP, que define los campos del datagrama asi como la forma en que actúan los sistemas terminales y los routers sobre estos campos.
Existe un único protocolo IP y los componentes dei nternet que tienen una capa de red deben ejecutar el protocolo Ip. 
También esta capa contiene protocolos de enrutamiento.
Esta capa se encarga de enrutamiento y direccioanmiento lógico.
Se considera que el router es un dispositivo exclusivo de la capa de Red. Ya que interconecta distintas redes, toma decisiones basadas en direcciones IP y ejecuta protocolos de enrutamiento.

<h1>Ejercicio 2</h1>
<h3>¿Por qué se lo considera un protocolo de mejor esfuerzo? ¿La pregunta habla de IP?</h3>

El protocolo IP es el protocolo de la capa de red. Este protocolo proporciona una comunicación lógica entre hosts.
El modelo de servicio de IP es el de un serviciode entrega de mejor esfuerzo. Esto quiere decir que
IP hace todo lo que puede por entregar los segmentos entre los hosts que se estan comunicando.
Pero no garantiza que los segmentos se entreguen en orden y no garantiza la integridad de los datos contenidos en los segmentos.
(por esta razón también se dice que IP es un servicio no fiable)

<h1>Ejercicio 3</h1>
<h3>¿Cuántas redes clase A, B y C hay? ¿Cuántos hosts como máximo pueden tener cada
una?</h3>

Antes de que se adoptara el enrutamiento CIDR, la parte de red de una dirección IP estaba restringida a longitudes de
8, 16 y 24 bits, este esquema era un esquema de direccionamiento por clases ya que estos tipos de direcciones IP se denominaban:

A -> 8 bits (/8)
B -> 16 bits (/16)
C -> 24 bits (/24)

la clase A utiliza 

8 bits de red  | 24 bits local


es posible 128 direcciones de red y 16.777.216 direcciones locales posibles(hosts)

la clase B utiliza

16 bits de red | 16 bits local 

es posible 16.384 direcciones de red y 65.536 direcciones locales (hosts)


La clase C utiliza 

24 bits de red | 8 bits local 

es posible 2.097.152 direcciones de red y 256 direcciones locales (hosts)

<h1>Ejercicio 4</h1>
<h3>¿Qué son las subredes? ¿Por qué es importante siempre especificar la máscara de
subred asociada?</h3>






<h1>División en subredes</h1>
<h1>Ejercicio 6</h1>
a.¿De que clase de red es la dirección dada (a, b o c)?
b.¿Cual es la dirección de subred?
c.¿Cual es la cantidad maxima de hosts que pueden estar en esa subred?
d.¿Cual es la dirección de broadcast de esa subred?
e.¿Cual es el rango de direcciones ip válidas dentro de la subred?

<h1>172.16.58.223/26</h1>


a. La red es de clase B 
b. [VER EN CUADERNO] la direccion de subred es 172.16.58.192 
c. la cantidad maxima de hosts es 2^6 - 2, osea 62 hosts.
d. 172.16.58.255
e. 172.16.58.193 - 172.16.58.254


<h1>163.10.5.49/27</h1>

a. la red es clase B 
b. [VER EN CUADERNO] la dirección de subred es 163.10.5.32
c. cantidad maxima de hosts es de 2^5 -2, osea 30 bits
d. 163.10.5.63
e. 163.10.5.33 - 163.10.5.62

<h1>128.10.0.0/23</h1>

a. La red es clase B
b. [VER EN CUADERNO] la dirección de subred es 128.10.1.0
c. la cantidad maxima de hosts es: 2^9 - 2, osea 510 hosts
d. 128.10.1.255 es la direccion de broadcast
e. 128.10.0.1 - 128.10.1.254

<h1>10.1.0.0/24</h1>
a. La red es clase A
b. [VER EN CUADERNO] la dirección de subred es 10.1.0.0
c. la cantidad maxima de hosts es 2^8 - 2, osea 254 hosts.
d. 10.1.0.255
e. 10.1.0.1 - 10.1.0.254

<h1>8.40.11.179/12</h1>
a. red clase A 
b. [VER EN CUADERNO] 8.32.0.0
c. la cantidad maxima de hosts es de 2^20 -2, osea 1048574
d. x
e.x

<h1>Ejercicio 7</h1>
<h3>Su organización cuenta con la dirección 128.50.10.0. Indique:
a. ¿Es una dirección de red o de host?
b. Clase a la que pertenece y máscara de clase.
c. Cantidad de hosts posibles.
d. Se necesitan crear, al menos, 513 subredes. Indique:
    i.Máscara necesaria.
    ii.Cantidad de redes asignables.
    iii.Cantidad de hosts por subred.
    iv.Dirección de la subred 710.
    v.Dirección de broadcast de la subred 710.
</h3>

Asumiendo mascara /16 por la clase de la dirección

a.
Es una dirección de host.

b.
Pertenece a la clase b, la mascara seria /16

c. los hosts posibles son 2^16 - 2, osea 65534 hosts

d.
    i. se necesitara sacar 10 bits para esto, ya que 2^10 permite lo requerido.
    ii. se tendran 2^10 redes asignables.
    iii. por cada red se tendran 2^6 hosts - 2 asignables
    iv. x
    v. x


<h1>ejercicio 8</h1>
<h3>8. Si usted estuviese a cargo de la administración del bloque IP 195.200.45.0/24
a. ¿Qué máscara utilizaría si necesita definir al menos 9 subredes?
b. Indique la dirección de subred de las primeras 9 subredes.
c. Seleccione una e indique dirección de broadcast y rango de direcciones asignables
en esa subred
</h3>

a. la mascara seria /28. Ya que para representar las 9 subredes se requerirían 4 bits extra. 
b. [VER CUADERNO]
c. [VER CUADERNO]


<h1>Ejercicio 9</h1>
<h3>
Dado el siguiente grafico [ver grafico en practica]
a. Verifique si es correcta la asignación de direcciones IP y, en caso de no serlo,
modifique la misma para que lo sea.
b. ¿Cuántos bits se tomaron para hacer subredes en la red 10.0.10.0/24? ¿Cuántas
subredes se podrían generar?
c. Para cada una de las redes utilizadas indique si son públicas o privadas
</h3>

a. hay dos direcciones IP incorrectas en el grafico 172.26.22.3, que corresponde a la dirección de broadcast de
172.26.22.0/30.
y la dirección de ip 172.17.10.17, que es una dirección fuera de rango para 172.17.10.0/28

b. La dirección IP 10.0.10.0/24 es una dirección de clase A. Por lo que esta usaba en un inicio mascara /8 
(u 8 bits para representar la red) por lo que tomaron 16 bits para esta red.
Se podrían generar 2^16 subredes. 

c.

X

<h1>CIDR</h1>

<h1>Ejercicio 10</h1>
<h3>¿Qué es CIDR (Class Interdomain routing)? ¿Por qué resulta útil?</h3>
La estrategia de asignación de direcciones en Internet se conoce como enrutamiento entre dominios sin clase, o 
CIDR (Classless Interdomain Routing). CIDR generaliza la noción de direccionamiento de subred.


<h1>Ejercicio 11</h1>
<h3>
¿Cómo publicaría un router las siguientes redes si se aplica CIDR?
a. 198.10.1.0/24
b. 198.10.0.0/24
c. 198.10.3.0/24
d. 198.10.2.0/24
</h3> 	

a. 198.10.1.0/24 ->numero CIDR
	contempla las direcciones desde 198.10.1.0/24 hasta 198.10.3.0/24

<h1>Ejercicio 12</h1>
<h3>Listar las redes involucradas en los siguientes bloques CIDR</h3>
● 200.56.168.0/21
● 195.24.0.0/13
● 195.24/13

Para 200.56.168.0/21
las redes implicadas irian 
desde 200.56.168.0/24 hasta 200.56.175/24

para 195.24.0.0/13
las redes implicadas irian 
desde 195.24.0.0/24 hasta 195.31.255.255 

[Ver cuaderno para ver el paso a paso]


<h1>VLSM</h1>

<h1>Ejercicio 14</h1>
<h3>¿Que es y para que se usa VLSM?</h3>
La mascara de subred de tamaño variable o VLSM(Variable Lenght Subnet Mask) es una de las soluciones que se implementaron
para evitar el agotamiento de direcciones IP en IPv4. 
También descentraliza las redes y de esta forma ayuda a tener redes más seguras y jerárquicas.

<h1>Ejercicio 15</h1>
<h3>Describa, con sus palabras, el mecanismo para dividir subredes utilizando VLSM.</h3>
Primero se comienza calculando la mascara de forma tal que pueda representar la subred, o subredes, de mayor cantidad de hosts.
luego tomando los bits que se encuentran entre los limites de la mascara original y la mascara nueva para armar las siguientes subredes.


