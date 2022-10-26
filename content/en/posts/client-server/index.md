---
title: How Client-Server communication works 
date: 2022-10-24T13:58:54+02:00
draft: false
showAuthor: false
authors: 
    - "mikelangelo"
slug: "client-server"
description: "You can learn how is the communication process between Client and Server"
tags: ["internet", "communication"]
---

![Client-Server](https://i.imgur.com/Nu8FU.png)

## Previous Concepts

In the operation of the web, it is necessary to highlight the *role* played by the **clients** and **servers** that make up the network and are the main agents of communication.

To explain how the client-server communication process is, it is necessary to explain a series of important concepts to take into account.

### Clients and servers

Every computer connected to the network is a client or server. The type of interaction they exert is:

* A **client** is any device running software that allows you to access the Internet, commonly with a browser such as Firefox.

* The **server** is the PC that stores that website and, therefore, receives a request from a client that requests the web page from the server so that it can be displayed in the client's browser.

For this communication to be carried out successfully, it has been necessary to create **protocols** and **tools** that allow the communication process.

### TCP/IP

The **Transmission Control Protocol and Internet Protocol**, are both protocols that define, through hierarchical layers, how end-to-end communication should be carried out, specifying how data should be formatted, addressed, transmitted, routed and received by the recipient. The **layers** that compose it commonly are:

* Medium access layer.
* Internet Layer
* transport layer
* Application layer.

### DNS

The **Domain Name System** is a large database that contains the position, defined by the IP, of the web server to which the URL entered in the browser belongs.
Thus, if we want to access the website of the CPIFP Los Enlaces center, it is the DNS that is in charge of *translating* the URL entered in the browser, www.cpilosenlaces.com, by the IP address that directs to the position where find the server that hosts the web.

### HTTP

The **Hypertext Transfer Protocol** defines the language that computers must speak to communicate. It follows the request-response scheme where the client makes a request, the request, with a specHerramientas para el desarrollo Webific format established by HTTP. The server, upon receiving the request, sends a response message.

The **messages** in HTTP are in plain text and, in the case of requests, they must establish a **request method** (defined by a verb such as GET or POST) and the **URL** of the resource that is requested. For responses, these will be accompanied by the typical **response code** (such as the famous 404 error) that indicates the response from the server and the resource, if the request has been accepted.

### Files that make up the web.

Currently, a website is made up of many different files. The so-called **resources** are the ones requested by clients and rendered on the user's web page. They are mainly multimedia files of image, sound, video, PDF, etc.
The web is also made up of **code files**, commonly HTML, CSS, and JavaScript that give the web its formatting, layout, and interactivity. These are executed by the client browser.

## How is communication established?

Firstly, with an **Internet connection** configured on the client computer (it will have its own IP within the network and MAC address, both terms giving a unique position and identity to each computer connected to the network), the browser will open and enter a URL, www.cpilosenlaces.com. Then:

1. If the web has been previously addressed, the browser will have stored the IP address provided by the DNS in the cache. If not, the browser **will ask the DNS** for the IP address to which it should go to request the web resource.

2. With the **IP address** of the server, the browser makes an **HTTP request** to the server requesting the necessary resources to render the web on the client's screen. The protocol that establishes how this communication should be carried out is HTTP, and the protocol that establishes the Internet connection through which all this data travels is TCP/IP.

3. If the request is validated by the server, it sends a ***200 OK*** code and the requested resources. All requested resources travel via **data packets** that contain small chunks of the requHerramientas para el desarrollo Web
4. Finally the browser receives all the data packets and **displays the resources** on the client computer. If the request had been rejected, the browser will display a screen with the code issued by the server, such as 404.

In relation to the **response codes** that the server sends, the **200s** codes, such as 202 or 203, are the **validation** codes of the request. On the other hand, **400s** codes, like 404, are the codes corresponding to a request rejected by the server.

{{< mermaid >}}
graph TB;
A[USER] --> B{writes URL} --> C(WEB BROWSER)
C --> |send URL| D(DNS) --> |send IP| C
C --> E{if has IP} --> |yes| F(HTTP request) --> |send| G(WEB SERVER) 
E --> |no| C
G --> H{if request validated} --> |yes| I(200's codes) --> C
H --> |no| J(400's codes) --> C
{{< /mermaid >}}

## Other considerations.

The client machine is in charge of reading the HTML, CSS and JavaScript received by the server and rendering them in the browser. But, commonly in the network, many of the web applications are developed on the ***server side***, that is, the server is in charge of filtering client requests and, depending on the programming logic defined in the application, send the defined resources, make calls to the database to modify or display entries, or any other utility that the web application may have.

Server-side applications are usually programmed in various programming languages ​​and using **Frameworks** that facilitate the work. Some of them are:

| Language      | Framework     |
| ----------    | ----------    |
| Java          | Spring        |
| JavaScript    | NodeJS        |
| Python        | DJango        |
| PHP           | Laravel, Symphony |
| C#            | Asp.Net Core  |
| Ruby          | Ruby on Rails |

Currently, one of the most widely used models of software architecture is the model-view-controller (**MVC**) where the entire structure of the application is separated into three parts.

* **Model**: This defines all the data that is used or composed by the application. In many cases, this data usually corresponds to the entities that make up the database. For example, on a movie web page, the movies and their attributes are the models of the application.
* **View**: Defines how the application data is displayed and how the client will view it. It includes the HTML and CSS that will show, in this example, the listings of the movies that the web database contains.
* **Controller**: Contains the business logic that filters the inputs and requests from the client and the commands that allow the views to be modified based on the input received. On the movie website, the controller would be in charge of allowing a movie to be added or deleted and, under what conditions (such as the release date of a movie not being greater than the current date). In this same case, the controller would make the calls to the database.

![MVC](https://www.freecodecamp.org/espanol/news/content/images/size/w1600/2021/06/MVC3.png)


