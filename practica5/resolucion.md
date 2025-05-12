<h1>Ejercicio 1</h1>
<h3>¿Cuál es la función de la capa de transporte?</h3>
La principal función de la capa de transporte es llevar los mensajes de la capa de aplicación
hasta la capa de red y viceversa. 

<h1>Ejercicio2</h2>
<h3>Describa la estructura del segmento TCP y UDP</h3>
TCP:
EL segmento TCP consta de campos de cabecera y un campo de datos.
El campo de datos, contiene un fragmento de los datos de la aplicación. 
El MSS limita el tamaño máximo del campo de datos de un segmento.

////////////////////////////////////////////////////////////////////////////////                      /
NUMERO De puerto de origen | Numero de puerto de destino                       /
////////////////////////////////////////////////////////////////////////////////                       /
/                      Numero de secuencia                                     /
////////////////////////////////////////////////////////////////////////////////                       /
/                       Numero de reconocimiento                               /
////////////////////////////////////////////////////////////////////////////////                      /
/Long cabec./No usado/cwr/ece/urg/ack/psh/rst/syn/fin| Ventana de recepcion    /
/SUMA DE COMPROBACION INTERNET                       |Puntero de datos urgentes/
////////////////////////////////////////////////////////////////////////////////
/                                    OPCIONES                                  /
////////////////////////////////////////////////////////////////////////////////
/                                    DATOS                                     /
////////////////////////////////////////////////////////////////////////////////

El segmento TCP incluye cabeceras con el puerto origen y el puerto destino.
Tambien incluye el campo de numero de sencuencia. Este es un campo de 32 bits.
Incluye el campo de número de reconocimiento también de 32 bits. Estos son tilizados por el 
emisor y receptor para implementar un servicio de transferencia de datos fiables.
El campo ventana de recepcion de 16 bits que se utiliza para el control de flujo.
El campo longitud de cabecera de 4 bits, que especifica la longitud de la cabecera TCP
en palabras de 32 bits. Las cabeceras TCP pueden tener longitud variable a causa del campo "opciones" de TCP (como usualmente esta vacio, generalmente la cabecera TCP tipica  es de 20 bytes)
El campo opciones es opcional y de longitud variable. SE usa cuando un emisor y receptor negocian el tamaño máximo de segmento (MSS) o como un factor de escala de la ventana en las redes de altas velocidad.
El campo indicador tiene 6 bits. 
	bit ack: se utiliza para indicar que el valor transportado en el campo de reconocimiento es valido.
	bits RST, SYN y FIN: Se utilizan para el establecimiento y cierre de conexiones.
	bits CWR y ECE: Se emplean en la notificación de congestión explícita.
	bit PSH: Indica que el receptor deberá pasar los datos a la capa superior de forma inmediata.
	bit URG: Se utiliza para indicar que hay datos en este segmento que fue marcado como urgente por la entidad de la capa superior.



UDP:
La estructura del segmento UDP esta definida en la RFC 768. Los datos de la aplicación ocupan el campo de datos del segmento UDP.
La cabecera UDP tiene solo cuatro campos y cada uno de estos tiene una longitud de dos bytes.

//////////////////////////////////////////////////////////
/Numero de puerto de origen | Numero de puerto de destino/
//////////////////////////////////////////////////////////
/Longitud                   |Suma de comprobacion        /
//////////////////////////////////////////////////////////
/Datos de la aplicación                                  /
//////////////////////////////////////////////////////////



<h1>Ejercicio 3</h1>
<h3>¿Cual es el objetivo del uso de puertos en el modelo TCP/IP</h3>
Diferenciar distintos servicios que corren bajo el mismo protocolo. Permitiendo la multiplexación y demultiplexación.

<h1>Ejercicio4</h1>
<h3>Comparece Tcp y udp en cuanto a 
>a. Confiabilidad.
>b multiplexacion.
>c. Orientado a conexión.
>d. Controles de congestion.
>e. Utilización de puertos.
</h3>

<h3>Confiabilidad</h3>
Por un lado TCP es un protocolo confiable debido a que el protocolo realiza varios controles para asegurar que la información emitida llegue al receptor.
Por el otro UDP es un protocolo no-confiable dado a su funcionamiento. Este protocolo no lleva a cabo todos los chequeos que hace TCP para confirmar que el receptor recibio todos los paquetes emitidos.

<h3>Multiplexación</h3>
Un proceso puede tener uno o varios sockets, por tato la capa de transporte entrega los datos al socket y no a la aplicación.
Para identificar estos sockets estos tienen un identificador único. Cada segmento de la capa de transporte contiene un campo para poder entregar los datos al socket adecuado.
En el receptor la capa de transporte examian estos campos para identificar el socket receptor y lo envia. Este proceso es la demultiplexación.

En TCP La multiplexación y demultiplexación esta orientada a la conexión. En UDP es sin conexión.
En Tcp el socket queda identificado por una tupla de cuatro elementos Ip origen, puerto origen, ip destino y puerto destino. Por lo que cuando un segmento TCP llega a un host el host emplea estos valores para demultiplxar el segmento al socket correspondiente.
En UDP este socket queda ifdentificado por una tupla que consta de una dirección ip de destino y un numero de puerto de destino. Por lo que, si dos segmentos UDP tienen distintas direcciones ip o números de puerto de origen,
pero la misma dirección ip de destino y el mismo de puerto. Entonces los dos segmentos se enviarán al mismo proceso destino a través del mismo socket.

<h3>Orientado a conexión</h3>
TCP establece una conexión antes de la transmisión de datos y asegura que ambas partes esten sincronizadas en términos de secuencia de datos y control de flujo. Por el otro lado
UDP no necesita conexión para iniciar y finalizar una transferencia de datos.

<h3>Control de congestión</h3>
TCP proporciona mecanismos que controlan la congestión. Estos mecanismos que provee TCP evitan que cualquier conexión TCP inunde con cantidades de trafico excesivas los enlaces y routers
existente entre los hosts que estan comunicandose.
Esto se consigue regulando la velocidad a la que los lados emisores de las conexiones pueden enviar tráfico a la red. 
Posee un mecanismo que indica al emisor cuánto espacio libre hay en el búfer de almacenamiento receptor.
Por el otro lado UDP no regula esto. Una aplicación que emplee el protocolo UDP puede enviar los datos a la velocidad que le parezca durante todo el tiempo que desee.

<h3>Utilización de puertos</h3>
TCP al estar orientado a conexión, establece una conexión punto a punto entre dos dispositivos por lo que cada conexión esta limitada a los procesos que intercambian datos.
Usa números de puertos para identificar apps especificas.
UDP permite que muchos clientes o procesos envien datos por el mismo socket. 

<h1>Ejercicio 5</h1>
<h3>La PDU de la capa de transporte es el segmento. Sin embargo, aveces suele utilizarse el término datagrama. Indique cuando </h3>

Se utiliza el termino datagrama al hablar de segmentos transmitidos mediante protocolo UDP.

<h1>Ejercicio 6</h1>
<h3>Describa el saludo de tres vias de TCP ¿UDP tiene esta caracteristica?</h3>
El saludo de tres via consta de 3 pasos. 
>Paso 1:
	TCP, del lado del cliente, envía un segmento TCP especial al TCP del lado del servidor. Este segmento especial no tiene datos de la capa de aplicación. Pero uno de los bits indicadores de la cabecera del segmento, el bit SYN, se pone en 1 (por eso este segmento se llama comunmente segmento SYN). Ademas el cliente selecciona de forma aleatoria un número de secuencia inicial y lo coloca ne el campo número de secuencia del segmento TCP SYN. 
>Paso 2:
	Una vez que el datagrama IP que contiene el segmento SYN TCP llega al host servidor (si llega), el servidor extrae dicho segmento SYN del datagrama, asigna los buffers y variables TCP a la conexión y envía un segmento de conexión concedida al cliente TCP. Por último, el servidor elige su propio número de secuencia inicial y almacena este valor en el campo número de secuencia de la cabecera del segmento TCp. Este segmento de conexión concedida confirma la recepción del paquete syn. (este segmento se llama comunmente segmento SYNACK)
>Paso 3:
	Al recibir el segmento SINACK, el cliente también asigna buffers y variables a la conexión. El host cliente envía entonces al servidor otro segmento que confirma la recepción del segmento de conexión concedida por parte del servidor.(la confirmación se da almacenando el valor servidor_nsi + 1 en el campo de reconocimiento de la cabecera TCP) este segmento se llama comunmente segmento ACK. 

