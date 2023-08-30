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

# Commands :

- In wp, run `docker compose up -d`
- `docker build -t <name>` in each dir
- `docker run <name>` in each dir, arg -d in backgroud, or -it to open terminal
- To see images : `docker image ls`
- To see launched containers : `docker ps`, -a to ee the stopped ones
- Connect ssh :
	- On VM:
		- sudo vim /etc/ssh/sshd_config // change port number
		- sudo service ssh restart
	- On iterm:
		- `ssh user@address -p <port>`
- Check if docker is running : `docker run hello-world`
- Check vm IP : `ip addr show` // see enp0s3 inet
- `docker logs <container>` to see logs
- `docker exec -it <container> bash` to see inside container
- In Mariadb: cat  /var/log/mysql/error.log
- `sudo mysqladmin version` see mariadb is installed

# install docker in vm

https://stackoverflow.com/a/48974927

# mariadb

https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-debian-11

# wp cli

https://make.wordpress.org/cli/handbook/guides/installing/

https://make.wordpress.org/cli/handbook/guides/quick-start/

https://www.datanovia.com/en/lessons/using-docker-wordpress-cli-to-manage-wordpress-websites/

# tutos

- tuto inception : https://eneshazr.medium.com/42kocaeli-inception-projesi-docker-wordpress-mariadb-eef9c025e79f
- tuto inception : https://github.com/Forstman1/inception-42

- setup your vm with VB : https://baigal.medium.com/born2beroot-e6e26dfb50ac
- wm config : https://github.com/tblaase/inception
- wp + db (works on host computer in localhost:8000) : https://www.hostinger.com/tutorials/run-docker-wordpress
- bridged + ssh (the previous works on host computer through ssh in vmip:8000) : https://medium.com/@jasonedlewis/accessing-your-vm-from-your-host-machine-via-ssh-b6e355bcd526
- https ? : https://zactyh.medium.com/hosting-wordpress-in-docker-with-ssl-2020-fa9391881f3

# Notes :

- nginx : root /var/www/wordpress to announce to nginx that we use this dir for the first page 
- do not forget wait 10
- ports in compose are shared among the different services and the host machine
- expose in compose are shared among the different services BUT NOT the host machine
