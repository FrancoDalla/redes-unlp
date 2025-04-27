<h1>Ejercicio 1</h1>
<h3>¿Qué protocolos se utilizan para el envío de mails entre el cliente y su servidor de
correo? ¿Y entre servidores de correo?
</h3>

Entre el cliente y su servidor de correo se utiliza smtp.
Entre servidores se utiliza smtp pero ademas tambien aparece el protocolo DNS para encontrar la dirección del destinatario.
(se pregunta por el registro MX y también por el A o AAAA del servidor de correo)

<h1>Ejercicio 2</h1>
<h3>
2. ¿Qué protocolos se utilizan para la recepción de mails? Enumere y explique
características y diferencias entre las alternativas posibles.
</h3>
Para recepción se utilizan principalmente POP e IMAP.


<h1>Ejercicio 7</h1>
<h3>¿En algún caso es posible enviar más de un correo durante una misma conexión TCP?
Considere:
● Destinatarios múltiples del mismo dominio entre MUA-MSA y entre MTA-MTA
● Destinatarios múltiples de diferentes dominios entre MUA-MSA y entre
MTA-MTA></h3>


Destinatarios múltiples del mismo dominio entre MUA-MSA y entre MTA_MTA.

Entre MUA y MSA:
Es posible. El MUA puede enviar múltiples correos en una misma conexión TCP si el MSA lo permite. SMTP permite varias transacciones en una sola sesión.

Entre MTA y MTA:
Es posible. Cuando un MTA envía correos a otro MTA para el mismo dominio, puede reutilizar la misma conexión TCP para enviar múltiples mensajes. Esto forma parte de la optimización de SMTP.

Destinatarios múltiples de diferentes dominios.

Entre MUA y MSA:
Es posible, pero depende de la configuración del MSA. 

Entre MTA Y MTA:
No es común.

<h1>Ejercicio 8</h1>
<h3>Indicar si es posible que el MSA escuche en un puerto TCP diferente a los convencionales ¿Que implicancias tendría?</h3>

Si bien esto es posible tiene implicancias que afectan a la efectividad del uso del MSA. Por ejemplo problemas de compatibilidad por MUAS que esperan el uso de puertos por defecto. Problemas con Firewall o problemas de entrega por, similar a los MUAS, asumir el uso de los puertos estandar. 
Si bien se puede hacer que el MSA escuche en otro puerto esto debe ir acompañado de la configuración pertinente de otros elementos relacionados en el servicio de correo.

<h1>Ejercicio 9</h1>
<h3>Indique sí es posible que el MTA escuche en un puerto TCP diferente a los
convencionales y qué implicancias tendría.</h3>
También es posible pero, similar al MSA en el ejercicio anterior, esto tiene sus distintas implicancias que afectan al buen uso del MSA. 
Si bien puede ser incluso más seguro (seguridad por ofuscación) también trae consigo desventajas como que los MTA remotos intentaran contactan con el puerto 25. Si este no escucha a traves del puerto definido como estandar podra perder mensajes.
También podría ser catalogado como algo extraño por distintos servicios, ya que puede notificarse que el MTA no esta funcionando según los estandares.
