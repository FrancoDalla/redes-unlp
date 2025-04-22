<h1>Ejercicio 6</h1>
<h3>
6. Describa para qué se utilizan los siguientes tipos de registros de DNS:
<ol>
<li>a. A</li> 
<li>b. MX</li> 
<li>c. PTR </li>
<li>d. AAAA </li>
<li>e. SRV</li>
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
```
google.com.		20	IN	A	216.58.202.78

nombre          ttl     tipo   ip 
```

<h3>REGISTRO MX</h3>
Los registros MX dirigen el correo electrónico a un servidor de correo. Este indica como deben dirigirse los mensajes
de acuerdo con el protocolo de transferencia simple de correo (SMTP)

Siguen la siguiente estructura:
[nombre] IN MX [prioridad] [nombre]

Un ejemplo utilizando el comando dig:
```
google.com.		300	IN	MX	10 smtp.google.com.

nombre          ttl    tipo prioridad nombre
```

<h3>REGISTRO PTR</h3>
Son lo contrario a un registro A que proporciona la ip asociada a un nombre de dominio.
Estos se utilizan en busquedas de DNS inverso cuando un usuario intenta acceder a un nombre de dominio,
se hace una busqueda dns inverso.

Un ejemplo utilizando el comando dig:
```
8.8.8.8.in-addr.arpa.	86400	IN	PTR	dns.google.

ip                      ttl          tipo nombre
```

<h3>REGISTRO AAAA</h3>
Los registros AAAA indican la dirección IPv6 de un determinado dominio.

Siguen la siguiente estructura:
[nombre] IN AAAA [ipv6] 


Un ejemplo utilizando el comando dig:
```
google.com.		236	IN	AAAA	2800:3f0:4002:810::200e

nombre          ttl     tipo    direccion ipv6
```

<h3>REGISTRO SRV</h3>
Especifican un servidor y un puerto para servicios específicos.

La estructura de estos es mas compleja siguen lo siguiente:

[nombre_servicio] TLS IN SRV [prioridad][peso][nombre]

Un ejemplo utilizando dig:
```
_sip._udp.sip.antisip.com. 43200 IN	SRV	10 50 5060 sip.antisip.com.
_sip._udp.sip.antisip.com. 43200 IN	SRV	10 50 9090 sip.antisip.com.
```

<h3>REGISTRO NS</h3>
El registro NS(name server) indica que servidor DNS es autoritativo para un dominio (osea, que servidor contiene los registros DNS en si).
Basicamente estos dominios indican a donde ir para buscar la direccion IP de un domiio. 
Es común que un dominio tenga múltiples registros de NS.

La estructura es la siguiente:

[nombre]  TLS IN NS [nombre]

Ejemplo utilizando dig:
```
google.			21600	IN	NS	ns-tld4.charlestonroadregistry.com.
```

<h3>REGISTRO CNAME</h3>
El registro CNAME(canonical name) apunta, desde un dominio alias, a uno canónico.. Estos se utilizan en lugar de los registros A
cuando un dominio o subdominio es un alias a de otro dominio. Todos los registros CNAME deben apuntar a un dominio, nunca a una dirección IP.

estructura: 
[nombre] TLS IN CNAME [alias] 

Ejemplo con dig:
```
```

<h3>REGISTRO SOA</h3>
El registro SOA (Start of authority) almacena información importante sobre un dominio o una zona.
Tales como la dirección de correo del administrador, cuando se actualizó el dominio por última vez o 
cuanto debe esperar el servidor entre actualizaciones.
Todas las zonas DNS necesitan un registro SOA para cumplir las normas de la IETF. También son importantes
para las transferencias de zona.

Estructura(es un poco más compleja)
[nombre] 
[tipo]
[mname]
[rname]
[serie]
[actualizar]
[RETRY]
[TTL]

Ejemplo con dig:
```
.			3111	IN	SOA	a.root-servers.net. nstld.verisign-grs.com. 2025041500 1800 900 604800 86400

```

<h3>REGISTRO TXT</h3>
Permite a un administrador de dominios introducir texto en el DNS. Este se almacena en forma de una o más
cadenas entre comillas. Su origen se penso para ingresar información legible para humanos. Pero ahora también
se pueden agregar datos legibles por máquina. Un dominio puede tener muchos de estos.

Estructura:
[nombre] TLS IN TXT [valor]

<h1>Ejercicio 7</h1>
<h3>En internet un dominio suele tener más de un servidor DNS ¿Por qué cree que esto es asi?</h3>
Imagino que, la razón de esto, es para tener la carga distribuída y, ademas, ser redundante.

<h1>Ejercicio 8</h1>
<h3>Cuando un dominio cuenta con más de un servidor, uno de ellos es el primario (o master) y los demas son secundarios (o slaves) ¿Por qué esto es asi?</h3>
Esta es una forma de organizar los servidores para que se puedan configurar facilmente varios a la misma vez. El servidor primario 
es el que es configurado y los demás replican a este. De esta manera podemos realizar una sola vez una modificación al servidor para que esta luego este disponible en los demas de forma automatica.

<h1>Ejercicio 9</h1>
<h3>Explique brevemente en que consiste el mecanismo de transferencia de zona y cuál es su finalidad</h3>
La transferencia de zona es un mecanismo que utilizan los servidores de DNS para replicar la base de datos de un servidor maestro a uno o mas servidores DNS esclavos.
La finalidad es facilitar la labor de configurar multiples servidores, reduciendo la tarea a configurar uno solo para que sea replicado por los demas.
Si bien esto facilita las cosas, tiene también que incluirse y establecer una forma de que periodicamente los servidores esclavos consulten para confirmar que sus datos coinciden con el maestro.

<h1>Ejercicio 10</h1>
<h3>Imagine que usted es el administrador del dominio de DNS de la UNLP (unlp.edu.ar). A
su vez, cada facultad de la UNLP cuenta con un administrador que gestiona su propio
dominio (por ejemplo, en el caso de la Facultad de Informática se trata de info.unlp.edu.ar).
Suponga que se crea una nueva facultad, Facultad de Redes, cuyo dominio será
redes.unlp.edu.ar, y el administrador le indica que quiere poder manejar su propio dominio.
¿Qué debe hacer usted para que el administrador de la Facultad de Redes pueda gestionar
el dominio de forma independiente? (Pista: investigue en qué consiste la delegación de
dominios). Indicar qué registros de DNS se deberían agregar.</h3>

Ejemplo tomado de la teoría (delegación de autoridad)

unlp.edu.ar , queremos agregar la facultad de redes con dominio redes.unlp.edu.ar.

1 - hay que otorgar la autoridad sobre el dominio redes.unlp.edu.ar
2 - Ahi tendremos que agregar registros DNS para guíar a redes.unlp.edu.ar
	>Registro A y AAAA para guíar el nombre hacia la dirección IP del dominio.<br>
	>Registros name-server(NS)<br>

#A CONSULTAR


<h1>Ejercicio 11</h1>
<h3>a. Usar dig para optener la dirección del host www.redes.unlp.edu.ar en la vm responer:
-¿La solicitud fue recursiva? ¿La respuesta? ¿Como sabemos esto?
-¿Puede indicar si se trata de una respuesta autoritativa? ¿Que significa que lo sea?
-¿Cual es la dirección IP del resolver utilizado? ¿Como lo sabe?
</h3>

La respuesta fue la siguiente :
´´´

´´´

<h1>Ejercicio 12</h1>
<h3>Investigue los comandos nslookup y host. ¿Para qué sirven? Intente con ambos
comandos obtener:
● Dirección IP de www.redes.unlp.edu.ar.
● Servidores de correo del dominio redes.unlp.edu.ar.
● Servidores de DNS del dominio redes.unlp.edu.ar.</h3>

<h3>nslookup - query Internet name servers interactly</h3>
Es un programa para consultar dns de internet. Tiene dos modos interactivo y no interactivo.

salida de ejemplo

´´´
$nslookup google.com
Server:		163.10.5.78
Address:	163.10.5.78#53

Non-authoritative answer:
Name:	google.com
Address: 142.250.79.78
Name:	google.com
Address: 2800:3f0:4002:811::200e
´´´

<h3>host - DNS lookup utility</h3>
Es una herramienta simple para realizar lookups dns 

<h1>Ejercicio 13</h1>
<h3>
¿Qué función cumple en Linux/Unix el archivo /etc/hosts o en Windows el archivo
\WINDOWS\system32\drivers\etc\hosts?
</h3>
Ambos archivos son archivos de texto plano que asocia direcciones ip con nombres de host, funcionando como 
sistema de resolución de nombres local antes de consultar a un servidor DNS externo.

<h1>Ejercicio 14</h1>
<h3>
Abra el programa Wireshark para comenzar a capturar el tráfico de red en la interfaz con
IP 172.28.0.1. Una vez abierto realice una consulta DNS con el comando dig para averiguar
el registro MX de redes.unlp.edu.ar y luego, otra para averiguar los registros NS
correspondientes al dominio redes.unlp.edu.ar. Analice la información proporcionada por dig
y compárelo con la captura.
</h3>

<h1>Ejercicio 15</h1>
<h3>
Dada la siguiente situación: “Una PC en una red determinada, con acceso a Internet,
utiliza los servicios de DNS de un servidor de la red”. Analice:
	a. ¿Qué tipo de consultas (iterativas o recursivas) realiza la PC a su servidor de
	DNS?

	b. ¿Qué tipo de consultas (iterativas o recursivas) realiza el servidor de DNS
	para resolver requerimientos de usuario como el anterior? ¿A quién le realiza
	estas consultas?
</h3>

a.
La PC realiza peticiones recursivas a su servidor DNS (me imagino que habla del servidor local aca)

b.
El servidor responde mediante peticiones iterativas. Las consultas que realiza el servidor
para resolver estos requerimentos son a otros servidores encargados de responder a consultas
sobre los dominios que aparecen en la petición.

<h1>Ejercicio 16</h1>
<h3>Relacione DNS con HTTP. ¿Se puede navegar si no hay servicio de DNS?</h3>
Mediante DNS se efectuan las consultas para sitios web transmitidos por HTTP. También 
podría destacar que ambos son tecnologías de la capa de aplicación.
Sobre la segunda pregunta la respuesta es si. Se puede navegar aunque no haya servicio de DNS.



