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
< Connection: close -> {Esto especifica que es 1.1} 



<h3>a. ¿Que versión de HTTP podría estar utilizando el servidor?</h3>

La versión de HTTP que podria estar usando el servidor es HTTP 1.1 ya que en la primer linea contiene

[>HEAD /metodos/ HTTP/?? ] -> En HTTP 2 y 3 no se especifica.

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

La respuesta recibida sería 302