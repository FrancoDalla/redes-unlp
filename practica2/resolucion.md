<h1>Ejercicio 18</h1>
<h3>
Investigue cuál es el principal uso que se le da a las cabeceras Set-Cookie y Cookie en
HTTP y qué relación tienen con el funcionamiento del protocolo HTTP.
</h3>
El header set-cookie se usa para enviar cookies desde el servidor al user-agent. Así este puede enviarlos
de vuelta al servidor. 
Por otro lado el head cookie de una solicitud HTTP contiene las cookies almacenadas que fueron enviadas
previamente.
La relación entre estas y HTTP es que este no es un protocolo que mantenga el estado de la conexión.
Por lo que para almacenar información a lo largo de las conexiones tiene que recurrirse a estas 
cabeceras y las cookies para hacer un seguimiento de lo realizado o de los datos del usuario


<h1>Ejercicio 19</h1>

<h3>
Cuál es la diferencia entre un protocolo binario y uno basado en texto? ¿De qué tipo
de protocolo se trata HTTP/1.0, HTTP/1.1 y HTTP/2?
</h3>

Una diferencia importante es que, por un lado un protocolo binario esta mejor delimitado para la computadora.
Los datos que se envian tienen una longitud establecida. 
Por otro lado los protocolos de texto tienen que ir recorriendo el dato hasta encontrar un caracter como
un salto de linea u otros caracteres similares que marquen el final del dato. 

HTTP 1.0 1.1 son protocolos basados en texto.
HTTP 2 es un protocolo binario.

<h1>Ejercicio 20</h1>

<h3>.a ¿Qué función cumple la cabecera host en HTTP 1.1? Existia en HTTP 1.0? ¿Que ocurre en HTTP 2?</h3>

La cabecera host en HTTP 1.1 es una cabecera obligatoria que especifica el nombre de dominio del
servidor para hosting virtual y, opcionalmente, el número de puerto TCP en el que el puerto escucha.

En HTTP 1.0 existe y puede agregarse pero no es obligatorio como en su versión posterior.

En HTTP 2 el header host es reemplazado por :authority: 





<h1>Ejercicio de parcial</h1>

curl -X ?? www.redes.unlp.edu.ar/xxx
> HEAD /metodos/ HTTP/?? ->{Esto especifica el recurso solicitado}
> Host: www.redes.unlp.edu.ar
> User-Agent: curl/7.54.0

< HTTP/?? 200 OK
< Server: nginx/1.4.6 (Ubuntu)
< Date: Wed, 31 Jan 2018 22:22:22 GMT
< Last-Modified: Sat, 20 Jan 2018 13:02:41 GMT
< Content-Type: text/html; charset=UTF-8
< Connection: close -> {Esto especifica que es HTTP 1.1} 



<h3>a. ¿Que versión de HTTP podría estar utilizando el servidor?</h3>

Ademas al final de la respuesta figura connection: close ->En 1.1 se asume persistencia, como arriba
no se definio esto, podemos suponer que utiliza esto.

<h3>b. ¿Que método está utiliando? Dicho metodo ¿Retorna el recurso completo solicitado?</h3>

El metodo utilizado es HEAD y este no retorna el recurso completo. Es como el get pero no retorna el cuerpo.

<h3>c. ¿Cual es el recurso solicitado?</h3>

El recurso solicitado es un documento html llamado metodos. 

<h3>d. ¿El metodo funcionó correctamente?</h3>

La respuesta al pedido es un 200 OK por lo que funciono correctamente.

<h3>e. Si la solicitud hubiera llevado un encabezado que diga:
If-Modified-Since: Sat, 20 Jan 2018 13:02:41 GMT
¿Cuál habría sido la respuesta del servidor web? ¿Qué habría hecho el
navegador en este caso?</h3>

La respuesta recibida sería 302https://developer.mozilla.org/es/docs/Web/HTTP/Headers/Host