<h1>Ejercicio 1</h1>
<h3>¿Cuál es el puerto por defecto que se utiliza en los siguientes servicios?
Web / SSH / DNS / Web Seguro / POP3 / IMAP / SMTP
Investigue en qué lugar en Linux y en Windows está descrita la asociación utilizada por
defecto para cada servicio.</h3>

>Web usa el puerto 80.
>SSH usa el puerto 22.
>DNS usa el puerto 53.
>Web seguro usa el puerto 443.
>POP3 usa el puerto 110 para conexiones no cifradas y 995 para conexiones seguras (TLS/SSL)
>IMAP usa el puerto 143 para conexiones no cifradas y el puerto 993 para conexiones cifradas (TLS/SSL)
>SMTP usa el puerto 25 para enviar mensajes en texto plano, también pueden ser cifrados si el servidor lo soporta.
	También usa el puerto 2525 como alternativa.
	EL puerto 587 esta registrado como puerto SMTP seguro y requiere conexión TLS explícita.
	El puerto 465 funciona a través de una conexión SSL implícita.

<h1>Ejercicio 2</h1>
<h3>Investigue qué es multicast. ¿Sobre cuál de los protocolos de capa de transporte
funciona? ¿Se podría adaptar para que funcione sobre el otro protocolo de capa de
transporte? ¿Por qué?nvestigue qué es multicast. ¿Sobre cuál de los protocolos de capa de transporte
funciona? ¿Se podría adaptar para que funcione sobre el otro protocolo de capa de
transporte? ¿Por qué?</h3>

Multicast es un método de comunicación en redes donde un único emisor envia datos a múltiples receptores. 
este principalmente funciona sobre UDP por las siguientes razones:
>Sin conexion: Esto es ideal ya que al no establecer una conexión es ideal para enviar datos a múltiples receptores sin generar overhead.
>Sin control de congestión o retransmisiones: Multicast prioriza eficiencia sobre confiabilidad y UDP no implementa retransmisiones.

No sería viable adaptarlo para que funcione en otra cosa (como TCP) debido a que habría varios problemas para implementarlo.
Uno de estos podría ser como realizar el saludo de 3 vias al inicio de cada conexión.


<h1>Ejercicio 3</h1>
<h3>Investigue cómo funciona el protocolo de aplicación FTP teniendo en cuenta las
diferencias en su funcionamiento cuando se utiliza el modo activo de cuando se utiliza el
modo pasivo ¿En qué se diferencian estos tipos de comunicaciones del resto de los
protocolos de aplicación vistos?</h3>

Lo más caracteristico del protocolo FTP son sus dos conexiones simultaneas una para control y otra para datos. 
La principal diferencia es que al funcionar en modalidad activa el servidor, de forma activa, se conecta al cliente para generar la conexión de datos.
Al ser modalidad pasiva el servidor, de forma pasiva, indica al cliente a que nuevo puerto conectarse. 
La diferencia con otros protocolos más importante es la posibilidad de que FTP funcione de modo activo. Ya que esto no es una caracteristica tan común.

<h1>Ejercicio 4</h1>