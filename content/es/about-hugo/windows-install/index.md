---
title: "Instalación para Windows"
date: 2022-10-21T18:01:14+02:00
draft: false
showAuthor: false
authors: 
    - "mikelangelo"
slug: "windows-install"
description: "How to install Hugo in Windows."
tags: ["instalation", "windows"]
---

![Windows Logo](https://storage.googleapis.com/webdesignledger.pub.network/WDL/6f050e39-windows_10_logoblue.svg-copy_windows.jpg)

{{< alert "link">}}
Este tutorial está basado en el oficial que puedes encontrar [aquí](https://gohugo.io/getting-started/installing/).
{{< /alert >}}

## Tutorial paso a paso

La siguiente vídeo es una guía completa de instalación de Hugo para Windows

{{< youtube G7umPCU-8xc >}}

### Cosas que debes suponer

1. Se usará **C:\Hugo\Sites** como punto de partida para un nuevo projecto.
2. Se usará **C:\Hugo\bin** para almacenar los archivos ejecutables.

### Estableciendo tus directorios

Vas a necesitar un lugar para almacenar el ejecutable de Hugo, su contenido y el sitio web generado con Hugo:

1. Abre el explorador de archivos.
2. Crea una nueva carpeta: **C:\Hugo**, asumiendo que quieres en Hugo en la unidad C, aunque puede almacenarse en cualquiera.
3. Crea una subcarpeta en el directorio Hugo: **C:\Hugo\bin**
4. Crea otra subcarpeta en Hugo: **C:\Hugo\Sites**

### Usuarios técnicos

1. Descargua el último ejecutable comprimido de Hugo en Hugo Releases.
2. Extrae todo el contenido a tu carpeta **..\Hugo\bin**.
3. Abre la linea de comandos de Windows (**cmd**) para añadir **hugo.exe** a la RUTA
    * do `set PATH=%PATH%;C:\Hugo\bin` to have hugo in PATH for the currently opened cmd box
    * do `setx PATH "%PATH%;C:\Hugo\bin"` to have hugo in PATH for every newly opened cmd box 
    {{< alert >}}**Warning!** “setx”, not “set”, plus syntax ‘key “val”’, not ‘key=val’{{< /alert >}}


{{< alert "comment">}}
Es posible utilizar "Git CMD" del paquete Git para Windows para los comandos nativos de Windows set y setx, pero no "Git Bash", PowerShell o cualquier otra "CLI" con comandos diferentes.
{{< /alert >}}

### Verifica la instalación

Vamos a ejecutatar algunos comandos para verificar que el ejecutable está listo para ejecutarse.

Abre un símbolo del sistema (**cmd**), introduce `hugo help` y presiona Enter. Deberías ver como resultado la salida:

    hugo is the main command, used to build your Hugo site.

    Hugo is a Fast and Flexible Static Site Generator
    built with love by spf13 and friends in Go.

    Complete documentation is available at https://gohugo.io/.

Si es así, entonces **la instalación ha sido finalizada con éxito**. Si no, verifica dos veces la ruta en la que colocó el archivo **hugo.exe** y que ésta fue escrita correctamente cuando la agregaste a la variable de entorno **PATH**.

## Problemas durante la instalación en Windows

{{< youtube c8fJIRNChmU >}}
