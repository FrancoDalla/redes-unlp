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

