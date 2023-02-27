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
- IP est la partie qui obtient l'adresse (ex. phone n#)
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
- Masque reseau :
	- Le masque est un separateur entre la partie reseau et la partie machine d'une
	  adresse IP
	- Le masque determine le nb de machines d'un reseau
	- On choisira le masque en fonction du nombre de machines installes dans le
	  reseau
	- 207.142.131.245/255.255.255.0 designe la machine d'adresse 245 sur le reseau d'adresse
	  207.142.131.0
	- Notation plus courte : IP/nb de bits a 1, ex. 207.142.131.245/24
	- IP : 192.168.150.35 > masque : 255.255.255.0 > adresse reseau :
	  192.168.150.0 > adresse de diffusion : 192.168.150.255

https://github.com/tblaase/Net_Practice#contents
- Particularite du masque : une fois qu'un bit est `0`, il ne peut y avoir de
  `1` apres, ainsi `255.255.255.0` est valide, `255.255.128.128` n'est pas
  valide
- Fourchettes d'IP speciales :
	- Private network :
		- `10.0.0.0 - 10.255.255.255`
		- `172.16.0.0 - 172.31.255.255.255`
		- `192.168.0.0 - 192.168.255.255`
	- Loopback adresses :
		- `127.0.0.0 - 127.255.255.255`

# Level 1

- Change adresse machine

# Level 2

- Get same mask
- Change adresse machine
- Change 1er octet IP valid & adresse machine
 
# Level 3

- Check mask :
	- Copy mask everywhere
	- If 255, l'IP reste la meme

# Level 4

- Copy-paste mask
- Then IP from A1 while changine adresse machine

# Level 5

- Same masks
- Default to router IP

# Level 6

- Same masks, get IPs, corresponding IP between routeur and tables
- Default router
- Internet IP corresponding to mask : 128, 256-128 = 128 = 25 bit

# Level 7

- Get a mask : if 3 subnets, 4 is ok, so 30th bit = 4, 256-4 = 252
- Change IPs of each interface while connecting tables

# Level 8

- R2 IP from default to R13 and R21 61, change mask to 252 because 2
- Change IPs of the two underlying networks, 12, 1718 and match masks and IPs
- Internet destination to R12 IP
- R1 : R21 IP.0/27 to IP R21

# Level 9

- Take R13 and change IPs
- Begin by C, 9 instead of 10 and connect to internet (router masks & IPs, C1 masks
  and IP, then change to 9) amd 
- Connect ABR11 but change private co - take A1 IP
- D default to R23, then take R23 IP, change to 0/18

# Level 10

- Set S1
- Set H41
- Change R13
- Set R22 to 193 and masks
- Internet to 0/24 then R1
