![logo](https://visa.cefim.eu/wp-content/uploads/2023/06/LogoCEFIM-hd.png) 
MAGNAN QUENTIN

# LIVRABLE DE FIN DE PROJET PREPATECH 2023_1 


##  INTRODUCTION
Nous sommes ravis de vous présenter le livrable final de notre projet visant à créer l'infrastrucrure réseau de notre entreprise fictive nommée **INWAVES**.

InWaves est une entreprise innovante de l'industrie musicale, proposant une vaste gamme de produits et de services pour répondre aux besoins des passionnés de musique. Nous proposons une sélection de matériel musical de qualité, des studios d'enregistrement équipés des dernières technologies, des services de location d'équipements audio et de scène, des programmes de formation musicale personnalisés, des solutions de promotion et de marketing pour les artistes, ainsi que des services d'édition de partitions. Notre engagement envers l'excellence et notre dévouement à soutenir la créativité des musiciens font de nous le partenaire idéal, pour toutes les étapes de leur parcours musical. 

Au cours de ce projet, nous avons suivi un processus méthodique pour répondre à chaque point spécifié dans le cahier des charges initial.

## CRÉATION DE L'ENTREPRISE

* ### CRÉER UN POOL DE RESSOURCE COLLABORATIF
 
Pour faciliter la communication, le partage de fichiers et la collaboration au sein de l'équipe. Notre choix s'est porté sur **Google drive**.

![ressourcecollab](/screens/pool%20de%20ressources%20collaboratives.png)

* ### L'IDENTITÉE VISUELLE

Notre logo, représentant une vague, incarnant la fluidité et le dynamisme de la musique, capturant ainsi l'essence même de l'entreprise.
**INWAVES** évoque le mouvement incessant de la créativité musicale, tout en offrant une image de modernité et d'innovation.

![ressourcecollab](/screens/logo%20inwaves%20sans%20fond.png)


* ### L'ORGANIGRAMME DE LA SOCIÉTÉ

Au sein de l'entreprise INWAVES, l'organigramme est structuré pour assurer une gestion efficace et fluide de ses activités. Le pôle Direction, placé au sommet de la hiérarchie, est responsable de définir la vision stratégique de l'entreprise et de prendre les décisions clés pour sa croissance et son développement.

Juste en dessous, le pôle Production est chargé de la création et de la gestion des produits et services musicaux, supervisant tous les aspects de la production, de la conception à la livraison. 

Le pôle Informatique assure le bon fonctionnement des systèmes informatiques et des technologies utilisées par l'entreprise, garantissant ainsi une infrastructure robuste et sécurisée.

Le pôle Commercial se concentre sur la promotion et la vente des produits et services d'INWAVES, développant des stratégies de marketing et de vente pour atteindre les objectifs de vente de l'entreprise. 

Le pôle Ressources Humaines est responsable du recrutement, de la gestion et du développement du personnel, veillant au bien-être des employés et à leur épanouissement professionnel.

Enfin, le pôle Administration et Juridique gère les tâches administratives et légales de l'entreprise, assurant la conformité réglementaire et la gestion efficace des processus administratifs.

Cette structure organisationnelle permet à INWAVES de fonctionner de manière cohérente et harmonieuse, favorisant la collaboration entre les différents départements et assurant le succès continu de l'entreprise dans l'industrie musicale.

![organigramme](/screens/Organigramme.png)

* ### LES FICHIERS CSV POUR REPARTIR LES 2000 UTILISATEURS DANS LEUR SERVICE RESPECTIF

Pour une gestion plus efficace des données nous avons reparti les 2000 employés/utilisateurs dans cinq fichiers CSV ci dessous ↓

![csv](/screens/fichierscsv.png)


La création de cinq fichiers CSV distincts, chacun contenant les noms, prénoms, groupe/pôle de l'organigramme, ainsi que les mots de passe de session par défaut et les noms d'ouverture de session des utilisateurs, revêt une importance cruciale pour la gestion efficace du projet d'importation des utilisateurs dans l'Active Directory.

![csv](/screens/fichier-csv-exemple.png)

## INFRA RÉSEAU WAN 

Tout d'abord, nous avons sélectionné une prise RJ45 disponible dans la salle, qui ensuite a du être brassée dans la salle serveur pour obtenir notre **adresse ip publique**(188.231.29.11).

Une fois la connexion établie, nous avons testé la prise réseau directement avec un poste pour vérifier sa fonctionnalité. Par la suite, nous avons procédé à la recherche d'un PC équipé de deux interfaces réseau qui nous servira de routeur. Nous avons ensuite installé IPFire via une clé USB bootable, et configuré correctement le WAN.

![wan](/screens/wan%20ipfire.jpg)

 Enfin, nous avons effectué un ping vers www.perdu.com, pour confirmer le bon fonctionnement de notre configuration réseau

 ![ping](/screens/ping-perdu-com.png)

 * ### CONFIGURATION LAN 

Nous avons mis en place la configuration **LAN** sans utiliser le **DHCP**, en attribuant une adresse **IPv4** privée de **classe B** avec un **masque de sous-réseau** /22. Cette approche nous permet de distribuer un total de **1022** adresses IP au sein du LAN. 

 ![lan](/screens/Lan%20ipfire.jpg)


## INFRA RÉSEAU LAN 

* ### SWITCH MANAGEABLE

Nous avons choisi le switch manageable D-Link modèle DGS-1210-24 en fonction de nos besoins en matière de connectivité.
Dans l'interface de gestion, nous avons configuré les paramètres de base du switch, tels que sa passerelle, son adresse IP et son masque de sous-réseau. Nous avons également défini un mot de passe sécurisé pour restreindre l'accès au switch.

![switch](/screens/switch-interface.png)



* ### Borne wifi 

Nous avions un besoin crucial d'une borne Wi-Fi en mode serveur DHCP afin de fournir un accès sans fil pratique à notre réseau. En déployant cette solution, nous avons pu offrir à nos utilisateurs la possibilité de se connecter à notre réseau sans avoir à configurer manuellement leur adresse IP, simplifiant ainsi le processus de connexion. 

![bornewifi](/screens/APtplink.png)

Ultérieurement, une fois que notre nouveau système sera entièrement opérationnel, le protocole DHCP sera désactivé et remplacé par une autre méthode de gestion des adresses IP.

![bornewifi](/screens/DHCP%20borne%20wifi%20.png)

## INFRA SYSTÈME N°1 (PHYSIQUE)

* ### NAS

Dans le cadre de notre projet, nous avons entrepris de choisir et de configurer un NAS Synology pour répondre à nos besoins de stockage de données. 

![NAS](https://www.synology.com/img/products/detail/DS923plus/heading.png)

Lors de la configuration du NAS Synology, il était essentiel de lui assigner la bonne adresse IP ainsi que la bonne passerelle afin d'assurer sa visibilité au sein de notre réseau. En configurant manuellement une adresse IP statique, nous avons garanti sa stabilité et sa présence continue au sein de l'infrastructure.

![adressageNAS](/screens/Config-NAS.png)
![adressageNAS](/screens/Config-NAS-DNS-Passerelle.png)

* ### IMPRIMANTE RÉSEAU

Au sein de notre infrastructure réseau, l'incorporation d'une imprimante en réseau s'est révélée indispensable pour satisfaire nos exigences en matière d'impression partagée. Afin de garantir sa disponibilité ininterrompue et son bon fonctionnement au sein de notre réseau, nous lui avons choisi une adresse IP statique.

![imp](/screens/Printer-Brother-L27500W.jpg)
![imp](/screens/Adressage-IP-Static-%20Printer.jpg) 

* ### CONFIGURER UN SERVEUR DE VIRTUALISATION, AVEC PROXMOX

Préparation de la clé USB bootable : Nous avons réussi à créer une clé USB bootable grâce au logiciel Rufus et à l'ISO de Proxmox téléchargé depuis le site officiel.

Une fois la clé prête, nous l'avons insérée dans le PC vierge et avons démarré l'ordinateur. En accédant au BIOS, nous avons configuré le démarrage à partir de la clé USB. Après l'installation, nous avons procédé à la configuration initiale en sélectionnant la langue, en partitionnant le disque dur et en définissant le mot de passe administrateur.


![CUBE](/screens/Cube-Virtualisation-Inwin.jpg) 

 Nous l'avons egalement adressé correctement à l'aide de quelques commandes. 

```console
sudo nano /etc/network/interfaces
```
```console
iface E1000 inet static
    address 172.16.3.248
    netmask 255.255.252.0
    gateway 172.16.3.254
```

Maintenant que notre serveur Proxmox est correctement configuré, il est facilement accessible. Il nous suffit de saisir l'adresse IP statique que nous avons attribuée au serveur suivi du port :8006 dans la barre d'adresse du navigateur pour accéder à l'interface de gestion de Proxmox.

 À l'avenir, nous prévoyons de remplacer l'utilisation de l'adresse IP par un nom de domaine.

![proxmoxview](/screens/proxmox-all-machine.png)

## Infra Système n°2 (virtualisée)

* ### Importance du choix du nom de WorkGroup

![workgroup](/screens/workgroup.jpg)

Un Workgroup est un groupe de postes de travail sur un réseau local partageant des ressources comme des fichiers et des imprimantes. Pour changer le nom d'un Workgroup sous Windows, ouvrez l'Explorateur de fichiers, faites un clic droit sur "Ce PC", puis allez dans "Propriétés". Ensuite, cliquez sur "Paramètres système avancés", puis allez dans l'onglet "Nom de l'ordinateur" et entrez le nouveau nom du Workgroup.


* ### Virtualiser des postes clients

Nous avons virtualisé deux postes clients sur VMware Workstation. Le premier poste utilise Windows 7 32 bits et le second Windows 8.1 64 bits. Étant donné que ces versions de systèmes d'exploitation ne reçoivent plus de mises à jour automatiques via Windows Update, nous avons dû télécharger manuellement les packs de mise à jour nécessaires pour les mettre à jour au maximum. Cette procédure garantit que les systèmes sont sécurisés et fonctionnent de manière optimale malgré la fin du support officiel.

* ### Installer un serveur 2012R2 sur le proxmox

![w2k12](/screens/w2K12.jpg)

Pour installer Windows Server 2012 R2 sur Proxmox, nous avons d'abord téléchargé l'ISO de Windows Server 2012 R2 depuis le site Microsoft Evaluation Center. Ensuite, nous avons accédé à l'interface web de Proxmox et uploadé l'ISO dans le stockage dédié aux ISO. Nous avons créé une nouvelle machine virtuelle (VM) en spécifiant les ressources nécessaires comme le CPU, la mémoire et le disque dur virtuel. Nous avons attaché l'ISO téléchargé comme lecteur CD/DVD de la VM et lancé l'installation de Windows Server 2012 R2, suivant les étapes d'installation à l'intérieur de la VM jusqu'à ce que le système soit opérationnel.

* ### Appliquer sur ces VMs une fiche de recette 

Pour chaque machine virtuelle (VM) créée sous Proxmox avec Windows Server 2012 R2, nous avons appliqué une fiche recette pour configurer la VM en tant que serveur client/serveur. Voici les étapes de notre fiche recette :

1. **Installer les VMWare Tools ou équivalent** : Installer les outils de virtualisation spécifiques pour améliorer les performances et la gestion des VM.
2. **Mettre à jour le système** : Effectuer toutes les mises à jour Windows jusqu'à un certain point, puis désactiver les mises à jour automatiques via le programme `sconfig` pour éviter des modifications inattendues.
3. **Configurer la sécurité d'Internet Explorer** : Désactiver la sécurité renforcée d'Internet Explorer pour les administrateurs afin de faciliter les tâches administratives sur le serveur.
4. **Changer le nom de la machine** : Attribuer un nom unique et pertinent à chaque VM pour une identification facile.
5. **Changer le workgroup** : Modifier le workgroup à "VOTREWORKGROUP" pour une meilleure organisation en réseau.
6. **Configurer le réseau** : Mettre chaque ordinateur dans un réseau privé et désactiver IPv6 pour simplifier la configuration réseau.
7. **Attribuer une IP fixe** : Assigner une adresse IP fixe à chaque VM, avec le DNS configuré sur 1.1.1.1 et la passerelle sur 172.16.3.254, adaptée au contexte du réseau.
8. **Autoriser le Bureau à Distance** : Activer l'accès à distance pour permettre la gestion à distance des VM via le Bureau à Distance.
9. **Installer les logiciels nécessaires** : Utiliser Ninite pour installer des utilitaires essentiels comme 7zip, SumatraPDF, Notepad++, Chrome, et BgInfo.
10. **Configurer le firewall** : Créer des règles entrantes dans le firewall pour autoriser l'ICMP afin que la machine puisse être pinguée.

Cette fiche recette assure que chaque VM est correctement configurée et prête pour un déploiement efficace et sécurisé dans l'environnement réseau.

* ### Créer un partage sur le NAS et le monter sur les postes

![NAS](/screens/Active-Partage-Fichier-NAS.png)




## Active Directory

* ### Installation du Rôle ADDS

![ad](/screens/installation-role-ad.png)

Pour installer le rôle Active Directory Domain Services (AD DS) sur une machine virtuelle Windows Server 2012 R2, nous avons utilisé le Gestionnaire de serveur pour ajouter le rôle AD DS. Cela nous a permis de configurer le serveur en tant que contrôleur de domaine, en créant une nouvelle forêt (inwaves.lan). Une fois le rôle installé, nous avons promu le serveur en tant que contrôleur de domaine, ce qui a impliqué la configuration des paramètres DNS et la création d'un domaine. Le rôle AD DS est essentiel pour gérer et organiser les ressources réseau, permettant l'authentification et l'autorisation des utilisateurs et des ordinateurs dans un environnement de domaine.

* ### Ajout des PC CLients dans le domaine

![domaine](/screens/domaine.jpg)

![domaine](/screens/remonté-pc-client-domaine.png)

Joindre un PC à un domaine Active Directory permet de centraliser la gestion des utilisateurs et des ressources, d'améliorer la sécurité, et de simplifier l'administration du réseau. Les utilisateurs peuvent se connecter avec les mêmes identifiants sur n'importe quel PC du domaine et accéder aux ressources partagées facilement.

L'administrateur peut créer modifier et supprimer des comptes utilisateurs, définir des mots de passe et des politiques de sécurité, attribuer des permissions et des droits d'accès, et appliquer des politiques de groupe pour standardiser les configurations sur tous les ordinateurs du domaine. Cela permet de contrôler qui peut accéder à quelles ressources, de déployer des logiciels, des mises à jour et de surveiller.

* ### Création des OU

![ou](/screens/ou.jpg)

Nous avons ensuite procédé à la création d'Unités Organisationnelles (OU) dans Active Directory pour organiser et structurer les objets de manière logique et fonctionnelle. Par exemple, nous avons créé des OUs pour regrouper les utilisateurs par fonction. Cette organisation nous permet de déléguer efficacement l'administration et d'appliquer des stratégies de groupe spécifiques à chaque groupe d'utilisateurs ou de ressources.

* ### Import des users du CSV dans les OU via un script powershell

![csv](/screens/fichier-csv-exemple.png)

<br>

![script](/screens/scrypt-csv-importation.png)

Nous avons utilisé un script PowerShell pour importer des utilisateurs à partir d'un fichier CSV dans des Unités Organisationnelles (OU) spécifiques dans Active Directory. 
Cela nous a permis d'automatiser le processus d'importation des utilisateurs et de les organiser directement dans les OUs appropriées.

* ### Création de 5 GPO utiles et appliquées sur les postes clients en VMs

![script](/screens/gpo-appliquée.png)


Ces cinq GPO (Group Policy Objects) ont été mises en place pour standardiser et faciliter la gestion des postes clients en VMs dans notre environnement.

La première GPO de gestion de mot de passe permet de définir des politiques de mot de passe strictes, améliorant ainsi la sécurité des comptes utilisateur.

La deuxième GPO est destinée à remonter automatiquement l'inventaire des postes clients vers GLPI, un outil de gestion des actifs informatiques. Cela assure un suivi précis des ressources et simplifie la gestion des parcs informatiques.

![dhcp](/screens/gpo-deploiement-client-glpi.png)

La troisième GPO est utilisée pour définir une page d'accueil par défaut sur un navigateur web spécifique sur tous les postes clients. Cela garantit que les utilisateurs accèdent à une page d'accueil uniforme et pertinente lorsqu'ils ouvrent leur navigateur.

![dhcp](/screens/gpo-page-pardefaut-ouverturenaviguateur.png)

La quatrième GPO permet de déployer un fond d'écran commun sur tous les postes clients, renforçant ainsi l'identité visuelle de l'entreprise et favorisant un sentiment d'appartenance à l'équipe.

![script](/screens/wallpaper-gpo.png)

Enfin, la cinquième GPO est utilisée pour mapper des lecteurs réseau et créer des raccourcis sur les postes clients, simplifiant ainsi l'accès aux ressources partagées et aux applications importantes pour les utilisateurs.

## Windows Server

* ### Héberger le rôle DHCP

![dhcp](/screens/dhcp-adresse.png)

Nous avons utilisé Proxmox pour virtualiser Windows Server 2012R2, qui héberge le rôle DHCP. Cette configuration permet de gérer automatiquement l'attribution des adresses IP au sein de notre réseau. Après avoir créé la machine virtuelle et installé Windows Server 2012R2, nous avons ajouté et configuré le rôle DHCP. Nous avons également configuré un bail d'adresse de 172.16.3.100 à 172.16.3.199, définissant les d'adresses IP disponibles.

* ### Héberger le rôle Serveur de Fichiers

![dhcp](/screens/serveur-rfs.png)

Pour virtualiser Windows Server 2012R2, qui héberge le rôle de serveur de fichiers. Cette configuration permet de centraliser et de gérer efficacement le stockage des fichiers au sein de notre réseau. Après avoir créé la machine virtuelle et installé Windows Server 2012R2, nous avons ajouté et configuré le rôle de serveur de fichiers. Cela inclut la mise en place de quotas pour limiter et surveiller l'espace de stockage par utilisateur ou groupe, et l'application de filtres de fichiers pour contrôler les types de fichiers autorisés, contribuant ainsi à la sécurité et à une gestion efficace des ressources. 

Nous avons créé un disque D: pour le stockage des fichiers et configuré les droits d'accès de manière suivante : les utilisateurs d'une unité d'organisation (OU) ont un accès en lecture/écriture à un dossier commun, tandis que tous les utilisateurs du domaine ont un accès en lecture à un dossier public et un accès en lecture/écriture à leur propre dossier personnel. De plus, les lecteurs des partages sont mappés via des stratégies de groupe (GPO).


![dhcp](/screens/quotas500mo.png)
 Nous avons appliqué des filtres de fichiers pour interdire les fichiers MP3 dans les dossiers communs et personnels.
![dhcp](/screens/interdiction-fichier-mp3.png)
 Nous avons appliqué des filtres de fichiers pour interdire les fichiers MP3 dans les dossiers communs et personnels
 mis en place un quota de 500 Mo pour les partages personnels.

 ![dhcp](/screens/fichier-perso-mapper-au-bureau.png)

 Les dossiers personnels sont mappés directement sur le bureau des utilisateurs

 ![dhcp](/screens/dossier-partagé-ou.png)

chaque service dispose d'un partage commun pour faciliter la collaboration entre eux 

 ![dhcp](/screens/autorisation-pour-acceder-a-une-autre-ou-fichier.png)

 Les personnes d'un service ne peuvent pas accéder aux partages des autres services, à l'exception de leur propre dossier personnel, du dossier commun et du dossier "Info". Cela assure une séparation claire des données entre les services et renforce la sécurité des informations sensibles.

* ### Héberger le rôle IIS

![dhcp](/screens/gpo-page-pardefaut-ouverturenaviguateur.png)


 avons installé le rôle IIS (Internet Information Services). Le serveur héberge désormais une simple page web index.html, accessible en HTTPS avec HSTS (HTTP Strict Transport Security).

Nous avons configuré la page index.html comme page par défaut des clients via une GPO (Group Policy Object), assurant ainsi que tous les utilisateurs accèdent à cette page lorsqu'ils naviguent sur le réseau intranet.

Cette solution offre une manière simple et sécurisée de fournir aux utilisateurs un point central d'accès à des informations essentielles via une page web accessible uniquement en HTTPS avec HSTS, renforçant ainsi la sécurité des communications sur le réseau interne.

## Linux

* ### Installer un Linux Debian 11 ans GUI sur qui va héberger le futur site web front-end d'INWAVES

nous nous lançons dans la mise en place du serveur qui hébergera notre futur site web front-end sur www.votredomaine.lan. Pour cela, nous avons choisi de virtualiser un environnement Debian 11 sans interface graphique sur Proxmox.

Après avoir créé la machine virtuelle et défini ses ressources, nous avons entamé l'installation de Debian 11. Optant pour une installation minimale, nous avons évité d'inclure une interface graphique afin de maximiser les performances et la sécurité du serveur.

Une fois Debian installé, nous nous sommes penchés sur la configuration réseau pour assurer l'accessibilité du serveur sur notre réseau local. C'est une étape cruciale pour que notre site web soit accessible depuis tous les postes de l'entreprise. Cela implique de définir une adresse IP statique (172.16.3.243) pour le serveur Debian 11 et de configurer les paramètres réseau correspondants, tels que la passerelle (172.16.3.254) par défaut et les serveurs DNS (inwaves.lan en 172.16.3.247).

* ### Installer les binutils (zip,curl,lynx,dnsutils,net-tools,git,screen,nmap)

Nous avons ensuite installé les binutils, ainsi que d'autres outils utiles tels que zip, curl, lynx, dnsutils, net-tools, git, screen et nmap grace à la commande : 

```console
apt install
```

* ### Installer un Apache sur ce serveur et créer un VHost qui point vers /home/siteweb/www

Pour installer Apache 2 sur votre serveur Linux, vous pouvez utiliser :

```console
apt install apache2
```

![apache2](/screens/apache2.jpg)


![chemin vhost](/screens/chemin-vhost.png)

Creer votre repertoire avec : 

```console
mkdir -p /home/wwwinwavescefimninja/wordpress
```

 Acceder au fichier de configuration pour votre VirtualHost dans le répertoire des sites disponibles d'Apache : 


```console
 sudo nano /etc/apache2/sites-available/wwwwinwavescefimninja.conf
```

Dans ce fichier, ajoutez les configurations suivante :

```console
 ServerName WWW.inwaves.lan
    DocumentRoot /home/wwwinwavescefimninja/wordpress

    <Directory /home/wwwinwavescefimninja/wordpress
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
```


* ### Créer une règle HSTS sur ce serveur pour la redirection http-->https

![vhost](/screens/hsts-sur-1er-vhost.png)

La mise en place d'une règle HSTS sur un serveur web est essentielle pour garantir que les communications avec le site se font de manière sécurisée, même si l'utilisateur oublie de spécifier HTTPS dans l'URL ou est redirigé depuis un lien HTTP.

Il suffit d'ajouter dans le fichier .conf vu precedemement la commande : 

```console
 RedirectPermanent / https://votredomaine


```

 De plus Pour garantir que les connexions HTTPS utilisent le certificat auto-signé, vous devez ajouter les chemins vers le certificat et la clé privée généré par OpenSSL et Apache dans le fichier de configuration Apache. Cela se fait en modifiant le fichier de configuration .conf associé au site web.


Ajouter la ligne : 

```console
SSLCertificateFile  /etc/apache2/apache.pem
```


* ### Rendre accessible de l'exterieur

![nat](/screens/regle-ipfire-pour-rendre-accessible-de-lexterieur.png)

Pour rendre notre site web accessible depuis l'extérieur de notre réseau local, nous devons configurer une règle NAT (Network Address Translation) sur notre pare-feu (firewall). Cette règle NAT permettra de rediriger le trafic entrant destiné à l'adresse IP publique de notre réseau vers l'adresse IP privée de notre serveur web hébergé localement

Sur le pare-feu (ipfire), la règle NAT redirige les requêtes HTTP (port 80) et HTTPS (port 443) reçues sur l'adresse IP publique vers l'adresse IP privée du serveur web.

* ### Certificat signé par Let's Encrypt

![lets](/screens/regle-hsts-et-lets-encrypt-2ieme-vhost.png)

Pour obtenir un certificat Let's Encrypt, nous avons installer un outil nommé Certbot sur notre serveur. Certbot simplifie le processus d'acquisition et de renouvellement des certificats SSL/TLS. Une fois Certbot installé, nous lui demandons d'obtenir un certificat pour notre domaine. Certbot communique alors avec les serveurs de Let's Encrypt pour prouver que nous possédons le domaine en question

Après cela Let's Encrypt nous fournit un certificat signé et une clé privée. nous avons plus qu'a la copier dans le fichier .conf de notre site comme vu precedemment avec le certificat auto-signé.


![certif nav](/screens/certificatletsenscrypt.png)

Avec l'installation du certificat signé par Let's Encrypt, les navigateurs considèrent désormais le site comme sécurisé, éliminant les messages d'avertissement précédents, et le certificat peut être consulté pour vérifier son authenticité.


* ### Installer MariaDB, créer un utilisateur qui aura tout les droits sur la future DB de votre CMS et aucun ailleurs

![maria](/screens/creation-user-mariadb-scrypt.png)

Nous avons installé MariaDB sur notre serveur en utilisant le gestionnaire de paquets de notre distribution Linux. Une fois MariaDB en place, nous avons accédé au client MariaDB avec les privilèges administrateur. Nous avons ensuite créé une base de données dédiée à notre futur CMS. Pour gérer cette base de données, nous avons créé un nouvel utilisateur en spécifiant un nom d'utilisateur et un mot de passe sécurisés. Cet utilisateur a été configuré pour avoir tous les droits uniquement sur cette nouvelle base de données


* ### Installer la version la plus récente de PHP

Nous avons ensuite installé la dernière version de PHP avec la commande :

```console
sudo apt install php
```

* ### Installer PhpMyAdmin

Nous avons ensuite installé PhpMyAdmin avec la commande :

```console
sudo apt install phpmyadmin
```
Cela nous a permis de disposer d'une interface web conviviale pour gérer nos bases de données MariaDB

* ### Installer Wordpress et faire une page d'accueil pour votre site

Nous avons ensuite installé WordPress en utilisant la commande :

```console
sudo apt install wordpress
```

![maria](/screens/login-wordpress.png)

Une fois arrivés sur l'interface de WordPress, nous avons été invités à nous connecter en utilisant les informations d'identification de l'utilisateur que nous avions créé précédemment dans MariaDB.

![maria](/screens/page-acceuil-wordpress.png)

![maria](/screens/editor-site-web-wordpress.png)

Ensuite nous avons pu accéder au tableau de bord de WordPress et commencer à personnaliser notre site web selon nos besoins et nos préférences.

![maria](/screens/paged_accueilworpress.png)


Nos visiteurs peuvent désormais accéder à notre site web WordPress et naviguer à travers son contenu de manière fluide et sécurisée.


## GLPI

* ### Installer sur un Linux Debian sans GUI le GLPI et le faire pointer sur help.votredomaine.lan (avec certificat local auto-signé , HSTS et HTTPS)
![vhost](/screens/certificat-hsts-autosingé-GLPI.png)

Nous avons installé GLPI sur un serveur LAMP(Linux Apache MariaDB PHP) Debian sans interface graphique exactement comme le serveur wordpress. Pour que les utilisateurs puissent accéder à GLPI via un navigateur web, nous avons configuré l'adresse IP du serveur GLPI vers le nom de domaine help.inwaves.lan.

Pour intégrer cette configuration dans notre Active Directory, nous devons ajouter une entrée DNS pour le nom de domaine help.votredomaine.lan, pointant vers l'adresse IP du serveur GLPI(172.16.3.245).

Pour le certificat auto-signé du serveur GLPI, nous avons suivi exactement la même procédure que celle utilisée pour le serveur web WordPress, Nous avons généré un certificat SSL auto-signé pour le serveur GLPI en utilisant les outils fournis par OpenSSL et Apache.

* ### Synchronisation du GLPI avec le DC1 pour remonter les utilisateurs.

![userglpi](/screens/user-remonté-GLPI.png)


Pour synchroniser GLPI avec notre contrôleur de domaine DC1 et remonter les utilisateurs, nous avons configuré l'intégration LDAP de GLPI. En accédant à l'interface d'administration de GLPI, nous avons renseigné les informations nécessaires pour établir une connexion avec notre Active Directory, telles que l'adresse du serveur, le port et les informations d'identification appropriées. Une fois la connexion établie, GLPI a pu interroger le contrôleur de domaine DC1 pour récupérer et synchroniser les utilisateurs du domaine.
<br><br>

![remontevm](/screens/remontée-pc-client-GLPI.png)


Pour permettre à GLPI de faire une remontée d'inventaire des PC clients en VM, nous avons déployé l'agent GLPI sur tous les postes du domaine. Nous avons configuré une GPO (Group Policy Object) dans notre Active Directory pour automatiser l'installation de cet agent sur chaque machine cliente. Grâce à cette GPO, l'agent GLPI est automatiquement installé et configuré sur tous les PC clients dès qu'ils rejoignent le domaine. Une fois installés, les agents commencent à envoyer régulièrement des données d'inventaire matériel et logiciel à GLPI, permettant une gestion centralisée et une visibilité complète de notre parc informatique virtuel.

* ### FAQ GLPI

![faqglpi](/screens/FAQ-GLPI.png)

Nous avons mis en place une foire aux questions (FAQ) dans GLPI. Cette FAQ sert à centraliser et à diffuser les réponses aux questions récurrentes, ce qui aide à réduire la charge de travail du support technique et à fournir rapidement des solutions aux utilisateurs.


* ###  Workflow complet d'un ticket pour un usager de l'AD

![faqglpi](/screens/Problem-discover.png)

Lorsqu'un utilisateur découvre un problème, il peut soumettre un ticket via l'interface GLPI(self service). 


![faqglpi](/screens/Problem-Solution-Statut-en-cours.png)

Si une réponse ou une solution est proposée, le ticket est mis en attente pour permettre à l'utilisateur de tester ou de valider la solution. 


![workglpi](/screens/ticket-clos.png)

Une fois la solution confirmée, le ticket est clos, assurant ainsi un suivi et une résolution systématique des incidents signalés.

## Infra Système n°3 (update)























