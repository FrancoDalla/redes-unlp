<h1>Ejercicio 6</h1>
<h3>
6. Describa para qué se utilizan los siguientes tipos de registros de DNS:
<ol>
<li>a. A</li> 
<li>b. MX</li> 
<li>c. PTR </li>
<li>d. AAAA </li>
<li>e. SR</li>
<li>f. NS</li>
<li>g. CNAME</li>
<li>h. SOA</li>
<li>i. TXT</li>
</ol>
</h3>

<h3>REGISTRO A </h3>
Los registros A indican la dirección IPv4 de un determinado dominio.

Siguen la siguiente estructura:
[nombre] IN A [IPv4]

Un ejemplo utilizando el comando dig:

google.com.		20	IN	A	216.58.202.78

nombre          ttl     tipo   ip 


<h3>REGISTRO MX</h3>
Los registros MX dirigen el correo electrónico a un servidor de correo. Este indica como deben dirigirse los mensajes
de acuerdo con el protocolo de transferencia simple de correo (SMTP)

Siguen la siguiente estructura:
[nombre] IN MX [prioridad] [nombre]

Un ejemplo utilizando el comando dig:
google.com.		300	IN	MX	10 smtp.google.com.

nombre          ttl    tipo prioridad nombre


<h3>REGISTRO PTR</h3>
Son lo contrario a un registro A que proporciona la ip asociada a un nombre de dominio.
Estos se utilizan en busquedas de DNS inverso cuando un usuario intenta acceder a un nombre de dominio,
se hace una busqueda dns inverso.

Un ejemplo utilizando el comando dig:
8.8.8.8.in-addr.arpa.	86400	IN	PTR	dns.google.

ip                      ttl          tipo nombre

<h3>REGISTRO AAAA</h3>
Los registros AAAA indican la dirección IPv6 de un determinado dominio.

Siguen la siguiente estructura:
[nombre] IN AAAA [ipv6] 

Un ejemplo utilizando el comando dig:
google.com.		236	IN	AAAA	2800:3f0:4002:810::200e

nombre          ttl     tipo    direccion ipv6

<h3>REGISTRO SR</h3>

<h3>REGISTRO NS</h3>

<h3>REGISTRO CNAME</h3>

<h3>REGISTRO SOA</h3>

<h3>REGISTRO TXT</h3>


