# Inception

https://tuto.grademe.fr/inception/

- Docker :
	- Modeliser chaque conteneur sous la forme d'une image que l'on peut stocker localement
	- Un conteneur est une MV sans noyau (OS, GC, reseau...)
	- Un conteneur ne contient que l'application *et* les dependances de l'application
- Une image docker c'est un dossier qui contient le Dockerfile.
- [Official image of wordpress](https://hub.docker.com/_/wordpress)
- Dockerfile [keywords](https://www.nicelydev.com/docker/mots-cles-supplementaires-dockerfile#:~:text=Le%20mot%2Dcl%C3%A9%20EXPOSE%20permet,utiliser%20l'option%20%2Dp%20.):
	- FROM : indique l'OS sous lequel doit tourner la MV, premier mot-clef et est obligatoire
	- RUN : permet de lancer une commande sur la MV, en genral pour mettre a jour les ressources de VM comme apk ou ajouter vim, curl, sudo
	- COPY : copier un fichier a partir du ./ ou se trouve de Dockerfile et ou la copier dans la MV. 
	- EXPOSE : informe Docker que le conteneur ecoute sur les ports reseaux specifies au moment de l'execution. EXPOSE ne rend pas les ports du conteneur accessibles a l'hote
	- ENTRYPOINT : lancer une commande arguments par arguments au lancement de celui-ci
- Docker Compose :
	- Outil developpe pour aider a definir et a partaer des application multi-conteneurs
	- Gerer des app qui utilisent plusieurs containers et de communiqer entre eux
- Best practices to write Dockerfiles : https://docs.docker.com/develop/develop-images/dockerfile_best-practices/
- Best practices for PID 1 : https://medium.com/@boutnaru/the-linux-process-journey-pid-1-init-60765a069f17
- Transport Layer Security (TLS, ou Securite de la couche de transport) permet
	- l'authentification du serveur
	- la confidentialite des donnees echangees
	- l'integrite des donnes echangees
	- C'est ce protocole qui change http et https
- 
Run WP, MDB, NGINX

# Commands :

In wp, run `docker compose up -d`

1. `docker build -t <name>` in each dir

2. `docker run <name>` in each dir, arg -d in background

To see images : `docker image ls`

To see launched containers : `docker ps`, -a to ee the stopped ones


