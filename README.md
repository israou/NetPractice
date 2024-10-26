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
