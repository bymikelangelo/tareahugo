---
title: "Installer Hugo sur Windows"
date: 2022-10-21T18:01:14+02:00
draft: false
showAuthor: false
authors: 
    - "mikelangelo"
slug: "hugo-windows-install"
description: "How to install Hugo in Windows."
tags: ["instalation", "windows"]
---

![Windows Logo](https://storage.googleapis.com/webdesignledger.pub.network/WDL/6f050e39-windows_10_logoblue.svg-copy_windows.jpg)

{{< alert "link">}}
Ce tutoriel est basé sur celui officiel que vous pouvez trouver [ici](https://gohugo.io/getting-started/installing/).
{{< /alert >}}

## Procédure pas à pas

Ce qui suit vise à être un guide complet pour installer Hugo sur votre PC Windows.

{{< youtube G7umPCU-8xc >}}

### Hypothèses pour Windows

1. Vous utiliserez **C:\Hugo\Sites** comme point de départ pour votre nouveau projet.
2. Vous utiliserez **C:\Hugo\bin** pour stocker les fichiers exécutables.

### Configurez vos répertoires

Vous aurez besoin d'un emplacement pour stocker l'exécutable Hugo, votre contenu et le site Web Hugo généré :

1. Ouvrez l'Explorateur Windows.
2. Créez un nouveau dossier : **C:\Hugo**, en supposant que vous vouliez Hugo sur votre lecteur C, bien que cela puisse aller n'importe où
3. Créez un sous-dossier dans le dossier Hugo : **C:\Hugo\bin**
4. Créez un autre sous-dossier dans Hugo : **C:\Hugo\Sites**

### Utilisateurs techniques

1. Téléchargez le dernier exécutable Hugo compressé depuis Hugo Releases.
2. Extrayez tout le contenu dans votre dossier **..\Hugo\bin**.
3. Ouvrez la ligne de commande Windows (cmd, "DOS") pour ajouter l'exécutable **hugo.exe** à votre PATH
    * do `set PATH=%PATH%;C:\Hugo\bin` to have hugo in PATH for the currently opened cmd box
    * do `setx PATH "%PATH%;C:\Hugo\bin"` to have hugo in PATH for every newly opened cmd box 
    {{< alert >}}**Warning!** “setx”, not “set”, plus syntax ‘key “val”’, not ‘key=val’{{< /alert >}}


{{< alert "comment">}}
You may also use “Git CMD” from the Git for Windows package for the native Windows commands set and setx, but not “Git Bash”, PowerShell, or any other “CLI” with different commands.
{{< /alert >}}

### Vérifier l'exécutable

Exécutez quelques commandes pour vérifier que l'exécutable est prêt à être exécuté, puis créez un exemple de site pour commencer.

Opérez une invite de commande (**cmd**), tapez `hugo help` et appuyez sur la touche Entrée. Vous devriez voir une sortie qui commence par :

    hugo est la commande principale, utilisée pour construire votre site Hugo.

    Hugo est un générateur de site statique rapide et flexible
    construit avec amour par spf13 et ses amis en Go.

    Une documentation complète est disponible sur https://gohugo.io/.

Si c'est le cas, **l'installation est terminée**. Si ce n'est pas le cas, revérifiez le chemin dans lequel vous avez placé le fichier **hugo.exe** et que vous avez correctement tapé ce chemin lorsque vous l'avez ajouté à votre variable **PATH**.

## Dépanner l'installation de Windows

{{< youtube c8fJIRNChmU >}}
