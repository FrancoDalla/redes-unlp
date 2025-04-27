<h1>DNS. Indicar con R o I como se hace cada consulta</h1>

>Cuándo se consulta a un servidor de un TLD (Iterativa)

>Cuando se consulta al servidor de DNS local/resolver que tenemos en nuestra red (Recursiva)

>Al realizar una consulta como DNS local/resolver a un root server (Recursiva)

>Al consultar a un open DNS como 1.1.1.1 (Iterativa)

>Cuando un servidor de mail debe determinar a que servidor enviar el e-mail (Iterativa)

<h1>¿Cual es el método en HTTP que permite obtener el documento requerido y no espera recibir datos en el body. Marcar todas las correctas</h1>

a. POST
b. GET ->Esta
c. SET
d. PUT
e. DELETE

<h1>SMTP/DNS. Si el usuario uno@domain.com envía un e-mail a dos@otrodomain.org. el local DNS/RESOLVER del MTA "uno", que servidores de DNS deberá consultar si no tiene cacheada la respuesta y necesita resolverla.</h1>

>Servidores del TLD com

>Servidores raíces. ->Esta

>Servidores del TLD org -> esta

>Servidores del dominio domain

>Servidores del dominio otrodomain.org -> esta

>Servidores del cc-TLD del país donde se encuentra el servidor MX del dominio domain.com

>Servidores del cc-TLD del país donde se encuentra el servidor MX del dominio otrodomain.org ->Esta

<h1>HTTP. Indicar que caracteristicas mejoran el rendimiento de HTTP (implementadas en diferentes versiones)</h1>
>Pipelining -Esta, es una caracteristica implementada en HTTP/1.1
>Conexiones persistentes ->esta, es una caracteristica que empezo a estar implementada en HTTP/1.0
>Compresión de headers ->Esta, es una caracteristica que se definio en HTTP/2
>Uso de SSL x
>Binary framing ->Esta, es una caracteristica definida en HTTP/2
>Implementacion de cookies x

<h1>E-MAIL. Indicar caracteristicas verdaderas de SMTP</h1>
a. Usa conexiones persistentes ->Esto es asi, SMTP usa conexiones de este tipo.V
b. Siempre requiere autenticación ->Esto no es verdadero. SMTP puede o no utilizar autenticación.F
c. Usa como protocolo de transporte UDP -> Esto no es verdadero. SMTP funciona sobre TCP.F
d. Usa por default el puerto 143 o 110 ->Esto no es verdadero. Utiliza el puerto 25.F
e. Se utiliza para la comunicación entre MTAs -> Verdadero?. Pareciera que se usa para mtas.
f. "MAIL FROM" es un comando del protocolo -> e velda.

<h1>E-MAIL. Que ventajas tiene IMAP4 sobre POP3</h1>
a. Permite autenticación. ->Falso, ambos protocolos permiten autenticación.
b. Permite enviar correos cifrados. -> Falso, ambos protocolos permiten enviar correos cifrados.
c. Manejo de carpetas. -> Falso, ambos permiten uso de carpetas, lo que si. Imap es mas flexible al respecto.
d. POP3 requere copiar los mensajes completos al MUA, IMAP es más flexible, permite manipular mensajes en el servidor. ->Esto es verdad.
e. POP3 sirve solo con SMTP y no con ESMTP ->Falso.


<h1>Dada la respuesta de DNS indicar que afirmaciones son correctas</h1>
a. El servidor que respondio es autoritativo -> Falso. La salida no tiene flag aa (autoritative answer)
b. La consulta se realizó de forma recursiva -> Creo que no.
c. el servidor de DNS acepta consultas recursivas -> Verdadero, flag rd.
d. El servidor de DNS soporta consultas recursivas -> verdadero, flag ra.
e. El servidor de dns consultado es 8.8.8.8 ->
g. Se consulto por un registro NS -> Verdadero, QUESTION SECTION amazon . IN NS
g. se consulto por un registor A -> Falso.
h. El dominio es un TLD -> Verdadero, es un top-level-domain.
i. dnsb.nic.amazon es El servidor primario del dominio amazon. ->Falso, tiene varios.
d. dnsb.nic.amazon es Un servidor primario del dominio amazon ->Verdadero.

<h1> E-MAIL. El header de un e-mail "to:" lo agrega:</h1>
a. MUA LOCAL. ->e velda.
b. MTA REMOTO.
C. MTA LOCAl
d. MUA REMOTO 

<h1>Relacionado. ¿Con que comando esta relacionado?</h1>
a. RCPT TO.
b. MAIL FROM. -> e velda.
c. HELO.
d. MAIL TO.

<h1>SSL. indicar caracteristicas verdaderas de TLS</h1>
a. Implementa autenticación del servidor ->Verdad. Esto se realiza mediante los certificados digitales.
b. solo HTTP y POP3 usan TLS para asegurar comunicaciones. ->Falso, mas cosas lo usan.
c. provee cifrado para garantizar confidencialidad de los datos. -> Verdadero. Es el objetivo de TLS
d. Como parte del handshake el servidor envía su certificado que contiene su clave privada. -> Falso, lo que se comparte es la clave pública.
e. Los mensajes se cifran con la clave pública del servidor. -> Es falso.
f. La clave de sesión es un secreto compartido entre cliente y servidor (ambos la conocen) ->Es verdad. Esto se comparte en el handshake de 4 pasos.

<h1>FTP. Indicar características verdaderas de FTP</h1>
a. Usa 2 conxiones, una para control y otra para datos. ->Es verdadero.
b. Los clientes FPT requieren interfaz gráfica. -> Falso.
c. Corre sobre UDP. ->Falso.
d. Es soportado por los navegadores utilizando la URI ftp:// ->Verdadero.
e. En el moco activo la conexión de datos la abre el cliente. ->Falso. En el modo activo la conexión la abre el servidor.



