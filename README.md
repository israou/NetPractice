Introduction au Réseau
Net_Practice nous initie aux bases de la mise en réseau, en nous faisant configurer les réseaux simples et comprendre le fonctionnement du protocole TCP/IP.

Qu’est-ce qu’un Réseau Informatique ?
Le réseau informatique désigne les appareils interconnectés qui peuvent échanger des données et partager des ressources. Ces appareils en réseau utilisent un système de règles, appelées protocoles de communication, pour transmettre des informations via des technologies physiques ou sans fil. En bref, le réseau est un ensemble de machines reliées entre elles. Tous ces éléments ont un point en commun : pour communiquer, ils doivent avoir une adresse IP !

Composants d’un Réseau
Hôte : Appareils connectés au réseau (ordinateurs, téléphones, serveurs, imprimantes…).
Médium de Transmission : Les réseaux utilisent des câbles (comme les câbles Ethernet) ou des technologies sans fil (Wi-Fi) pour permettre aux hôtes de communiquer.
Câbles Ethernet : Câbles réseau utilisés pour connecter des appareils dans un réseau câblé (les appareils sont connectés physiquement).
Routeurs et Switchs :
Switch : Appareil qui connecte plusieurs hôtes dans un réseau local (LAN) pour échanger des données.
Routeur : Appareil qui connecte plusieurs réseaux, souvent pour relier un réseau local à Internet.
Types de Réseaux
LAN (Local Area Network) : Réseau local couvrant une zone restreinte, comme une maison, un bureau ou une école. Les ordinateurs sont directement interconnectés via des câbles ou des technologies sans fil.
WAN (Wide Area Network) : Réseau étendu couvrant une grande zone géographique, comme Internet qui est un WAN global.
PAN (Personal Area Network) : Réseau personnel autour d'une seule personne, comme la connexion entre un smartphone et un ordinateur via Bluetooth.
MAN (Metropolitan Area Network) : Réseau qui couvre une ville ou une grande zone urbaine.
Les Bases du Réseau et des Adresses IP
Adresse IP : Chaque dispositif dans un réseau a une adresse IP unique qui permet de l'identifier. Une adresse IP peut être publique (visible sur Internet) ou privée (utilisée à l’intérieur d’un réseau local). En résumé, l'adresse IP identifie un dispositif sur un réseau TCP/IP, un peu comme une adresse postale qui permet de savoir où envoyer les informations.
Protocoles TCP/IP
Le TCP/IP est le protocole qui régit la communication entre appareils. Il spécifie comment les données doivent être découpées, transmises et rassemblées pour atteindre leur destination correctement.

Versions d’Adresses IP
IPv4 : Formée de 32 bits, divisée en 4 octets (chacun entre 0 et 255). Exemple : 192.168.12.1. Elle offre environ 4,3 milliards d’adresses uniques.
IPv6 : Formée de 128 bits, représentée par huit groupes de quatre chiffres hexadécimaux, séparés par des deux-points. Exemple : 2001:0db8:85a3:0000:0000:8a2e:0370:7334. Elle permet un nombre quasi illimité d’adresses en réponse à l'épuisement des adresses IPv4.
Adresses Publiques et Privées
Adresse IP publique : Accessible directement via Internet et attribuée à votre routeur par votre fournisseur d'accès Internet (FAI). Elle permet de se connecter à Internet depuis l’intérieur vers l’extérieur.
Adresse IP privée : Attribuée à chaque appareil dans un réseau interne. C'est ainsi que les appareils d'un même réseau communiquent entre eux. Lorsqu'un réseau est connecté à Internet, il ne peut pas utiliser d'adresses IP privées.
Plages d'Adresses IP Privées
Les plages suivantes sont réservées aux adresses IP privées :

192.168.0.0 – 192.168.255.255
172.16.0.0 – 172.31.255.255
10.0.0.0 – 10.255.255.255
NB : Chaque dispositif connecté à un réseau possède une adresse IP publique (pour être visible sur Internet) ou une adresse privée pour une utilisation locale dans un réseau interne.

Les Masques de Sous-Réseau et Sous-Réseaux
L'adresse IP est divisée en deux parties : une partie identifie le réseau et une autre l'hôte dans ce réseau. Le masque de sous-réseau aide à déterminer quelle partie de l'adresse IP est réservée au réseau et laquelle est dédiée aux hôtes. Par exemple, dans le réseau 192.168.1.0/24, le masque 255.255.255.0 indique que les 24 premiers bits identifient le réseau et les 8 derniers sont réservés pour les hôtes.

DHCP : Protocole de Configuration Dynamique des Hôtes
Le DHCP (Dynamic Host Configuration Protocol) permet d'attribuer automatiquement des adresses IP :

Quand un appareil se connecte à un réseau, il envoie une demande au serveur DHCP en disant : "Je viens de me connecter, j'ai besoin d'une adresse IP."
Le serveur DHCP (souvent le routeur) reçoit la demande et choisit une adresse IP libre pour l’appareil.
Le serveur DHCP répond avec l'adresse IP à utiliser ainsi que d'autres informations nécessaires.
L’appareil utilise l'adresse IP reçue et est prêt à communiquer sur le réseau.
Adresses Réservées
X.X.X.0 : Adresse de réseau.
X.X.X.255 : Adresse de diffusion (Broadcast), utilisée pour envoyer des données à tous les appareils du réseau.
Classes d'Adresses IP
Dans l'espace d'adressage IPv4, il existe 5 classes d'adresses IP : A, B, C, D, E. Les classes A, B et C sont principalement utilisées par la majorité des appareils sur Internet, tandis que les classes D et E sont destinées à des usages spéciaux.



Protocoles Réseau
Un protocole est un ensemble de règles que les dispositifs d'un réseau utilisent pour communiquer entre eux. Les plus importants pour toi à ce stade sont :
* TCP/IP (Transmission Control Protocol/Internet Protocol) : Le protocole standard pour la communication sur Internet. Il garantit la livraison fiable des données (TCP) et permet de les acheminer vers la bonne destination (IP).
* UDP (User Datagram Protocol) : Un protocole sans connexion donc plus rapide que TCP, mais moins fiable car il ne garantit pas que les données arrivent à destination.
Qu’est-ce que TCP (protocole de contrôle de transmissions) ?
Le protocole de contrôle de transmissions (TCP, Transmission Control Protocol) est l’un des principaux moyens de transmission des données entre les réseaux sur Internet. Il s’agit d’un protocole de communication orienté connexion qui permet aux appareils et applications informatiques d’envoyer des données et d’en vérifier la livraison. Avec le protocole de datagramme utilisateur (UDP, User Datagram Protocol), TCP constitue la base du transfert de données à l’échelle mondiale.
Qu’est-ce qu’UDP (protocole de datagramme utilisateur) ?
UDP (protocole de datagramme utilisateur) est l’un des protocoles qui permet le transfert de données entre les réseaux sur Internet. Il s’agit d’un protocole de communication orienté message qui permet aux appareils et applications informatiques d’envoyer des données, sans en vérifier la livraison. UDP est le mieux adapté à la communication en temps réel et aux systèmes de diffusion.


Quelles sont les trois différences entre TCP et UDP ?
1. TCP exige une connexion fiable entre le serveur et le destinataire, ce qui peut ralentir le transfert de données. UDP est un protocole sans connexion, donc beaucoup plus rapide. 
2. TCP garantit une transmission sans faille des données, même si les paquets perdus ou endommagés sont retransmis. UDP est un protocole « tire et oublie » qui ne vérifie pas les erreurs et ne renvoie pas les paquets de données perdus. 
3. UDP est plus adapté à la diffusion et au streaming en direct. TCP est préférable pour les communications directes (e-mails, navigation Web ou transfert de fichiers). 
À quoi servent les protocoles TCP et UDP ?
TCP est de préférence utilisé pour les communications directes nécessitant une connexion fiable (navigation Web, e-mails, SMS et transfert de fichiers). UDP sert de préférence pour la transmission de données en direct et en temps réel, lorsque la vitesse est plus importante que la fiabilité. UDP est normalement utilisé pour les jeux en ligne, le streaming en direct et les protocoles DNS.
Les ports TCP sont-ils différents des ports UDP ?
Oui, les ports TCP et UDP sont différents, mais ils utilisent parfois le même numéro de port. Par exemple, UDP/53 et TCP/53 sont tous deux utilisés pour le DNS, mais il s’agit de types de connexion différents. Les ports TCP sont conformes aux protocoles de contrôle de transmissions, tandis que les ports UDP sont conformes aux protocoles de datagramme utilisateur.

Les 4 couches du modèle TCP/IP
Le modèle TCP/IP est composé de 4 couches principales :

Couche d'Application (Application Layer)
Cette couche est la plus proche de l'utilisateur. Elle contient les protocoles qui permettent aux applications de communiquer entre elles. Les principaux protocoles de cette couche incluent :

HTTP (Hypertext Transfer Protocol) pour le web
FTP (File Transfer Protocol) pour le transfert de fichiers
SMTP (Simple Mail Transfer Protocol) pour l'e-mail
DNS (Domain Name System) pour la résolution de noms de domaines
Couche de Transport (Transport Layer)
Cette couche fournit un service de communication fiable entre processus sur différents hôtes. Elle gère la segmentation/déssegmentation des données et l'assurance de la livraison. Les principaux protocoles de cette couche sont :

TCP (Transmission Control Protocol) pour une communication fiable
UDP (User Datagram Protocol) pour une communication non fiable
Couche Internet (Network Layer)
Cette couche est responsable de la routage des paquets entre les réseaux. Elle gère l'adressesage des paquets et leur routage. Le principal protocole de cette couche est IP (Internet Protocol).

Couche d'Accès Réseau (Network Access Layer)
Cette couche gère la transmission de données entre les appareils sur le même réseau. Elle définit les protocoles physiques et de liaison de données. Les principaux protocoles de cette couche incluent Ethernet et Wi-Fi.

Fonctionnement du modèle TCP/IP
Quand on envoie des données via internet, elles passent par ces 4 couches dans un certain ordre, puis dans l'ordre inverse lorsqu'elles sont reçues. Voici les étapes principales :

Les données sont encapsulées dans des segments à la couche de transport
Ces segments sont encapsulés dans des paquets à la couche internet
Les paquets sont encapsulés dans des frames à la couche d'accès réseau
Les frames sont transmises physiquement sur le réseau
Lorsqu'ils arrivent à destination, le processus se répète dans l'ordre inverse.

Avantages du modèle TCP/IP
Le modèle TCP/IP présente plusieurs avantages :
Interopérabilité : permet une communication entre différents systèmes et réseaux
Échelle : conçu pour fonctionner avec un grand nombre de réseaux et appareils
Standardisation : fournit un cadre standardisé pour les communications réseau
Flexibilité : permet d'ajouter facilement de nouveaux protocoles
Fiabilité : offre des mécanismes pour assurer la livraison des données
En résumé, le modèle TCP/IP est le fondement technique de l'internet moderne, offrant une architecture robuste et flexible pour les communications réseau.

Le Handshake TCP/IP
Le handshake TCP/IP est un processus essentiel pour établir une connexion fiable entre deux dispositifs sur un réseau TCP/IP. Il s'agit d'une série de trois échanges de paquets entre le client et le serveur afin de s'assurer qu'ils sont prêts à communiquer entre eux.
Étapes du Handshake TCP/IP
Étape 1 : SYN
Le client envoie un paquet SYN au serveur.
Ce paquet contient :
Un numéro de séquence initial aléatoire
L'indicateur SYN mis à 1
La fenêtre de réception
Étape 2 : SYN-ACK
Le serveur reçoit le paquet SYN.
En réponse, il envoie un paquet SYN-ACK au client.
Ce paquet contient :
L'indicateur SYN mis à 1
L'indicateur ACK mis à 1
Le numéro de séquence initial du serveur
La fenêtre de réception du serveur
Étape 3 : ACK
Le client reçoit le paquet SYN-ACK.
Il répond alors avec un paquet ACK.
Ce paquet confirme que la connexion a bien été établie.
Importance du Handshake TCP/IP
Synchronisation des numéros de séquence : Permet de s'assurer que les deux parties utilisent les mêmes numéros de séquence pour la communication.
Vérification de la connexion : Assure que les deux parties sont prêtes à communiquer et que tous les paramètres nécessaires sont correctement configurés.
Prévention des attaques : Le handshake aide à prévenir les attaques comme le "SYN Flood" en limitant le nombre de connexions malveillantes.
Reliabilité : Établit une connexion fiable entre le client et le serveur avant de commencer à échanger des données.
Paramètres de la connexion : Permet d'échanger des informations importantes comme les fenêtres de réception et de transmission.
Conclusion
Le handshake TCP/IP est un élément crucial du protocole TCP, garantissant ainsi une communication sécurisée et fiable entre les appareils sur un réseau TCP/IP. Il joue un rôle vital dans l'établissement de la connexion avant que les données ne commencent à être échangées.
Le protocole TCP (Transmission Control Protocol) établit une connexion fiable en plusieurs étapes pour assurer la transmission des données. D'abord, il y a le handshake en trois étapes :
L’ordinateur A envoie un message SYN (synchronize) à l’ordinateur B pour indiquer le début de la connexion.
L’ordinateur B répond avec un message SYN-ACK (synchronize-acknowledge) pour confirmer qu'il est prêt à recevoir les données.
L’ordinateur A termine le handshake en envoyant un message ACK (acknowledge) pour valider la connexion.
Une fois le handshake terminé, les données sont envoyées entre les deux ordinateurs de manière ordonnée et fiable.

LE ROUTAGE 
Le routage est le processus par lequel un routeur achemine les données d’un réseau à un autre, jusqu’à leur destination. Le routeur détermine le meilleur chemin en analysant les adresses IP des paquets de données.
NAT (Network Address Translation) intervient lorsqu'un réseau privé veut accéder à Internet. Le routeur utilise le NAT pour remplacer l'adresse IP privée de chaque appareil par une adresse IP publique unique. Cela permet aux appareils du réseau local de partager une seule IP publique pour communiquer avec l'extérieur, tout en restant protégés.
En résumé, le routeur gère le routage pour guider les paquets et utilise le NAT pour connecter des adresses privées à Internet en toute sécurité.

Table de routage
Une table de routage est une table de données stockée dans un routeur ou un hôte réseau qui répertorie les routes vers des destinations réseau particulières. Dans NetPractice, la table de routage se compose de 2 éléments :
Destination : La destination spécifie une adresse réseau où un hôte est la cible finale des paquets. La route par défaut, ou 0.0.0.0/0, est utilisée quand aucune autre route n'est disponible pour une adresse IP de destination. Cette route par défaut utilisera l'adresse du prochain saut pour envoyer les paquets sans indiquer de destination spécifique. Elle correspondra à n'importe quel réseau.

next hop : Le prochain saut fait référence au routeur le plus proche par lequel un paquet peut passer. C'est l'adresse IP du routeur suivant sur le trajet du paquet. Chaque routeur maintient sa propre table de routage avec une adresse de prochain saut.
