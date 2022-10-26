---
title: "Comment fonctionne la communication client-serveur"
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

## Concepts précédents

Dans le fonctionnement du web, il faut souligner le *rôle* joué par les **clients** et **serveurs** qui composent le réseau et sont les principaux agents de communication.

Pour expliquer comment se déroule le processus de communication client-serveur, il est nécessaire d'expliquer une série de concepts importants à prendre en compte.

### Clients et serveurs

Chaque ordinateur connecté au réseau est un client ou un serveur. Le type d'interaction qu'ils exercent est :

* Un **client** est un appareil exécutant un logiciel qui vous permet d'accéder à Internet, généralement avec un navigateur tel que Firefox.

* Le **serveur** est le PC qui stocke ce site Web et, par conséquent, reçoit une demande d'un client qui demande la page Web au serveur afin qu'elle puisse être affichée dans le navigateur du client.

Pour que cette communication soit menée à bien, il a été nécessaire de créer des **protocoles** et des **outils** qui permettent le processus de communication.

### TCP/IP

Le **Protocole de contrôle de transmission et le Protocole Internet** sont deux protocoles qui définissent, à travers des couches hiérarchiques, comment la communication de bout en bout doit être effectuée, en spécifiant comment les données doivent être formatées, adressées, transmises, acheminées et reçues par le destinataire. Les **couches** qui le composent couramment sont :

* Couche d'accès moyen.
* Couche Internet
* couche de transport
* Couche d'application.

### DNS

Le **Domain Name System** est une grande base de données qui contient la position, définie par l'adresse IP, du serveur Web auquel appartient l'URL saisie dans le navigateur.
Ainsi, si nous voulons accéder au site Web du centre CPIFP Los Enlaces, c'est le DNS qui se charge de *traduire* l'URL saisie dans le navigateur, www.cpilosenlaces.com, par l'adresse IP qui dirige vers la position où trouver le serveur qui héberge le web.

### HTTP

Le **Hypertext Transfer Protocol** définit le langage que les ordinateurs doivent parler pour communiquer. Il suit le schéma requête-réponse où le client fait une requête, la requête, avec un format Webific spécifique établi par HTTP. Le serveur, à réception de la requête, envoie un message de réponse.

Les **messages** en HTTP sont en clair et, dans le cas de requêtes, ils doivent établir une **méthode de requête** (définie par un verbe tel que GET ou POST) et l'**URL** du ressource demandée. Pour les réponses, celles-ci seront accompagnées du typique **code de réponse** (comme la fameuse erreur 404) qui indique la réponse du serveur et de la ressource, si la requête a été acceptée.

### Fichiers qui composent le Web.

Actuellement, un site Web est composé de nombreux fichiers différents. Les soi-disant **ressources** sont celles demandées par les clients et affichées sur la page Web de l'utilisateur. Ce sont principalement des fichiers multimédias d'image, de son, de vidéo, de PDF, etc.
Le Web est également composé de **fichiers de code**, généralement HTML, CSS et JavaScript, qui donnent au Web sa mise en forme, sa mise en page et son interactivité. Ceux-ci sont exécutés par le navigateur client.

## Comment la communication est-elle établie ?

Tout d'abord, avec une **connexion Internet** configurée sur l'ordinateur client (il aura sa propre adresse IP au sein du réseau et son adresse MAC, les deux termes donnant une position et une identité uniques à chaque ordinateur connecté au réseau), le navigateur s'ouvrira et entrez une URL, www.cpilosenlaces.com. Alors:

1. Si le Web a déjà été adressé, le navigateur aura stocké l'adresse IP fournie par le DNS dans le cache. Sinon, le navigateur **demandera au DNS** l'adresse IP à laquelle il doit aller pour demander la ressource Web.

2. Avec l'**adresse IP** du serveur, le navigateur envoie une **requête HTTP** au serveur demandant les ressources nécessaires pour afficher le Web sur l'écran du client. Le protocole qui établit comment cette communication doit être effectuée est HTTP, et le protocole qui établit la connexion Internet par laquelle transitent toutes ces données est TCP/IP.

3. Si la requête est validée par le serveur, celui-ci envoie un code ***200 OK*** et les ressources demandées. Toutes les ressources demandées voyagent via des **paquets de données** qui contiennent de petits morceaux de la requête Web
4. Enfin, le navigateur reçoit tous les paquets de données et **affiche les ressources** sur l'ordinateur client. Si la demande a été rejetée, le navigateur affichera un écran avec le code émis par le serveur, tel que 404.

Par rapport aux **codes de réponse** que le serveur envoie, les codes **200s**, comme 202 ou 203, sont les codes de **validation** de la requête. Par contre, les codes **400s**, comme 404, sont les codes correspondant à une requête rejetée par le serveur.

{{< mermaid >}}
graph TB;
A[USER] --> B{writes URL} --> C(WEB BROWSER)
C --> |send URL| D(DNS) --> |send IP| C
C --> E{if has IP} --> |yes| F(HTTP request) --> |send| G(WEB SERVER) 
E --> |no| C
G --> H{if request validated} --> |yes| I(200's codes) --> C
H --> |no| J(400's codes) --> C
{{< /mermaid >}}

## Autres considérations.

La machine cliente est chargée de lire les HTML, CSS et JavaScript reçus par le serveur et de les restituer dans le navigateur. Mais, généralement dans le réseau, de nombreuses applications Web sont développées ***côté serveur***, c'est-à-dire que le serveur est chargé de filtrer les requêtes des clients et, selon la logique de programmation définie dans l'application, d'envoyer les ressources définies, faire des appels à la base de données pour modifier ou afficher des entrées, ou tout autre utilitaire que l'application Web peut avoir.

Les applications côté serveur sont généralement programmées dans divers langages de programmation et à l'aide de **Frameworks** qui facilitent le travail. Certains d'entre eux sont:

| Language      | Framework     |
| ----------    | ----------    |
| Java          | Spring        |
| JavaScript    | NodeJS        |
| Python        | DJango        |
| PHP           | Laravel, Symphony |
| C#            | Asp.Net Core  |
| Ruby          | Ruby on Rails |

Actuellement, l'un des modèles d'architecture logicielle les plus largement utilisés est le modèle-vue-contrôleur (**MVC**) où toute la structure de l'application est séparée en trois parties.

* **Modèle** : Ceci définit toutes les données qui sont utilisées ou composées par l'application. Dans de nombreux cas, ces données correspondent généralement aux entités qui composent la base de données. Par exemple, sur une page Web de film, les films et leurs attributs sont les modèles de l'application.
* **Affichage** : définit la façon dont les données de l'application sont affichées et comment le client les affichera. Il comprend le HTML et le CSS qui afficheront, dans cet exemple, les listes des films que contient la base de données Web.
* **Contrôleur** : Contient la logique métier qui filtre les entrées et les requêtes du client et les commandes qui permettent de modifier les vues en fonction des entrées reçues. Sur le site Web du film, le contrôleur serait chargé d'autoriser l'ajout ou la suppression d'un film et, dans quelles conditions (comme la date de sortie d'un film n'étant pas supérieure à la date actuelle). Dans ce même cas, le contrôleur effectuerait les appels à la base de données.

![MVC](https://www.freecodecamp.org/espanol/news/content/images/size/w1600/2021/06/MVC3.png)


