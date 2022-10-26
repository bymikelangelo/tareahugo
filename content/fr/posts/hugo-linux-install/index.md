---
title: "Installer Hugo sur Linux"
date: 2022-10-21T18:01:42+02:00
draft: false
showAuthor: false
authors: 
    - "mikelangelo"
slug: "hugo-linux-install"
description: "How to install Hugo in Linux."
tags: ["installation", "linux"]
---

![Linux Logo](https://blog.webuphosting.com/wp-content/uploads/2018/04/linux-logo.png)

{{< alert "link">}}
Ce tutoriel est basé sur celui officiel que vous pouvez trouver [ici](https://gohugo.io/getting-started/installing/).
{{< /alert >}}

## Snap Package

Dans toutes les distributions Linux prenant en charge les snaps, vous pouvez installer la version « étendue » de Sass/S

```shell
snap install hugo --channel=extended
```
Pour installer la version non étendue sans prise en charge de Sass/SCSS :

```shell
snap install hugo
```

To switch between the two, use either `snap refresh hugo --channel=extended` or `snap refresh hugo --channel=stable`.

{{< alert >}}Hugo installé via Snap ne peut écrire que dans le répertoire $HOME de l'utilisateur - et les répertoires montés sur gvfs appartenant à l'utilisateur - en raison du modèle de confinement et de sécurité de Snaps. Plus d'informations sont également disponibles [dans ce numéro GitHub connexe](https://github.com/gohugoio/hugo/issues/3143).
{{< /alert >}} 

## Debian and Ubuntu

Un package hugo Debian officiel partagé avec Ubuntu et installable via **apt-get** :

```shell
sudo apt-get install hugo
```
Ce que cela installe dépend de votre version Debian/Ubuntu. Sur Ubuntu bionic (18.04), cela installe la version non étendue sans prise en charge de Sass/SCSS. Sur Ubuntu disco (19.04), cela installe la version étendue avec prise en charge de Sass/SCSS.

{{< alert >}}Cette option n'est pas recommandée car Hugo dans les gestionnaires de packages Linux pour Debian et Ubuntu a généralement quelques versions de retard, comme décrit [ici](https://github.com/gcushen/hugo-academic/issues/703/).
{{< /alert >}}








