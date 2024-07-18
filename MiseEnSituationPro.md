# 🔧 Equipements à disposition

Dans ce checkpoint, tu interviens sur une infrastructure réseau constituée de différentes VM.

Pour les utiliser :

    Télécharge les fichiers OVA correspondant à partir de ce lien : TéléchargementVM
    Importe les machines virtuelles dans Virtualbox
    Démarre-les lorsqu'elles sont necessaire

Listes des VM :
| Nom |	OS |	Fonction |	Paramètres | IP |	Utilisateurs |  
|:-:|:-:|:-:|:-:|:-:|:-:|  
| SRVWIN01 |	Windows Server 2022 |	 AD-DS, DNS, DHCP |	172.16.10.10/24 |	administrator |  
| SRVLX01 |	Linux Debian 11 |	Glpi, serveur web |	172.16.10.15/24 |	root, wilder |  
| SRVLX02 |	Linux Red Hat 7 |	IPBX |	172.16.10.5/24 |	root |  
| CLIENT01 |	Windows 10 |	- |	DHCP |	administrateur, wilder |  

Indications supplémentaires sur les VM :

    Tous les mots de passe des comptes utilisateurs du tableau ci-dessus sont P@ssw0rdTssR
    Tous les outils et logiciels necessaires sont installés sur les machines
    Les différentes mise en veille des machines Windows sont désactivées

N'hésite pas à cloner une VM, ou à faire un snapshot si tu n'est pas sûr de tes manipulations.

# 💪 Challenge  

## 1. Adaptation de script

Machine concernée : CLIENT01
Intervention 1

Sur la machine CLIENT01, tu trouveras le script PowerShell C:\Scripts\GetIpConfiguration.ps1.
Dans ce script, remplace les commentaires # XXX par un commentaire qui explique ce que fait la ligne ou le paragraphe situé en dessous.

Question 1 :
Insère la ou les copies d'écran du script avec tes commentaires.
Intervention 2

Fais 2 copies de ce script (nommées GetIpConfiguration_1.ps1 et GetIpConfiguration_2.ps1) et modifie les pour avoir en sortie écran :

    L'alias d'interface
    L'adresse IP v4
    Le masque de sous-réseaux
    Le statut du DHCP

En complément, tu dois exporter les informations trouvées dans un fichier de sortie. Ce fichier se nomme export1.csv pour le premier script, et export2.csv pour le second. Ils sont placés au même endroit que les scripts, et les informations sont séparées par des ";" (point-virgule).

L'affichage de sortie du script GetIpConfiguration_1.ps1 doit être exactement comme ci-dessous (avec les attributs dans l'ordre) :

InterfaceAlias      IPAddress       PrefixLength      Dhcp

--------------      ---------       ------------      ----

Ethernet            172.16.10.60    24                Enabled

L'affichage de sortie du script GetIpConfiguration_2.ps1 doit être exactement comme ci-dessous (avec le contenu de chaque ligne dans l'ordre) :

Type d'interface : Ethernet

Adresse IP :	      172.16.10.60/24

Statut du DHCP :   Enabled

Voilà ce que peut être le contenu du fichier export1.csv :

Ethernet;172.16.10.60;24;Enabled

De même, voilà ce que peut être le contenu du fichier export2.csv :

Ethernet;172.16.10.60/24;Enabled

### Question 2 :
Insérer les copies d'écran du script GetIpConfiguration_1.ps1, de l'affichage de sortie, et du contenu du fichier export1.csv .

### Question 3 :
Insérer les copies d'écran du script GetIpConfiguration_2.ps1, de l'affichage de sortie, et du contenu du fichier export2.csv .

  
## 2. Active Directory

Machines concernées : SRVWIN01 et CLIENT01
Intervention 1

Modifie la configuration du service DHCP sur le serveur pour que le client ai l'adresse IP dynamique 172.16.10.100.

### Question 4 :
Insérer les copies d'écran de la configuration DHCP sur le serveur, ainsi que le résultat de la commande "ipconfig/all" sur le client.
Intervention 2

On souhaite mettre un fond d'écran sur les machines clientes suivant le service dans lequel se trouve les utilisateurs.
En te basant sur les GPO existantes, créer une GPO USER-Interface-Wallpaper-Gestion pour les personnes ayant un compte dans l'OU Gestion.

Cette GPO :

    Affiche l'image C:\Content\Gestion.jpg en fond d'écran
    A une application sécurisée par des groupes de filtrage (contenant les utilisateurs de l'OU Gestion)

### Question 5 :
Insérer les copies d'écran de la configuration de la GPO (contenu et partie filtrage), ainsi que le résultat sur le client.
Intervention 3

Faire en sorte que le serveur IPBX soit accessible par le nom ipbx.lab.lan.

### Question 6 :
Insérer la ou les copies d'écran de la configuration sur serveur, ainsi que le résultat de la commande "ping" sur le client.

  
## 3. Serveur Linux

Machines concernées : SRVLX01 et CLIENT01

Tu peux te servir du serveur SRVWIN01 pour délivrer un paramétrage IP à la machine cliente CLIENT01.
Si tu souhaite t'en passer, n'oublie pas de paramétrer la machine CLIENT01 en IP fixe.

Intervention 1

Afin d'améliorer la sécurité de l'accès SSH au serveur, fais les modifications suivantes :

    Interdire l'accès avec le compte root
    Interdire l'accès par mot de passe
    Autoriser l'accès par clé de chiffrement
    Modifier le port TCP de ce service pour qu'il soit accessible sur le numéro 22504

### Question 7 :
Insérer la ou les copies d'écran de la configuration sur le serveur, ainsi que l'application dans une connexion SSH depuis le client vers le serveur.
Intervention 2

Sur le home directory de root tu as :

    Un fichier LisezMoi qui contient des informations sur les serveurs/applications installés
    Un fichier En-Travaux.tar.gz qui contient une image et l'index d'un site temporaire

Ce site temporaire doit s'afficher à la place du site intranet.

### Question 8 :
Insérer la copie d'écran de l'application sur le client lors de la visite du site web.

  
## 4. Téléphonie

Machines concernées : SRVLX02, SRVWIN01, et CLIENT01

Pour les interventions, 2 softphones vont être utilisés, un sur chacun des PC Windows (client et serveur).
Intervention 1

Créer le compte de l'utilisateur Miguel Hernandez avec le numéro 80104 sur l'IPBX.

### Question 9 :
Insérer la ou les copies d'écran de la configuration du compte sur l'IPBX, ainsi que le résultat sur le client.
Intervention 2

Mettre en service les 2 softphones avec les lignes de Miguel Hernandez et d'Emma Chen.

### Question 10 :
Insérer la ou les copies d'écran attestant une communication réussie entre les 2 utilisateurs.
