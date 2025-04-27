<h1>Indicar de forma breve la diferencia entre el método GET y el PUT</h1>
El metodo get solicita una representación del recurso especificado. Estas deben utilizarse generalmente para recuperar datos, no incluirlos.
Es una petición sin cuerpo, valida si lo incluye. Segura, idempotente(utilizarlo varias veces tiene el mismo efecto), cacheable y permitida en formularios HTML

Por el otro lado el metodo put es usado para crear nuevos elementos o remplazar una representación del elemento destino con los datos incluidos en su petición.
Por lo que esta es una petición con cuerpo, incorrecta si no lo incluye, no se considera segura, idempotente, no cacheable y que no esta permitida en formularios HTML.

<h1>Indicar cuales características mejoran el rendimiento de HTTP</h1>

a.
Conexiones persistentes ->eta
b.
Uso de SSL ->
c.
Binary Framing -> esta
d.
Compresión de headers -> Esta
e.
Pipelining -> esta

<h1>En HTTP 1.0 no se pueden usar conexiones persistentes</h1>
Falso.

<h1>Los códigos HTTP 3XX están relacionados con re direcciones</h1>
Verdadero.

<h1>HTTP no mantiene estados, por más que tenga conexiones persistentes</h1>
Verdadero.

<h1>SSL/TLS le agrega una capa de seguridad al protocolo HTTP sin cambiarlo</h1>
Verdadero.
