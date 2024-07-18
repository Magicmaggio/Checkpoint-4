# 💪 Challenge  

## 1. Assurer le support utilisateur en centre de service

### 1.1 Du point de vue d'ITIL, quelle est la différence entre un incident et un problème ?

### 1.2 Quels sont les différents moyens de prendre le contrôle à distance d'une machine ?

### 1.3 Donne les différentes étapes à respecter dans une résolution d'incident par téléphone.  

  
## 2. Exploiter des serveurs Windows et un domaine Active Directory

### 2.1 Qu'est-ce qu'un rôle FSMO ?

### 2.2 En quoi la réplication entre contrôleurs de domaine est primordiale sur un domaine ?  

  
## 3. Exploiter des serveurs Linux

### 3.1 Quel est le résultat de la commande suivante : chmod u+x /home/tssr/factures/export.sh ?

### 3.2 Quelle commande dois-tu écrire dans un terminal sur un OS Debian pour ajouter l'adresse IP 172.16.8.16/24 à l'interface enp0s8 ?

### 3.3 L'utilisateur Wilder ne parvient plus à accéder au dossier travaux. Explique la cause probable et donne les outils (commandes) pour diagnostiquer et résoudre le problème.
```
wilder@SRV08:~$ ls /home/wilder/travaux/
ls: impossible d'ouvrir le répertoire /home/wilder/travaux/: Permission non accordée
wilder@SRV08:~$
```
### 3.4 D’après les éléments de la capture ci-dessous, si on ajoute un disque dur supplémentaire qui n'a qu'une seule partition, comment se nommera t'elle ?


### 3.5 Donne 2 commandes qui te permettent de visualiser les disques et les partitions d'un serveur Linux.  

  
## 4. Exploiter un réseau IP

### 4.1 Une entreprise a un réseau 192.160.16.0/25. Elle souhaite le découper en 4 sous-réseaux de taille identiques.
Pour les 2 premiers sous-réseaux, donne l’adresse de réseaux, le masque (en notation CIDR), la première adresse disponible, la dernière adresse disponible, ainsi que l'adresse de broadcast.

### 4.2 Complète le tableau de conversion suivant :  

  
| Décimal |	Binaire |	Hexadécimal |  
| :-: | :-: | :-: |  
| 9	| | |	  
| 127 |	|	0x7F |  
| 255 |	|	|  
| 16 |	00010000 | |  


### 4.3 Pour le schéma ci-dessous :

    Quels sont les liens trunk ?
    Quelle méthode de routage intervlan est utilisée ?


### 4.4 Sur un réseau IP, 2 PC ont la configuration IP suivante :

    PC1 : 192.168.1.54/24
    PC2 : 192.168.2.74/24

Sans changer l'adresse IP des 2 PC, donne une solution matérielle et une modification du paramétrage à effectuer pour que les 2 PC puissent communiquer entre-eux.

### 4.5 Des ordinateurs sont connectés sur un switch qui n'a qu'un seul vlan, avec les configurations IP suivantes :
PC	Adresse IP	Masque de sous-réseau
PC1	192.168.10.8	255.255.255.0
PC2	192.168.10.12	255.255.255.0
PC3	192.168.10.10	255.255.0.0
PC4	192.168.11.9	255.255.255.0

Pour chaque ordinateur, indique en expliquant les communications ICMP réussies.

### 4.6 Quelles sont les actions possibles à mettre en œuvre pour sécuriser un réseau sans fil ?

### 4.7 Quelles sont les routes statiques à ajouter sur le routeur Routeur1 pour permettre la communication entre PC0 et PC3 ?

### 4.8 Complète le tableau suivant avec les informations sur les différents services/protocoles :  

| Acronyme |	Nom complet |	Port(s) par défaut TCP |	Port(s) par défaut UDP |  
|:-:|:-:|:-:|:-:|
| HTTP | | | |			
|	|	20 (données), 21 (commandes), 22 (sécurisé) | | |    	
| SSH | | | |			
| TFTP | | | |			
| |	Simple Mail Transfer Protocol | | |		
| IMAP | | | |			
| LDAP | | | |			
| | |	110 (non sécurisé), 995 (sécurisé) | |  	
| |	| 53 | |	
| NTP | | | |  			
| |	| 995 | |  	

### 4.9 Sur quels ports du switch peut-on brancher ce téléphone IP ?

### 4.10 Indique sur quelle couche du modèle TCP/IP les protocoles suivant se trouve (mets une croix "x" dans la bonne colonne) :  

| Protocole |	Accès réseau |	Internet |	Transport |	Application |  
|:-:|:-:|:-:|:-:|:-:|
| ARP |	| | | |			  
| Ethernet | | | | |	  			
| ICMP | | | | |				  
| IPv6 | | | | |				  
| DHCP | | | | |				  
| FTP | | | | |				  
| TLS/SSL | | | | |			  	
| POP3 | | | | |				  
| Telnet | | | | |				  
| SNMP | | | | |    

## 5. Maintenir des serveurs dans une infrastructure virtualisée

### 5.1 Explique ce qu'est un cluster d'hyperviseur. Quel est l’intérêt d'une telle structure ?

### 5.2 Qu'est-ce qu'un container ? Donne différentes solutions de conteneurisation.

### 5.3 Que représente les lignes de code ci-dessous ? Comment les utiliser ?

```
FROM ubuntu:latest
# Installation de packages
RUN apt-get update && apt-get install -y \
    bash \
    nano \
    && rm -rf /var/lib/apt/lists/*

# Répertoire local
RUN mkdir /data

# Dossier de travail
WORKDIR /data

# Image en mode interactif
CMD ["bash", "-i"]
```
### 5.4 Pour la copie d'écran ci-dessous, quelle devrait être ta démarche dans une telle situation ?

### 5.5 Que veulent dire les termes PaaS, IaaS, et SaaS ?

### 5.6 Dans la mise en oeuvre d'une solution HA (High Availability), quels sont les élements indispensable ?
  
## 6. Maintenir et sécuriser les accès à Internet et les interconnexions des réseaux

### 6.1 Quel est l'impact des ACL ci-dessous sur la machine 172.16.0.10 ? Peut-on fusionner ces ACL pour n'en former qu'une seule ? Si oui fais-le.  

```
access-list 100 deny icmp host 172.16.0.10 172.17.0.0 0.255.255.255
access-list 100 permit ip any any
access-list 101 deny tcp host 172.16.0.10 host 220.0.0.60 eq www
access-list 101 deny tcp host 172.16.0.10 host 220.0.0.60 eq 443
access-list 101 permit ip any any
```

### 6.2 Pour les commandes ci-dessous les 2 chaînes de caractères en entrée sont de tailles différentes et pourtant la longueur du résultat des commandes est identique. Pourquoi ?

wilder@Ubuntu:~$ echo -n "test message" | sha512sum
950b2a7effa78f51a63515ec45e03ecebe50ef2f1c41e69629b50778f11bc080002e4db8112b59d09389d10f3558f85bfdeb4f1cc55a34217af0f8547700ebf3  -

wilder@Ubuntu:~$ echo -n "ce message n'a aucun rapport avec le précedent !" | sha512sum
0096a6b7b1ff9714c8a0ecd308e1c952ec2f956f0f5ae28ec29b3e6b68f16a127ea4c379c4aafce2e4f97c029874628f4d3376440ae87c34f83b225c973f1d0a  -

### 6.3 Sur l'infrastructure réseau représentée par le schéma ci-dessous, que faut-il faire pour que l'on puisse accéder de manière sécurisée au serveur web depuis internet ?

### 6.4 Quels types de VPN sont représentés dans les illustrations suivantes ?

### 6.5 Par rapport au schéma ci-dessous, complète le texte en dessous avec les bons termes.

Pour envoyer un message privé à Bob, Alice utilise - expression 1 -de Bob pour rendre « illisible » le « texte en clair » et Bob utilise- expression 2 -pour transformer le texte « illisible » en « texte en clair ». Ce processus représente un chiffrement- expression 3 -.

### 6.6 Tu as ci-dessous un extrait d’un guide de configuration d’un tunnel VPN site à site en IPSec/ISAKMP. Traduit ce passage en Français.

When ISAKMP negotiations begin, the peer that initiates the negotiation sends all of its policies to the remote peer, and the remote peer tries to find a match. The remote peer checks all of the peer's policies against each of its configured policies in priority order (highest priority first) until it discovers a match.

### 6.7 En matière de sécurité informatique, indique 3 types de menaces (risques et attaques) auxquelles peut être confronté un SI (ne rentre pas dans les détails).
  
## 7. Mettre en place, assurer et tester les sauvegardes et les restaurations des éléments de l'infrastructure

### 7.1 Qu'est-ce que la règle 3-2-1 ?

### 7.2 Quelles sont les différents types de sauvegardes à mettre en place en entreprise ?

### 7.3 Indiquer les différences entre une sauvegarde, de l'archivage, et un clonage.
  
## 8. Exploiter et maintenir les services de déploiement des postes de travail

### 8.1 Quels avantages apporte la mise en place d'un service centralisé de mises à jour logicielles au sein d'une entreprise ? Indique une solution que tu connais et explique son fonctionnement.

### 8.2 Quels sont les inconvénients liés à la mise en place d'une solution de terminaux clients légers par rapport à des postes fixes ?

### 8.3 Que fait l’exécution de la ligne de commande suivante ? Dans quel contexte est-elle utilisée ?

``C:\Windows\System32\sysprep\sysprep.exe /oobe /generalize /shutdown``

### 8.4 Dans le cadre d'un déploiement de postes clients Linux, quelle est l'utilité d'un dépôt local de paquet ?
