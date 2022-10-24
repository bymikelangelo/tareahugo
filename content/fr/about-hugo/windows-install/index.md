---
title: "Windows Install"
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
This tutorial is based on the official one you can find [here](https://gohugo.io/getting-started/installing/).
{{< /alert >}}

## Walkthrough

The following aims to be a complete guide to installing Hugo on your Windows PC.

{{< youtube G7umPCU-8xc >}}

### Assumptions for Windows

1. You will use **C:\Hugo\Sites** as the starting point for your new project.
2. You will use **C:\Hugo\bin** to store executable files.

### Set up Your Directories

You’ll need a place to store the Hugo executable, your content, and the generated Hugo website:

1. Open Windows Explorer.
2. Create a new folder: **C:\Hugo**, assuming you want Hugo on your C drive, although this can go anywhere
3. Create a subfolder in the Hugo folder: **C:\Hugo\bin**
4. Create another subfolder in Hugo: **C:\Hugo\Sites**

### Technical Users

1. Download the latest zipped Hugo executable from Hugo Releases.
2. Extract all contents to your **..\Hugo\bin** folder.
3. Open Windows command-line (cmd, “DOS”) to add the **hugo.exe** executable to your PATH
    * do `set PATH=%PATH%;C:\Hugo\bin` to have hugo in PATH for the currently opened cmd box
    * do `setx PATH "%PATH%;C:\Hugo\bin"` to have hugo in PATH for every newly opened cmd box 
    {{< alert >}}**Warning!** “setx”, not “set”, plus syntax ‘key “val”’, not ‘key=val’{{< /alert >}}


{{< alert "comment">}}
You may also use “Git CMD” from the Git for Windows package for the native Windows commands set and setx, but not “Git Bash”, PowerShell, or any other “CLI” with different commands.
{{< /alert >}}

### Verify the Executable

Run a few commands to verify that the executable is ready to run, and then build a sample site to get started. 

Oper a Command Prompt (**cmd**), type `hugo help` and press the Enter key. You should see output that starts with:

    hugo is the main command, used to build your Hugo site.

    Hugo is a Fast and Flexible Static Site Generator
    built with love by spf13 and friends in Go.

    Complete documentation is available at https://gohugo.io/.

If you do, then **the installation is complete**. If you don’t, double-check the path that you placed the **hugo.exe** file in and that you typed that path correctly when you added it to your **PATH** variable. 

## Troubleshoot Windows Installation

{{< youtube c8fJIRNChmU >}}
