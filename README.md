->>>Net_Practice nous inite aux bases de la mise en réseau, en nous faisant configurer les réseaux simples et comprendre le fonctionnement du protocole TCP/IP<<<-


  Avant de plonger dans le monde du reseautique qu'est ce qu'un réseau ?
  
  
  ----> Le réseau informatique désigne les appareils informatiques interconnectês qui peuvent échanger des données et partager des ressources entre eux,
         ces appareils en reseau utilisent un systeme de regles appelés protocole de communication pour transmettre des informations sur des technologies physiques ou sans fil.
         en gros le reseau est un ensemble de machine reliées ensembles, tous ces eements ont un point en commun : pour communiquer il faut qu'elles ayent une adresse ip !!!
   ----> LES COMPOSANTS D'UN RÉSEAU :
         * HÔTE : ce sont les appareils connectés au reseau (ordinateurs, téléphone, serveurs,imprimantes...)
         * MÉDIUM TRANSMISSION : Les reseaux utilisent les cables (comme les cables ethernet) ou des technologies sans fil comme le wi-fi pour permettre aux hôtes de communiquer.
           -les cables ethernet sont des cables reseau utilisées pour connecter des appareils au sein d'un reseau filaire (filaire veut dire réseaux informatique ou les appareils sont connectés physiaquement entre eux à l'aide de cables)
         * ROUTEURS ET SWITCH : 
           -> SWITCH : un appareil qui connecte plusieurs hotes dans un réseau local (LAN : local area network), leurs permettant d'echanger les données.
           -> ROUTEUR : un appareil qui connecte plusieurs réseaux entre eux, souvent utilisé pour relier un reseau local a internet.
  -----> LES TYPES DE RÉSEAUX :
        * LAN : Local Area Network : un réseau local couvrant une zone restreinte, comme une maison, un bureau, ou une école, les ordinnateurs sont directement interconnectés via des cables ou des technologies sans fil.
        * WAN : Wide Area Network : un réseau étendu couvrant une grnde zone géographique comme internet qui est un WAN global.
        * PAN : Personnal Area Network ; un réseau personnel autour d'une seule personne , comme la connexion entre un smartphone et un ordinateur via blueutooth.
        * MAN ; Metropolitan Area Network : un réseau qui couvre une ville ou une grnde zone urbaine.
  -----> LES BASES DU RÉSEAU ET DES ADRESSES IP :
        ADRESSE IP : chaque dispositif dans un réseau a une adresse ip (Internet Protocol) unique qui permet de l'identifier.
                     Une adresse ip peut etre publique et donc visible sur internet, ou privée et donc utilisée a l'interieur d'un réseau  local.
                     en gros l'adresse ip identifie de manière unique un dispositif sur un réseau TCP/IP
                     elle fonctionne comme une adresse postale qui permet de savoir où envoyer les informations
                     TCP/IP : C'est le protocole qui régit la communication entre appareils. Il spécifie comment les données doivent être découpées, transmises et rassemblées pour atteindre leur destination correctement.
                     il existe deux versions d'adresses ip
                     IPV4 : formée de 32 bits, divisée en 4 octets (4 nombres entre 0 à 255). exemple : 192.168.12.1 elle offre environ 4,3 milliards d'adresses uniques
                     IPV6 : formée de 128 bits, représentée par huit groupes de 4 chiffres héxadécimaux, séparés par deux points. exemple 2001:0db8:85a3:0000:0000:8a2e:0370:7334
                     elle permet un nombre quasi illimité d'adresses uniques en réponse à l'epuisement des adresses ipv4
                              **Adresse publique et adresse privée**
                     -->Une adresse IP publique est une adresse IP accessible directement via Internet et attribuée à votre routeur réseau par votre fournisseur d'accès Internet (FAI).
                     Une adresse IP publique (ou externe) vous permet de vous connecter à Internet depuis l'intérieur de votre réseau vers l'extérieur de celui-ci.
                     -->Une adresse IP privée est une adresse que votre routeur réseau attribue à votre appareil.
                     Chaque appareil au sein d'un même réseau se voit attribuer une adresse IP privée unique (parfois appelée adresse réseau privée)
                     c'est ainsi que les appareils d'un même réseau interne communiquent entre eux.
                     Lorsqu'un réseau est connecté à Internet, il ne peut pas utiliser une adresse IP provenant des adresses IP privées réservées.
                     Les plages suivantes sont réservées aux adresses IP privées :
                           192.168.0.0 – 192.168.255.255 (65,536 IP addresses)
                            172.16.0.0 – 172.31.255.255   (1,048,576 IP addresses)
                            10.0.0.0 – 10.255.255.255     (16,777,216 IP addresses)
      NB : CHAQUE DISPOSITIF CONNECTÊ A UN RESEAU POSSEDE UNE ADRESSE IP SOIT PUBLIQUE POUR ETRE VISIBLE SUR INTERNET, SOIT PRIVÉE POUR UNE UTILISATION LOCALE DANS UN RÉSEAU INTERNE (192.168.0.X) -> RESEAU DOMESTIQUE
-----> LES MASQUES DE SOUS-RÉSEAUX ET LES SOUS-RÉSEAUX :
      L'adresse ip est divisée en deux parties
        une partie identifie le reseau
        une partie identifie l'hote sur ce reseau
      Le masque de sous-reseau aide a determiner quelle partie de l'adresse ip est reservée au réseau et laquelle est dédiée aux hotes 
      exemple : dans le réseau 192.168.1.0/24  
                le masque de sous-réseau est 255.255.255.0
                cela indique que les 24 premiers bits identifient le réseau et les 8 derniers bits sont réservées pour les hotes
                255.255.255.0 en binaire donne : 11111111.11111111.11111111.00000000
  Il faut savoir que tout inclut une adresse ip est tout inclut un sous-masque ! 
  le routeur donne aux dispositifs les adresses ip , cette magie mysterieuse est connue sous DHCP 
  QU'EST CE QUE LE DHCP ??????
  ----->   DHCP (Dynamic Host Configuration Protocol) est un protocol qui permet d'attribuer q=automatiquement des adresses ip aux autres appareils
  (1) : Quand je me connecte a1 un reseau mon appareil envoie une demande au seveur DHCP du réseau, cette demande dit: "JE VIENS DE ME CONNECTER , J'AI BESOIN D'UNE ADRESSE IP"
  (2) : Le serveur DHCP (routeur) recoit la demande et choisit une adresse ip libre pour mon appareil
  (3) : Le serveur DHCP envoie une répopnse à mon appareil avec l'adresse ip qu'il doit utiliser ainsi que d'autres informations nécessaires
  (4) Mon appareil utilise l'adresse ip recue et il est maintenant pret a communiquer sur le reseau.
  Il existe deux adresses ip que je peux jamais utiliser , elles sont intouchables !!!!!!!!! 
  X.X.X.0 c'est le 1er né : adresse réseau
  X.X.X.255 la derniere adresse ip : adresse de diffusion BROADCAST --> il le diffusera a tout le monde :(
  Dans l'espace d'adressage IPV4 il existe 5 classes A B C D E , chaque classe possede une plage spécifiques d'adresses ip et determine le nombre d'appareil que vous pouvez avoir sur votre réseau
  les classes A B C sont principalemet utilisées par la majorité des appareils sur Internet 
  les classes D et E sont destinées a des utilisations speciales
  
                                                                                              
jusqu'ici tout va bien !
