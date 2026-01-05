# NetPractice – 42 School Project

**NetPractice** is a networking fundamentals project from 42 School. The goal is to understand and configure small-scale networks by solving 10 progressive levels of networking challenges. This project teaches **IP addressing**, **subnetting**, **routing**, and **network troubleshooting** without any coding.

This is a **practical exercise** where you learn by doing. The more you practice and understand the concepts, the easier the levels become.

## 📌 Project Overview

NetPractice consists of 10 levels of increasing difficulty where you must configure IP addresses, subnet masks, and routes to make networks function correctly. Each level tests your understanding of different networking concepts.

**Important:** This project is about **understanding**, not memorizing. Take time to learn the concepts rather than copying solutions.

## 🎯 Learning Objectives

By completing this project, you will understand:
* **IP Addressing** – How IPv4 addresses work
* **Subnet Masks** – How to divide networks into subnets
* **CIDR Notation** – Compact IP address representation
* **Network vs Host Bits** – Understanding address ranges
* **Routing** – How packets travel between networks
* **Network Troubleshooting** – Identifying and fixing configuration issues

## 📚 Core Concepts Explained

### 1. IP Addresses (IPv4)

An **IP address** is a unique identifier for a device on a network.

**Format:** `X.X.X.X` where X is a number between 0-255

**Example:** `192.168.1.10`

Each IP address consists of:
* **Network portion** – Identifies the network
* **Host portion** – Identifies the device on that network

### 2. Subnet Masks

A **subnet mask** determines which part of an IP address is the network and which part is the host.

**Common Subnet Masks:**

| CIDR | Subnet Mask | Binary | Hosts | Use Case |
|------|-------------|--------|-------|----------|
| /32 | 255.255.255.255 | 11111111.11111111.11111111.11111111 | 1 | Single host |
| /30 | 255.255.255.252 | 11111111.11111111.11111111.11111100 | 2 | Point-to-point links |
| /29 | 255.255.255.248 | 11111111.11111111.11111111.11111000 | 6 | Small networks |
| /28 | 255.255.255.240 | 11111111.11111111.11111111.11110000 | 14 | Small LANs |
| /27 | 255.255.255.224 | 11111111.11111111.11111111.11100000 | 30 | Medium LANs |
| /26 | 255.255.255.192 | 11111111.11111111.11111111.11000000 | 62 | Larger LANs |
| /25 | 255.255.255.128 | 11111111.11111111.11111111.10000000 | 126 | Large LANs |
| /24 | 255.255.255.0 | 11111111.11111111.11111111.00000000 | 254 | Standard LAN |
| /16 | 255.255.0.0 | 11111111.11111111.00000000.00000000 | 65,534 | Large networks |
| /8 | 255.0.0.0 | 11111111.00000000.00000000.00000000 | 16,777,214 | Huge networks |

### 3. CIDR Notation

**CIDR (Classless Inter-Domain Routing)** is a compact way to represent subnet masks.

**Format:** `IP_ADDRESS/PREFIX_LENGTH`

**Examples:**
* `192.168.1.0/24` = Network with 254 usable hosts
* `10.0.0.0/8` = Network with 16,777,214 usable hosts
* `172.16.0.0/30` = Network with 2 usable hosts

### 4. Calculating Subnets

**Step-by-step example:**

Given: `192.168.1.0/26`

1. **Subnet mask:** `/26` = `255.255.255.192`

2. **Binary representation:**
```
   11111111.11111111.11111111.11000000
   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^  Network bits (26)
                                 ^^  Host bits (6)
```

3. **Number of hosts:** 2^6 - 2 = 64 - 2 = **62 usable hosts**
   * Subtract 2 for network address and broadcast address

4. **Network address:** `192.168.1.0` (first address)

5. **Broadcast address:** `192.168.1.63` (last address)

6. **Usable host range:** `192.168.1.1` to `192.168.1.62`

### 5. Private IP Ranges

These IP ranges are reserved for private networks (RFC 1918):

* **Class A:** `10.0.0.0` to `10.255.255.255` (`10.0.0.0/8`)
* **Class B:** `172.16.0.0` to `172.31.255.255` (`172.16.0.0/12`)
* **Class C:** `192.168.0.0` to `192.168.255.255` (`192.168.0.0/16`)

### 6. Special IP Addresses

* **Network Address:** First address in subnet (all host bits = 0)
  * Example: `192.168.1.0/24` → Network is `192.168.1.0`

* **Broadcast Address:** Last address in subnet (all host bits = 1)
  * Example: `192.168.1.0/24` → Broadcast is `192.168.1.255`

* **Loopback:** `127.0.0.1` – Points to the local machine

* **Default Route:** `0.0.0.0/0` – Matches any destination

### 7. Routing

**Routing** determines how packets travel between different networks.

**Route Table Components:**
* **Destination:** Target network address
* **Next hop:** Router's IP address to forward packets to
* **Default route:** `0.0.0.0/0` catches all unmatched traffic

**Example:**
```
Destination      Next Hop
10.0.0.0/24      Direct (local network)
20.0.0.0/24      10.0.0.254 (router)
0.0.0.0/0        10.0.0.1 (default gateway)
```

## 🛠️ How to Approach NetPractice

### Step-by-Step Strategy

1. **Start with Level 1**
   * Don't skip ahead
   * Each level builds on previous knowledge

2. **Understand Before Filling**
   * Read what each level is asking
   * Identify which devices can't communicate
   * Determine why they can't communicate

3. **Check for Common Issues:**
   * ✅ Are IP addresses in the same subnet?
   * ✅ Are subnet masks compatible?
   * ✅ Is there a route to the destination?
   * ✅ Are IP addresses unique (no duplicates)?
   * ✅ Are network/broadcast addresses avoided?

4. **Use Logical Thinking**
   * If two devices need to communicate directly, they must be on the same network
   * If devices are on different networks, they need a router with proper routing

5. **Verify Your Configuration**
   * Use the "Check again" button
   * Read error messages carefully
   * Understand WHY it's wrong, not just WHAT is wrong

### Common Mistakes to Avoid

❌ **Using network addresses as host IPs**
```
Bad:  192.168.1.0/24 (this is the network address)
Good: 192.168.1.1/24
```

❌ **Using broadcast addresses as host IPs**
```
Bad:  192.168.1.255/24 (this is the broadcast address)
Good: 192.168.1.254/24
```

❌ **Incompatible subnet masks**
```
Bad:  Host A: 192.168.1.10/24
      Host B: 192.168.1.20/25
Good: Host A: 192.168.1.10/24
      Host B: 192.168.1.20/24
```

❌ **Duplicate IP addresses**
```
Bad:  Host A: 192.168.1.10/24
      Host B: 192.168.1.10/24
Good: Host A: 192.168.1.10/24
      Host B: 192.168.1.11/24
```

❌ **Missing or incorrect routes**
```
Bad:  No default route configured
Good: Default route: 0.0.0.0/0 → gateway
```

## 💡 Practical Tips

### Quick Subnet Calculation

**Formula:** Number of hosts = 2^(32 - prefix) - 2

* `/30` → 2^(32-30) - 2 = 4 - 2 = **2 hosts**
* `/29` → 2^(32-29) - 2 = 8 - 2 = **6 hosts**
* `/28` → 2^(32-28) - 2 = 16 - 2 = **14 hosts**
* `/27` → 2^(32-27) - 2 = 32 - 2 = **30 hosts**
* `/26` → 2^(32-26) - 2 = 64 - 2 = **62 hosts**
* `/25` → 2^(32-25) - 2 = 128 - 2 = **126 hosts**
* `/24` → 2^(32-24) - 2 = 256 - 2 = **254 hosts**

### Determining if IPs are in Same Subnet

**Method:** Perform bitwise AND of IP address and subnet mask

**Example:** Are `192.168.1.10` and `192.168.1.50` in the same `/26` subnet?
```
IP 1:     192.168.1.10  = 11000000.10101000.00000001.00001010
IP 2:     192.168.1.50  = 11000000.10101000.00000001.00110010
Mask /26: 255.255.255.192 = 11111111.11111111.11111111.11000000

Network 1: 192.168.1.0   = 11000000.10101000.00000001.00000000
Network 2: 192.168.1.0   = 11000000.10101000.00000001.00000000

Result: YES, they are in the same subnet (192.168.1.0/26)
```

### Online Tools (for learning, not cheating!)

Use these to **understand concepts**, not to get answers:

* **Subnet Calculator:** [subnet-calculator.com](https://www.subnet-calculator.com/)
* **IP Address Guide:** [ipcalc.org](http://jodies.de/ipcalc)
* **Visual Subnet:** [visualsubnetcalc.com](https://www.visualsubnetcalc.com/)

**Use these tools to:**
* Verify your manual calculations
* Understand WHY an answer is correct
* Learn subnet patterns

**Don't use them to:**
* Find answers without understanding
* Copy-paste solutions

## 🎓 Level Progression Guide

### Levels 1-3: Basics
* Focus on: IP addresses and simple subnetting
* Skills: Understanding /24, /25, /26 networks
* Concepts: Same network communication

### Levels 4-6: Intermediate
* Focus on: Routing between networks
* Skills: Configuring routes and gateways
* Concepts: Multi-network topology

### Levels 7-8: Advanced
* Focus on: Complex routing with multiple routers
* Skills: Route tables and next hops
* Concepts: Path selection

### Levels 9-10: Expert
* Focus on: Everything combined
* Skills: Full network configuration
* Concepts: Troubleshooting complex topologies

## ⚠️ Important Notes

### Why You Shouldn't Cheat

1. **You're Learning for Yourself**
   * Networking is fundamental to many tech jobs
   * Understanding networks helps in system administration, DevOps, security, etc.
   * These concepts appear in job interviews

2. **It Gets Easier with Practice**
   * First levels might seem hard
   * Once concepts click, later levels become straightforward
   * Struggling is part of learning

3. **Evaluation Matters**
   * You'll need to explain your solutions during evaluation
   * Evaluators can ask "why" questions
   * Copying without understanding will be obvious

4. **Real-World Application**
   * These are skills you'll actually use
   * Understanding networks helps debug connection issues
   * Essential for cloud computing, containers, VPNs, etc.

### How to Really Learn

✅ **Do This:**
* Solve each level yourself
* Understand WHY your solution works
* Use calculators to verify, not to solve
* Ask peers for explanations, not answers
* Redo levels if you don't fully understand

❌ **Don't Do This:**
* Copy solutions without understanding
* Skip to later levels without mastering basics
* Memorize answers instead of learning concepts
* Rush through just to finish

## 📖 Study Resources

### Recommended Learning Path

1. **Start Here:**
   * [Subnetting Made Easy (YouTube)](https://www.youtube.com/watch?v=s_Ntt6eTn94)
   * [IP Addressing and Subnetting Tutorial](https://www.cisco.com/c/en/us/support/docs/ip/routing-information-protocol-rip/13788-3.html)

2. **Practice:**
   * Do NetPractice levels in order
   * Take notes on each level
   * Redo difficult levels

3. **Deepen Understanding:**
   * [Computer Networking Course (free)](https://www.coursera.org/learn/computer-networking)
   * Read about TCP/IP stack
   * Explore routing protocols

### Books (Optional)

* **TCP/IP Illustrated, Volume 1** by W. Richard Stevens
* **Computer Networks** by Andrew S. Tanenbaum
* **Network Warrior** by Gary A. Donahue

## ✅ Verification Checklist

Before submitting each level, check:

- [ ] All IP addresses are unique
- [ ] No network or broadcast addresses used as host IPs
- [ ] Devices on same network have same network portion
- [ ] Subnet masks are consistent within each network
- [ ] Routes point to valid next hops
- [ ] Default route configured where needed
- [ ] All required fields are filled
- [ ] Green checkmarks appear on all fields

## 👤 Author

**Israa Chaabi** – 42 Student | Software Engineering  
 42 Login: `ichaabi`

## 💬 Final Advice

> **"The only way to learn networking is to practice. Take your time, understand each concept, and don't skip ahead. Your future self will thank you for learning this properly."**

Remember:
* 🧠 **Understand, don't memorize**
* 📝 **Practice makes perfect**
* 🤝 **Ask for help when stuck (but not for answers)**
* ⏰ **Take breaks if frustrated**
* 🎯 **Focus on learning, not just passing**

Good luck, and enjoy learning about networks! 🌐

---

----------------------------------------------------------

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
