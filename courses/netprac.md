# Netpractice

# TCP/IP

https://www.avast.com/fr-fr/c-what-is-tcp-ip

- Transmission Control Protocol/Internet Protocol
- Ensemble de regles normalisees (protocoles) permettant aux ordinateurs de communiquer sur
  un reseau tel qu'internet
	- Comment demarrent conversation ?
	- A qui le tour ?
	- Comment sait que message correctement transmis ?
	- Comment terminent conversation ?
- IP est la partie qui obtien l'adresse (ex. phone n#)
- TCP est responsable de la livraison des donnees une fois que cette IP a ete
  trouvee (ex. techno faisant sonner le tel)
- Pas besoin de les separer
- TCP/IP decompose message en *paquets* qui sont envoyes par differents itineraire
  si encombre et rassembles a l'autre ordi
- TCP/IP divise les differentes taches de communication en 4 *couches*
	- But : garder l'ensemble standardise (ex. place des pedales dans voiture)
	1. Couche de liaison de donnees / interface reseau ou couche physique :
		- Gere les parties physiques de l'envoi de la reception de donnees
		  (cable Ethernet, reseau sans fil, carte d'interface reseau, pilote
		  periph etc.)
	2. Couche Internet/ reseau :
		- Controle le mouvement des paquets sur le reseau
	3. Couche transport :
		- Fournit connexion des donnes fiables entre deux appareils.
		- Divise les donnes en paquets
		- Accuse reception des paquets recus
		- S'assure qe ce dernier accuse reception des paquets qu'il recoit
	4. Couche application :
		- Application avec laquelle l'user interagit
		- Ces applis n'ont pas besoin de se proccuper des details de la
		  communication
- Quand paquets transmis entre ordinateurs, vulnerables car les autres peuvent
  le voir (reason why do not use public wifi when send data)

https://fr.wikibooks.org/wiki/R%C3%A9seaux_TCP/IP/Adressage_IP_v4
http://math.univ-lyon1.fr/irem/Formation_ISN/formation_reseau/couche_reseau/masque.html
- IP est ecrit sur 4 octets entre 0 et 2^32 : 11110000 11110000 11110000
  11110000
- Constitue de deux parties : adresse reseau (3 premiers octets) et adresse
  machine (dernier octet)
- Le masque est un separateur entre la partie reseau et la partie machine d'une
  adresse IP
- Le masque determine le nb de machines d'un reseau
- On choisira le masque en fonction du nombre de machines installes dans le
  reseau
- 207.142.131.245/255.255.255.0 designe la machine d'adresse 245 sur le reseau d'adresse
  207.142.131.0
- Notation plus courte : IP/nb de bits a 1, ex. 207.142.131.245/24
- 
