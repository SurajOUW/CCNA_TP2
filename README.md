## I. Exploration locale en solo 
### 1.Affichage d'informations sur la pile TCP/IP locale

Pour afficher le nom, l'adresse MAC et l'adresse IP de l'interface Wi-Fi et Ethernet il faut ouvrir le "powershell"(sous windows) et inscrire la commande suivante : ipconfig /all

* Wi-Fi
* * nom : Intel(R) Dual Band Wireless-AC 8265
* * adresse MAC : F8-59-71-94-D1-C6
* * adresse IP : 192.168.1.55 
* * adresse réseau : 192.168.0.0
* * adresse de broadcast : 192.168.1.255

* Ethernet
* * nom : Intel(R) Ethernet Connection (4) I219-V
* * adresse MAC : 54-E1-AD-3D-1C-45
* * adresse IP : Aucune
* * adresse réseau : Aucune
* * adresse broadcast : Aucune

### Trouver comment afficher les informations sur une carte IP (change selon l'OS)

Pour les informations d'une carte IP (ici Windows), nous allons procéder à une petite recherche dans le panneau de configuration > Réseau et Internet > Centre Réseau et Partage. Une fois dedans, un clic sur les paramètres de la carte et une liste des détails des connexions réseau apparait, on choisit un statut à la carte, et ce dernier onglet va nous montrer les paramètres réseau recherché.

## II. Exploration locale en duo
### 1. Prérequis
Tout d'abord nous avons retiré les pare-feux

### 2. Câblage

Nous avons procédé au câblage entre les deux machines grâce à un câble RJ45

### 3. Modification d'adresse IP

*  Modifiez l'IP des deux machines pour qu'elles soient dans le même réseau : 

Aller dans : Panneau de configuration > Réseau et Internet > Connexions réseau > clic droit sur "Ethernet" puis clic sur "Propriété" > clic sur "Internet Protocol Version 4" puis clic sur Propriétés.

Pour le PC_1 nous avons mis l'adresse IP suivante : 192.168.0.1 et pour le PC_2 192.168.0.2 .
Pour le masque de sous-réseau nous avons mis : 255.255.255.0 .

* Vérifiez à l'aide de commandes que vos changements ont pris effet :

Pour cela il suffit d'aller dans le terminal et d'y inscrire "ip config" (sous windows)!

* Utilisez ping pour tester la connectivité entre les deux machines :

Dans cette partie il suffit d'écrire dans le terminal "ping {adresse ip de l'ordinateur connecté}" soit ici "ping 192.168.0.2" et nous pouvons observer que le pc nous confirme bien le test de 4 paquets.

* Testez avec un /20, puis un /24, puis le plus petit réseau que vous trouvez

* Inventez un nouveau réseau


### 4. Utilisation d'un des deux comme gateway

* Sur le PC qui n'a plus internet, sur la carte Ethernet, définir comme passerelle l'adresse IP de l'autre PC :
Nous avons déconnecté le PC_2 et dans la case "Passerelle par défaut :" qui est dans les propriétés IPV4 de la carte Ethernet nous avons rentré l'adresse IP du PC_1 qui est 192.168.0.49
