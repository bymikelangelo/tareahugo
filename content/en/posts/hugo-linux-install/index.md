---
title: "Install Hugo on Linux"
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
This tutorial is based on the official one you can find [here](https://gohugo.io/getting-started/installing/).
{{< /alert >}}

## Snap Package

In any of the Linux distributions that support snaps, you may install the “extended” Sass/SCSS version with this command:

```shell
snap install hugo --channel=extended
```

To install the non-extended version without Sass/SCSS support:

```shell
snap install hugo
```

To switch between the two, use either `snap refresh hugo --channel=extended` or `snap refresh hugo --channel=stable`.

{{< alert >}} Hugo installed via Snap can write only inside the user’s $HOME directory—and gvfs-mounted directories owned by the user—because of Snaps’ confinement and security model. More information is also available [in this related GitHub issue](https://github.com/gohugoio/hugo/issues/3143).
{{< /alert >}} 

## Debian and Ubuntu

An official hugo Debian package which is shared with Ubuntu and is installable via **apt-get**:

```shell
sudo apt-get install hugo
```

What this installs depends on your Debian/Ubuntu version. On Ubuntu bionic (18.04), this installs the non-extended version without Sass/SCSS support. On Ubuntu disco (19.04), this installs the extended version with Sass/SCSS support.

{{< alert >}}
This option is not recommended because the Hugo in Linux package managers for Debian and Ubuntu is usually a few versions behind as described [here](https://github.com/gcushen/hugo-academic/issues/703/).
{{< /alert >}}








