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



