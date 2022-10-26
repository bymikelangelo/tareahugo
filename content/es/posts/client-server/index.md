---
title: Cómo funciona la comunicación entre Cliente y Servidor
date: 2022-10-24T13:58:54+02:00
draft: false
showAuthor: false
authors: 
    - "mikelangelo"
slug: "client-server"
description: "Aprende como funciona el principal modelo de comunicación que compone Internet."
tags: ["internet", "communication"]
---

![Client-Server](https://i.imgur.com/Nu8FU.png)

## Conceptos previos

En el funcionamiento de la web hay que destacar el *papel* que tienen los **clientes** y **servidores** que componen la red y son los principales agentes de la comunicación. 

Para explicar cómo es el proceso de comunicación entre cliente -servidor, es necesario explicar una serie de conceptos importantes a tener en cuenta. 

### Clientes y servidores

Todo ordenador conectado a la red es un cliente o servidor. El tipo de interacción que estos ejerces es:

* Un **cliente** es cualquier dispositivo que ejecuta un software que permite acceder a Internet, comunmente con un navegador como Firefox. 

* El **servidor** es el PC que almacena esa web y, por lo tanto, recibe la petición de un cliente que solicita la página web al servidor para que esta sea mostrada en el navegador del cliente.

Para que esta comunicación se realice con éxito, ha sido necesario la creación de **protocolos** y **herramientas** que permitan el proceso de comunicación. 

### TCP/IP

El **Protocolo de Control de Transmisión y Protocolo de Internet**, son ambos los protocolos que definen, a traves de capas jerarquizadas, como debe realizarse la comunicación de extremo a extremo especificando cómo los datos deberían ser formateados, direccionados, transmitidos, enrutados y recibidos por el destinatario. Las **capas** que lo componen comunmente son: 

* Capa de acceso al medio. 
* Capa de Internet
* Capa de transporte
* Capa de aplicación. 

### DNS

El **Sistema de Nombres de Dominio** es una gran base de datos que contiene la posición, definida por la IP, del servidor web a la que pertenece la URL introducida en el navegador. 
Así pues, si queremos acceder a la web del centro CPIFP Los Enlaces, es el DNS el que se encarga de *traducir* la URL introducida en el navegador, www.cpilosenlaces.com, por la dirección IP que direcciona a la posición donde se encuentra el servidor que almacena la web. 

### HTTP 

El **Protocolo de transferencia de Hipertexto** define el idioma que han de hablar las computadoras para entablar la comunicación. Sigue el esquema petición-respuesta donde el cliente realiza una petición, la petición, con un formato concreto establecido por HTTP. El servidor, al recibir la petición, envia un mensaje de respuesta. 

Los **mensajes** en HTTP son en texto plano y, en el caso de las peticiones deben establecer un **método de petición** (definido por un verbo como GET o POST) y la **URL** del recurso que se solicita. Para las respuestas, estas estaran acompañadas de el típico **código de respuesta** (como el famoso error 404) que indica cual es la respuesta del servidor y el recurso, si la petición ha sido aceptada. 

### Archivos que componen la web.

En la actualidad, una web esta compuesta por muchos archivos deferentes. Los llamados **recursos** son los que solicitan los clientes y se renderizan en la página web del usuario. Son principalmente, archivos multimedia de imagen, sonido, video, PDF, etc. 
La web tambien se compone de **archivos de código**, comunmente HTML, CSS y JavaScript que dan formato, diseño e interactividad a la web. Estos son ejecutados por el navegador del cliente.

## ¿Cómo se establece la comunicación?

En primer lugar, con una **conexión a Internet** configurada en el equipo cliente (este poseerá su propia IP dentro de la red y la dirección MAC, ambos términos dan una posición e identidad única a cada ordenador conectado a la red), se abrira el navegador e introducira una URL, www.cpilosenlaces.com. Entonces:

1. Si la web ha sido direccionada con anterioridad, el navegador habrá almacenado la dirección IP proporcionada por el DNS en la memoria caché. Si no es así, el navegador **solicitará al DNS** cual es la dirección IP a la que debe dirigirse para solicitar el recurso web. 

2. Con la **dirección IP** del servidor, el navegador realiza una **petición HTTP** al servidor relcamando los recursos necesarios para renderizar la web en la pantalla del cliente. El protocolo que establece como debe efectuarse esta comunicación es el HTTP y, el protocolo que establece la conexión a Internet por la que viajan todos esos datos es TCP/IP. 

3. Si la petición es validada por el servidor, este envia un ***código 200 OK*** y los recursos que se solicitan. Todos los recursos solicitados viajan a traves de **paquetes de datos** que contienen pequeños trozos de los recursos solicitados. Esto permite al servidor atender a las peticiones de miles de usuarios. 

4. Finalmente el navegador recibe todos los paquetes de datos y **muestra los recursos** en el equipo cliente. Si la petición hubiese sido rechazada, el navegador mostrará una pantalla con el código emitido por el servidor, como el 404. 

En relación a los **códigos de respuesta** que el servidor envia, los códigos **200s**, como el 202 o el 203, son los códigos de **validación** de la petición. Por otro lado, los códigos **400s**, como el 404, son los códigos correspondientes a una petición rechazada por el servidor.

{{< mermaid >}}
graph TB;
A[USER] --> B{writes URL} --> C(WEB BROWSER)
C --> |send URL| D(DNS) --> |send IP| C
C --> E{if has IP} --> |yes| F(HTTP request) --> |send| G(WEB SERVER) 
E --> |no| C
G --> H{if request validated} --> |yes| I(200's codes) --> C
H --> |no| J(400's codes) --> C
{{< /mermaid >}}

## Otras consideraciones.

La máquina cliente es la encargada de leer el HTML, CSS y JavaScript recibidos por el servidor y renderizarlos en el navegador. Pero, comunmente en la red, muchas de las aplicaciones web estan desarrolladas de ***lado del servidor***, es decir, es el servidor el encargado filtrar las peticiones de los clientes y, en funcion de la lógica de programación definida en la apliación, enviar los recursos definidos, hacer las llamadas a la base de datos para modificar o mostrar entradas, o cualquier otra utilidad que pueda tener la apliacion web. 

Las aplicaciones del lado del servidor suelen programarse en diversos lenguajes de programación y utilizando **Frameworks** que faciliten el trabajo. Algunos de estos son:

| Lenguaje      | Framework     |
| ----------    | ----------    |
| Java          | Spring        |
| JavaScript    | NodeJS        |
| Python        | DJango        |
| PHP           | Laravel, Symphony |
| C#            | Asp.Net Core  |
| Ruby          | Ruby on Rails |

En la actualidad, uno de los modelos mas utilizado de arquitectura de software es el modelo-vista-controlador (**MVC**) donde se separan en tres partes toda la estructura de la aplicación.

* **Modelo**: En el se definen todos los datos que se utilizan o componen la aplicación. En muchos casos, estos datos suelen corresponder a las entidades que componen la base de datos. Por ejemplo, en una página web de cine, las películas y sus atributos son los modelos de la aplicación.
* **Vista**: Define como se muestran los datos de la aplicación y como los visualizará el cliente. Engloba el HTML y CSS que mostraran, en este ejemplo, los listados de las películas que contienen la base de datos de la web. 
* **Controlador**: Contiene la lógica de negocio que filtra las entradas y peticiones del cliente y los comandos que permiten modificar las vistas en funcion de la entrada recibida. En la web de cine, el controlador se encargaría de permitir añadir o eliminar una película y, bajo que condiciones (como que la fecha de estreno de una película no fuera mayor a la fecha actual). En este mismo caso, el controlador haría las llamadas a la base de datos.

![MVC](https://www.freecodecamp.org/espanol/news/content/images/size/w1600/2021/06/MVC3.png)


