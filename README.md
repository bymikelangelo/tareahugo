# tareahugo
Website create with Hugo

Este proyecto pertenece a un proyecto de la asignatura Desarrollo Web en entorno Servidor de el ciclo Superior D.A.W. 

## ¿En que consiste este repositorio? 

Este repositorio consiste en una **página web** creada con generador de webs estáticas 
[**Hugo**](https://gohugo.io/) para su desarrollo. 
Para la creación, se ha utilizado el tema [**Blowfish**](https://themes.gohugo.io/themes/blowfish/) aportado desde el pŕopio repositorio 
[original](https://github.com/nunocoracao/blowfish) de su autor. 

El objetivo de este proyecto ha sido aprender a crear un sitio web personal, como este blog, y mantenerlo, utilizando herramientas web
como Hugo que facilitan enormemente el desarrollo de una página web, pero permiten obtener una web adaptada a las exigencias personales
de cada usuario.

## ¿Como desplegar este proyecto?

Para desplegar este proyecto es necesario tener instalado Hugo en el equipo. Pulsa para ver el 
[manual de instalación](https://gohugo.io/getting-started/installing/) oficial de Hugo. 

Seguidamente, debes clonar este proyecto en tu equipo local con el siguiente comando:

~~~
git clone https://github.com/bymikelangelo/tareahugo.git <ruta de instalación>
~~~

Una vez clonado el repositorio, desde terminal ve a la carpeta del proyecto en tu ruta de instalacion

~~~
cd <ruta de instalación>
~~~

Ya en la carpeta, para desplegar la web y visualizarla en el navegadordebes ejecutar el comando `hugo server`. La salida del comando
te notificará con una **dirección IP** y **puerto** que debes introducir en tu navegador para visualizar la web. Normalmente es http://localhost:1313.

Finalmente, podras acceder a la visualización de este proyecto en tu navegador.

## Aspectos a resolver o mejorar

* Esta misma página web se ha intentado desplegar en el sitio **GitHub Pages** sin obtener un resultado favorable. Para ello se ha seguido 
la [documentación oficial](https://nunocoracao.github.io/blowfish/docs/hosting-deployment/#github-pages) presente en la página de Blowfish. 
Para ello, se creó el archivo de configuración .yaml y la action GitHub pero esta obtenia un error como resultado de su ejecución.

* Queda pendiente de implementar una imagen de cabecera por cada artículo creado, como se muestra en la página oficial de Blowfish.






