---
title: "Instalación en entornos Linux"
date: 2022-10-21T18:01:42+02:00
draft: false
showAuthor: false
authors: 
    - "mikelangelo"
slug: "linux-install"
description: "How to install Hugo in Linux."
tags: ["installation", "linux"]
---

![Linux Logo](https://blog.webuphosting.com/wp-content/uploads/2018/04/linux-logo.png)

{{< alert "link">}}
Este tutorial está basado en el oficial que puedes encontrar [aquí](https://gohugo.io/getting-started/installing/).
{{< /alert >}}

## Snap

En cualquiera de las distribuciones de Linux que admiten Snap, puedes instalar la versión "extendida" de Sass/SCSS con este comando:

```shell
snap install hugo --channel=extended
```

Para instalar la versión no extendida sin compatibilidad con Sass/SCSS:

```shell
snap install hugo
```

Para cambiar entre cualquera de las dos, alterne entre `snap refresh hugo --channel=extended` y `snap refresh hugo --channel=stable`.

{{< alert >}} 
Hugo, instalado a través de Snap, solo puede escribir dentro del directorio $HOME del usuario, y los directorios montados en gvfs propiedad de él, debido al modelo de confinamiento y seguridad de Snap. Más información disponible [en este hilo relacionado de GitHub](https://github.com/gohugoio/hugo/issues/3143).
{{< /alert >}} 

## Debian y Ubuntu

El paquete oficial de Hugo para distros basadas en Debian se puede instalar a través de **apt-get**:

```shell
sudo apt-get install hugo
```

El resultado de esta instalación depende de su versión de Debian/Ubuntu. En Ubuntu bionic (18.04), se instala la versión no extendida sin compatibilidad con Sass/SCSS. Para Ubuntu disco (19.04) se instalarña una versión extendida con compatibilidad con Sass/SCSS.

{{< alert >}}
No se recomienda esta opción de instalación debido a que la versión de Hugo en los administradores de paquetes de Linux para Debian y Ubuntu no es la más actualizada o reciente. Puedes ver información al respecto [aquí](https://github.com/gcushen/hugo-academic/issues/703/).
{{< /alert >}}








