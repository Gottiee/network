# Open system interconnection

### Table des matières

- [Tableau](#tableau)
- **Couche**
    - [1 - La couche physique](#1---la-couche-physique)
    - [2 - La couche de liaison de données](#2---la-couche-de-liaison-de-données)
    - [3 - La couche réseau](#3---la-couche-réseau)
    - [4 - La couche de transport](#4---la-couche-de-transport)
    - [5 - La couche session](#5---la-couche-session)
    - [6 - La couche de présentation](#6---la-couche-de-présentation)
    - [7 - La couche applicative](#7---la-couche-applicative)

L'OSI fournit une norme permettant à différents systèmes informatiques de communiquer entre eux. 

## Tableau

> *tips* Pour se souvenir du nom des couches il est conseilé de retenir: *Please do not throw sausage pizza away*

Couche | nom | utilité | protocol associé | Data Unit
--- | --- | --- | ---
7 | Application | [La couche applicative](#7---la-couche-applicative) | HTTP HTTPS - SMTP - IMAP - POP3 - FTP - SSH - DHCP - LDAP - RDP - SMB - WebDAV
6 | Presentation | [La couche de présentation](#6---la-couche-de-présentation) | / | data
5 | Session | [La couche session](#5---la-couche-session) | SOCKS | data
4 | Transport | [La couche de transport](#4---la-couche-de-transport) | TCP - UDP | segments
3 | Network | [La couche réseau](#3---la-couche-réseau) | IPv4 - IPv6 - ICMP - ICMPv6 | packets
2 | Data Links | [La couche de liaison de données](#2---la-couche-de-liaison-de-données) | ARP - Mac addressing - Ethernet - WIFI | frames
1 | Physical | [la couche physique](#1---la-couche-physique) | encode 1 et 0 | bits

## 7 - La couche applicative

La couche application du modèle OSI fournit l’interface pour l’utilisateur final qui utilise un appareil connecté à un réseau.

## 6 - La couche de présentation

La couche de présentation est responsable de la traduction, du chiffrement et de la compression des données.
Si les périphériques communiquent via une connexion chiffrée, la couche 6 est chargée d’ajouter le chiffrement du côté de l’expéditeur ainsi que de le décoder du côté du récepteur afin que celui-ci puisse présenter à la couche applicative des données lisibles non chiffrées.

Enfin, la couche de présentation est également responsable de la compression des données qu’elle reçoit de la couche applicative avant de les délivrer à la couche 5. Cela permet d’améliorer la vitesse et l’efficacité de la communication en réduisant la quantité de données qui seront transférées.

- chiffrement / déchiffrement
- compression / décompression de données

## 5 - La couche session

Il s’agit de la couche responsable de l’ouverture et de la fermeture de la communication entre les deux appareils.

- ouverture / fermeture communication entre deux appareils (session)

## 4 - La couche de transport

La couche 4 est responsable de la communication de bout en bout entre les deux appareils. Cela inclut la récupération de données de la couche de session et leur décomposition en morceaux appelés segments avant de les envoyer à la couche 3.
La couche transport est également responsable du contrôle des flux et des erreurs

- communication de bout en bout entre deux appareils
- controls flux / erreurs (inter-réseaux (entre les réseaux))

## 3 - La couche réseau

La couche réseau est chargée de faciliter le transfert de données entre deux réseaux différents. Si les deux périphériques en communication sont sur le même réseau, la couche réseau est inutile. La couche réseau divise les segments de la couche transport en unités plus petites, appelées paquets, sur le périphérique de l'expéditeur et réassemble ces paquets sur le périphérique récepteur. La couche réseau trouve également le meilleur chemin physique pour que les données atteignent leur destination ; c'est ce qu'on appelle le routage. 

- transfert entre deux réseaux différents
- divise les segments de la couche transport
- routage (choix du meilleurs chemin physique)

## 2 - La couche de liaison de données

La couche liaison facilite le transfert de données entre deux périphériques sur le même réseau. La couche liaison est également responsable du contrôle des flux et des erreurs dans les communications intra-réseau (la couche transport n’effectue que le contrôle des flux et des erreurs pour les communications inter-réseaux). 

- communication intra-réseau (dans le résaux)(flux + erreur)

## 1 - La couche physique

Cette couche inclut les équipements physiques impliqués dans le transfert de données, tels que les câbles et les commutateurs. C'est également la couche où les données sont converties en une séquence binaire

- convertion en binaire