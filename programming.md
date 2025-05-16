# Programming

## Table of Contents

<!-- vim-markdown-toc GFM -->

* [Tabby](#tabby)
* [MonitorControl](#monitorcontrol)
* [Rectangle](#rectangle)
* [Yabai](#yabai)
* [AutoRaise](#autoraise)
* [GitStatusRef](#gitstatusref)
* [Kubernetes](#kubernetes)
	* [Udemy, Kubernetes for the Absolute Beginners - Hands-on https://cern.udemy.com/course/learn-kubernetes/learn/lecture/22027940#overview](#udemy-kubernetes-for-the-absolute-beginners---hands-on-httpscernudemycomcourselearn-kuberneteslearnlecture22027940overview)
		* [K8 overview](#k8-overview)
		* [K8 Concepts](#k8-concepts)
		* [K8 concepts - Pods, replicasets, deployments](#k8-concepts---pods-replicasets-deployments)
		* [Networking](#networking)
		* [Services](#services)
		* [Microservices Architecture](#microservices-architecture)
		* [K8 on Cloud](#k8-on-cloud)
	* [Udemy, Kubernetes Certified Application Developer (CKAD) with Tests](#udemy-kubernetes-certified-application-developer-ckad-with-tests)
		* [2. Core Concepts](#2-core-concepts)
		* [3. Configuration](#3-configuration)
		* [4. Multi-Container Pods](#4-multi-container-pods)
		* [5. Observability](#5-observability)
		* [10. Helm Fundamentals](#10-helm-fundamentals)
		* [(admin) 12. Helm Basics](#admin-12-helm-basics)
* [Web performance](#web-performance)
	* [Ultimate guide to web performance](#ultimate-guide-to-web-performance)
* [Python](#python)
	* [Python 101: Learn the 5 Must-Know Concepts](#python-101-learn-the-5-must-know-concepts)
	* [Ecrivez du code python maintenablehttps://openclassrooms.com/fr/courses/7160741-ecrivez-du-code-python-maintenable](#ecrivez-du-code-python-maintenablehttpsopenclassroomscomfrcourses7160741-ecrivez-du-code-python-maintenable)
	* [Django](#django)
		* [Débutez avec le framework Django :](#débutez-avec-le-framework-django-)
		* [Mettez en place une API avec Django REST Framework](#mettez-en-place-une-api-avec-django-rest-framework)
	* [Flask](#flask)
		* [Designing a RESTful API with Python and Flask](#designing-a-restful-api-with-python-and-flask)
		* [Flask mega-tutorial I: Hello-World](#flask-mega-tutorial-i-hello-world)
		* [Flask meta-tutorial IV: Database](#flask-meta-tutorial-iv-database)
		* [Flask mega-tutorial VII: Error Handling](#flask-mega-tutorial-vii-error-handling)
		* [Flask mega-tutorial XV: A better app structure](#flask-mega-tutorial-xv-a-better-app-structure)
* [MySQL](#mysql)
	* [mysql tutorial for beginners, full course](#mysql-tutorial-for-beginners-full-course)
* [rest](#rest)
	* [saison 20-21- part 3 - web services rest concepts de base :](#saison-20-21--part-3---web-services-rest-concepts-de-base-)
	* [adopter les api rest pour vos projets web :](#adopter-les-api-rest-pour-vos-projets-web-)
* [unity](#unity)
	* [20 unity tips in 10 min](#20-unity-tips-in-10-min)
	* [10 unity tips you (probably) didn't know about](#10-unity-tips-you-probably-didnt-know-about)
	* [scriptable objects](#scriptable-objects)
	* [ml-agents](#ml-agents)
* [github working in group setup](#github-working-in-group-setup)
* [how to learn (...) without following tutorials ?](#how-to-learn--without-following-tutorials-)
* [mastering the vim language](#mastering-the-vim-language)

<!-- vim-markdown-toc -->

# [Tabby](https://tabby.tabbyml.com/docs/installation/apple)
tabby serve --device metal --model StarCoder-1B

# [MonitorControl](https://github.com/MonitorControl/MonitorControl)
Open 'MonitorControl' and control any monitor (I use it for brightness mainly)

# [Rectangle](https://rectangleapp.com/)

# [Yabai](https://github.com/koekeishiya/yabai)
https://flat-pasta-dc7.notion.site/Yabai-8da3b829872d432fac43181b7ff628fc

# [AutoRaise](https://github.com/sbmpost/AutoRaise)

# [GitStatusRef](https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/)

# Kubernetes

- [Cheatsheet](https://kubernetes.io/docs/reference/kubectl/quick-reference/)

## Udemy, Kubernetes for the Absolute Beginners - Hands-on https://cern.udemy.com/course/learn-kubernetes/learn/lecture/22027940#overview

### K8 overview
- Kubernetes is a container orchestration technology used to orchestrate the deployment and management of hundreds of thousands of containers in a clustered environment
- Node (Minions) = worker machine where containers will be launched by K8
- Cluster = a set of nodes grouped together
- Master is another node with K8 installed and configured as a master
- Components:
	- API server (m): frontend for K8 to interact with K8 server
	- etcd (m): distributed reliable key-value store to store all data used to manage the cluster, responsible for implementing locks within the cluster to ensure that there are no conflicts bw the Masters
	- scheduler (m): distribute work across multiple nodes
	- controller (m): notice and responde when nodes, containers or end points goes down
	- container runtime (w): docker
	- kubelet (w): agent running each node in the cluster, make sure that containers are running on the nodes as expected
- `kubectl run hello-minikube`
- `kubectl cluster-info`
- `kubectl get nodes` + `-o wide` (for OS)
- rkt uses Container Runtime Interface whereas docker uses `dockershim` (until 1.24)
- `nerdctl` provides a Docker-like CLI for containerD, supportes docker compose
- `crictl` provides a CLI for CRI compatible container runtimes, debugging tool
	- `crictl pods`

### K8 Concepts
- Pod is smallest object to be created in K8
- Pods have a 1-1 interaction with a node/container
- A pod can contain multiple containers of different kinds
- `kubectl run nginx --image=nginx` creates nginx image from cloud
- `kubectl get pods -o wide`
- `kubectl describe pod <name>`
- `kubectl get deployments` # list deployments
- `kubectl get services <name>` # see type, ip, ports of <name>
- `minikube start`
- `minikube service <name>` # deploy
- `minikube pause/unpause`
- `minikube stop`
- `minikube delete services <name>`
- `minikube delete --all`
- Minikube handbook : https://minikube.sigs.k8s.io/docs/handbook/

### K8 concepts - Pods, replicasets, deployments
- In YAML, always :
	- `apiVersion` (e.g., v1, v1, apps/v1, apps/v1),
	- `kind` (e.g., Pod, Service, ReplicaSet, Deployment), 
	- `metadata` (with `name`, `labels` [app, type], etc.), 
	- `spec` (e.g., `containers` [name, image])
- Pods:
	- `kubectl create -f <file.yml>` (imperative management, tells exactly how to do smth, e.g., step-by-step instructions – to use when quick one-offs, debug, learning)
	- `kubectl apply -f <file.yml>` (declarative management, tell what you want and it figures out how to do it, e.g., "make sure it is done" – for prod, automation, gitops, repeatability)
- Replicaset:
	- Replication Controller (Older tech) | Replica Set (New way to setup replication)
	- `kubectl get replicationcontrollers`
	- ReplicaSet must have `selector`, it can indeed monitor another pod that was created before, it is a process that monitor the pods
	- To change n° of replicas
		- `kubectl replace -f <def.yml>`
		- `kubectl scale --replicas=6 -f <def.yml>`
		- `kubectl scale --replicas=6 replicaset <rs-name>`
	- `kubectl describe replicaset <rs-name>`
	- `kubectl edit replicaset <rs-name>`
- Deployment:
	- When you deploy, it creates replicaset
	- `kubectl get all`
	- `kubectl create deployment httpd-frontend --image=httpd:2.4-alpine --replicas=3`
	- Two types of deployment strategies:
		- Recreate: delete then up, but application down time in between
		- Rolling update (default): one pod after the other
	- Rollout:
		- `kubectl rollout status deployment/<deployment-name>` see status
		- `kubectl rollout history deployment/<deployment-name>` see history
			- to change cause, either `kubectl create -f <deployment.yaml> --record` or add under `metadata`, `kubernetes.io/change-cause:` 
		- When you `kubectl apply -f <deployment.yml>`, you can see changes in status and history
	- Updates: It creates another replicaset under the hood and then delete the number 1
	- Rollback: to undo `kubectl rollout undo deployment/<deployment-name>`
	- `kubectl set image deploy <d-name> <container-name>/<image>`

### Networking
- Private IP inside a node is 10.244.0.0, and each POD is 0.2, 0.3, etc.
- All containers/PODs can communicate to one another without NAT
- All nodes can communicate with all containers and vice-versa without NAT

### Services
- Services is an object that enable loose coupling between micro services in our app
- Services types:
	- NodePort: takes an internal port accessible on a port on the node
		- E.g., external access
		- TargetPort = Port of the pod, Port = port of the Service, NodePort = Port of the Node (bw 30000;32767)
		- Use labels and selectors to link the service to the pod
		- selector: takes the pod-definition.yml
		- `kubectl get svc`
		- `minikube service <service-name> --url`
	- ClusterIP: creates a virtual IP inside the cluster to enable communication bw different services
	- LoadBalancer: provisions a load balancer for our app in supported cloud providers
- Service endpoints are the touching points with each node, if you `kubectl describe service/...` and you got no endpoints, it means it is not linked to a pod
- Service template can be found in man : https://kubernetes.io/docs/concepts/services-networking/service/

### Microservices Architecture
- Name the container when `docker run`
- A POD IP can change, so never make the link to a specific IP address
- This is why you must use a service that expose an app to other applications for users for external access
- Workflow:
	i) Deploy PODs for each container
	ii) Create Services (ClusterIP) for the apps that need to be exposed/accessed
	iii) Create Services (NodePort) for the apps that need to be open to the user
- Create pod, create service
- Deploying single pods is NOT the way, but deploy deployment having multiple instance of a pod
- From pod, create deployment
- Scale deployment:
	- `kubectl scale deployment <deploy-name> --replicas=3`

### K8 on Cloud
- K8 on AWS using kops or KubeOne
- Google Cloud Platform / Google Kubernetes Engine:
	- Create deploy, then services
- Amazon Elastic Kubernetes Service
- Azure Kubernetes Service

## Udemy, Kubernetes Certified Application Developer (CKAD) with Tests

### 2. Core Concepts
- Nodes/Minions
- Cluster is a set of Nodes, multiple nodes allow sharing the weight
- Master is another node with K8 installed and is configured as a master
- Helper containers can be part of the same pod alongside your app, they live and die together
- To begin: Run docker, `minikube start`, `kubectl get nodes -o wide`
- `kubectl get pod <pod-name> -o yaml > pod-definition.yaml` to extract definition of an existing POD, then edit changes, delete and recreate the pod
- `kubectl apply -f redis.yaml` to apply changes
- `kubectl set image pods/redis redis=redis` to change image of redis pod to redis
- `kubectl edit replicaset` to edit a replicaset
- `kubectl scale replicaset/new-replica-set --replicas=2` scale a replicaset
- `kubectl explain replicaset` man to replicaset
- `kubectl get all`
- In definition under `metadata` you can specify `namespace` 
- `kubectl create namespace dev`
- `kubectl config set-context $(kubectl config current-context) --namespace=dev`
- `kubectl get pods --all-namespaces` or `kubectl get pods --namespace=research`
- `kubectl run redis --namespace=finance --image=redis` to create redis pod in finance namespace
- `kubectl get pods -n=dev`
- For 'Blue' in 'dev1' to access 'db-service' in 'dev2' namespace, it has to use: db-service.dev2.svc.cluster.local
- Imperative Commands:
	- `kubectl run redis --image=redis --dry-run=client -o yaml > redis.yaml` to create a redis image with a yaml as output
	- `kubectl create -f redis.yaml`
	- `--dry-run=client` allows to not create, and to check if the command is right
	- https://kubernetes.io/docs/reference/kubectl/conventions/
	- POD : `kubectl run nginx --image=nginx --port=8080 --dry-run=client -o yaml`
	- DEPLOYMENT : `kubectl create deployment nginx --image=nginx -n=dev --dry-run -o yaml`
	- SERVICE : `kubectl expose pod redis --port=6379 --name redis-service --dry-run=client -o yaml` or `kubectl create service clusterip redis --tcp=6379:6379 --dry-run=client -o yaml` or `kubectl expose pod nginx --port=80 --name nginx-service --type=NodePort --dry-run=client -o yaml`

### 3. Configuration
- Commands and arguments in k8:
	- ENTRYPOINT -> specs/containers/command: then list of '-' or ["cmd1", "cmd2"]
	- CMD -> specs/containers/args: ["--my","args"]
- Environment variables
```
spec:
  containers:
  - name: bla
    image: bla-img
	env:
	  - name: APP_ENV
	    value: lol # for plain key
		valueFrom:
		  configMapKeyRef: # for configmap
		    name: <configfile-name>
			key: ENVVAR
		  secretKeyRef: # for secrets
```
- ConfigMaps:
	- 1) create configmap
	- `kubectl create configmap app-config --from-literal=KEY=value --from-literal=KEY2=value2`
	- `kubectl create configmap app-config --from-file=app_config.properties`
	- and 2) inject into pod
	- in specs/containers add `envFrom: - configMapRef: name:<metadata-name-of-configmap>`
- Secrets:
	- 1) create secrets
	- `kubectl create secret generic <secret-name> --from-literal=<key>=<value> --from-file=<path-to-file>`
	- But encode `| base64` when putting in secrets and to decode `| base64 --decode`
	- and 2) inject into pod
	- in pod's spec/containers add `envFrom: - secretRef: name: db-secret`
	- in spec/containers add `volumes: -name: <volume-name> secret: secretName: <secret-name>`
	- Encrypting confidential data at rest: https://kubernetes.io/docs/tasks/administer-cluster/encrypt-data/
		- `ETCDCTL_API=3 etcdctl --cacert=/etc/kubernetes/pki/etcd/ca.crt --cert=/etc/kubernetes/pki/etcd/server.crt --key=/etc/kubernetes/pki/etcd/server.key get /registry/secrets/default/secret1 | hexdump -C`
		- `kubectl get secrets --all-namespaces -o json | kubectl replace -f -`
	- https://kubernetes.io/docs/concepts/configuration/secret/#risks
- Security contexts:
	- Security settings
	- `kubectl exec ubuntu-sleeper -- whoami`
	- `securityContext: runAsUser: 1010`
- Service accounts:
	- For Prometheus or Jenkins
	- Automatically mounts the default SA, to undo it: `spec: automountServiceAccountToken: false`
- Resource Requirements:
	- kube-scheduler identifies best node to place node on, if too full 'insufficient cpu'
	- `spec:containers:resources:requests:memory: "1Gi"cpu: 1` 
	- `spec:containers:resources:limits:memory: "2Gi"cpu: 2` 
- Taints and Tolerations:
	- What pods can be scheduled on a node, place a pod (toleration, e.g., bug) on a node (taints, e.g., spray on person) but no guarantee that it will be placed on that node
	- Tells the node to accept certain toleration
	- A taint is automatically applied to the Master node
- Node Selectors:
	- If we have different power nodes
	- `kubectl label nodes node-1 size=Large`
	- And for pod `spec:ndoeSelector:size:Large`
	- Cannot have conditionnal: Large or Medium, not small, this is why you must work with affinity
- Node Affinity:
	- `spec:affinity:nodeAffinity:requiredDuringSchedulingIgnoredDuringExecution:nodeSelectorTerms:-marchExpressions:-key:size/operator: In/values:-Large/-Medium`

### 4. Multi-Container Pods
- They share the same workspace (e.g., app and logs), can refer to localhost, and have access to same storage volumes
- Design Patterns:
	- Sidecar: Log Server
	- Adapter: Process logs before sending it to central server
	- Ambassador: connects to different db at different stages
- initContainers:
	- `spec:containers:-//firstcontainer//initContainers:-//secondcontainer//-//thirdcontainer//`
	- https://kubernetes.io/docs/concepts/workloads/pods/init-containers/

### 5. Observability
- 

### 10. Helm Fundamentals
- You may have many yaml file for every object
- Sometimes called as the package manager of K8, it does all the micro management
- You put each of your yaml in templates

### (admin) 12. Helm Basics
- 

# Web performance

## [Ultimate guide to web performance](https://www.youtube.com/watch?v=0fONene3OIA)
- LCP, Largest Contentful Paint:
	- Loading performance
	- Good < 2.5s Needs improvement < 4.0s Poor
	- First to largest contenful paint (from the first assets to be displayed to the page with all assets)
	- Bad LCP == Bad SEO
	- HOWTO:
		- Open Network tab
		- Examine the network waterfall
		- It shows you how each asset is loaded
		- Solutions:
			1. Reduce resource load time -> lower the Bytes of an asset + use modern assets (webp or avif, same for fonts)
			2. In production, use a CDN
			3. Render blocking JS -> AVOID await, e.g., Next.js > react because SSR (server side render) vs Single page application
			4. Preload -> `rel="preload"`, `fetchpriority="{low|high}"`
- FID, First Input Delay:
	- Interactivity
	- Good < 100ms NI < 300ms Poor
	- HOWTO:
		- With Web vitals pluggin
		- Solutions:
			- Reduce JS execution -> use partytown or lazy loading
- CLS, Cumulative Layout Shift:
	- Visual Stability
	- Good < 0.1 NI < 0.25 Poor
	- Elements on the page shouldn't be jumping
	- HOWTO:
		- Solutions:
			- Use img width and height OR srcset

# Python

## [Python 101: Learn the 5 Must-Know Concepts](https://www.youtube.com/watch?v=mMv6OSuitWw)
- Mutable – immutable
- List comprehensions :
	- `x = [i for i in range (10)]`
- Function arguments & parameter types :
	- `def fn(*args, **kwargs)` # key word args
	- `*args` to say that we can accept any positional parameters -> stored in tuple
	- `**kwargs` means the function can accept any number of keyword arguments -> stored in dictionary
- if __name__ == "__main__" :
	- Allow the file, when ran directly, to do what's under it
	- But when imported, does not run it
- Global Interpreter Lock :
	- Cannot run multi-thread

## [Ecrivez du code python maintenable]()https://openclassrooms.com/fr/courses/7160741-ecrivez-du-code-python-maintenable
- [PEP 8](https://peps.python.org/pep-0008/) :
- Python Enhancement Proposal
- Style guide
- variables (snake_case) = `pep_eight`
- const variables = `PEP_EIGHT`
- class (CapitalizedCase) = `PepEight`
- modules = `pepeight`
- Comments (#) are above the code
- Simple line docstrings :
	- `"""This is my docstring"""`
- Or complete docstring :
```
"""Docstrings are written at the begining of a function, class or module. They only describe return, useful to explain the usage.

Attrs:
- first (str) -- bla
- second (str) -- bla

Returns:
- blabla
"""
```

- `_PrivateClasses` do not need docstrings
- When fixing default value, we can do `var1="my var"`
- Pas (d'espace)
- Line code max = 79 chars
- Cut a long string by CR
- Order : File comments, imports, constants then code
- try: ... except ValueError as error: raise ValueError
- `if isinstance(obj, int):`
- `if greeting` AND NOT == True or is True
- Linter :
	- `pip install flake8`
	- `pip install black`
- Design patterns :
	- Constant : faire des chiffres variables, des VAR_CONST
	- Decorateur : quand on veut faire exécuter des fonctions avant et après, on fait un décorateur; si tu veux faire des trucs avant et après ta fonction, tu va décorer cette fonction du décorateur (wrapper)
```
def calculate_time_spent(function):
	
    def wrapper(*args, **kwargs):
	
		start = time()
		result = function(*args, **kwargs)
		end = time()
		time_spent = end - start
		print(f"sec passées: {time_spent:.2f}")
		
		return result
		
	return wrapper


@decorate_function # sucre syntaxique
def function_to_pass():
	print("Await...")
	sleep(3)
	print("Done!")
```

- MVC, Modèle-Vue-Contrôleur : 
	- Modèle -- notification -> Contrôleur -- mise à jour -> Vue
	- Modèle <- mise à jour  -- Contrôleur <- user action -- Vue
	- Modèle = infos relatives à l'état du système, càd fonctionnalités brutes de l'application
	- Vue = Interface visuelle et/ou sonore pour l'user
	- Contrôleur = garantit que les commandes sont exe correctement, modifie les objects, met à jour l'app, càd rouages de l'app
- `__init__` pour initialiser les variables à l'intérieur d'une classe, `self.var1 = var1`
- `__str__` pour retourner joliment `return f"{self.var1} is {self.var2}"`
- `__repr__` pour retourner directement `self`
- `__lt__` pour comparer la classe less than
- SOLID beneficial principles ([Durand, 2013](https://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/)):
- KISS (Keep It Simple, Stupid) to an easier understanding, maintenance, modification and testing
- Single responsibility, one class/function = one job/task, there's only one reason to modify it
	- Model View Controler
	- Lorsque vous ajoutez une nouvelle fonctionnalité, posez-vous ces questions :
		- Quels sont les changements à venir qui pourraient impacter cette classe ?
		- Qu’est-ce qui pourrait donner à la classe plus d’une raison d’être modifiée ?
- Opened to extension / Closed to modification
	- Quand algorithmes, probable qu'il change au fil du temps
	- Quand données qui entrent ou sortent du système
- Liskov substitution, child classes should be able to do what parent classes do
	- "Si Φ(x) est une propriété démontrable pour tout objet x de type T, alors, Φ(y) doit être vrai pour les objets y de type S, lorsque S est un sous-type de T."
	- Le principe de substitution de Liskov s’applique aux hiérarchies d’héritage. Il est enfreint lorsqu’une classe dérivée ne peut pas prendre la place d’une classe de base sans casser le système.
- Interface segregation, responsabilité unique appliqué aux interfaces
	- Mieux vaut avoir deux interfaces avec peu de méthodes à impléementer qu'une seule interface qui ait tropp de reponsabilités!
- Dependency inversion, classes parents ne doivent pas avoir à changer lorsqu'une de leur sous-classes est modifiée
	- Moins un objet en sait sur un autre et moins il est dépendant de cet autre objet
- STUPID principles to avoid :
	- Singleton:
		- Difficile de tester, on ne peut pass sous-classer, il casse le O
	- Tight coupling:
		- When 2 classes/modules dépendent tellement l'une de l'autre que si modif de l'une modif de l'autre
	- Untestability:
		- Si une classe a besoin de nombreuses dépendances pour fonctionner correctement, il faut réécrire.
	- Premature Optimization
	- Indescriptive Naming
	- Duplication

## Django

### [Débutez avec le framework Django](https://openclassrooms.com/fr/courses/7172076-debutez-avec-le-framework-django?archived-source=4425076) :

- `python3 -m venv env`
- `source env/bin/activate` & `deactivate` to leave
- `pip install django` # once in env, installs django
- `pip freeze > requirements.txt` # keep track of required packages
- `django-admin startproject merchex` # creates local proj, app, db, command line utility (CLU)
- `python manage.py runserver` # creates local server,  manage.py is the CLU script of django
- `python manage.py migrate` # creates db.sqlite3
- `python manage.py startapp listings` # repertoire of apps
- Add 'listings' to INSTALLED_APPS in appname/appname/settings.py (the config of the entire project)
- **VIEW** :
- Create views in `listings/views.py` by defining a function
	- A view is a function accepting an HttpRequest Object as a parameter and returns an HttpResponse
```
from django.http import HttpResponse
...
def hello(request):
	return HttpResponse('<h1>Hello, world.</h1>')
```
- Once the view created, update the URL Model in `urls.py`
```
from listings import views
...
path('hello/', views.hello)
```
- **MODEL**:
- A model defines the object characteristics and behaviors you want to keep track in you app. It resembles to a stadard class but it can persist its data in a db.
- 
- Django a un ORM (Object-Relational Mapping), pour updater le modèle il faudra migrer régulièrement
- In `listings/models.py` :
```
class Band(models.Model):
    name = models.fields.CharField(max_length=100)
```
- Django takes care of creating the constructor for us
- La structure d'une base de données, en termes de tables et de colonnes, est appelée schéma
- Une migration est un ensemble d'instructions permettant de passer le schéma de votre DB d'un état à un autre.
- `python manage.py makemigrations`
- `python manage.py migrate`
- `python manage.py shell`
- In shell:
	- `from listings.models import Player`
	- To save an object in the DB : `player.save()` ou `player = Player.objects.create(name='Foo')`. NOTE: Once you save the `id` is automatically added for us
- `Player.objects.{count(),all()}` # to count and see
- In `listings/views.py` :
```
from listings.models import Player
...
players = Player.objects.all()
def hello(request):
    players = Player.objects.all()
    return HttpResponse(f"""
                        <h1>Welcome in VeryKoolGames!</h1>
                        <p>L'équipe est composée de : <p>
                        <ul>
                            <li>{players[0].name}</li>
                            <li>{players[1].name}</li>
                            <li>{players[2].name}</li>
                        </ul>
                        """)
```
- **GABARIT** est un fichier HTML permet d'interprêter du code python, https://docs.djangoproject.com/fr/5.0/ref/templates/builtins/
- MVT : Modèle(stock données)-Vue(récupère données)-Template(affiche données)
- To render this HTML file in `listings/views.py` : `return render(request, 'listings/hello.html', {'players':players})`
- Under `listings/templates/listings/base.html`:
```
<html>
    <head><title>VeryKoolGames</title></head>
    <body>
		{% block content %}{% endblock %}
    </body>
</html>
```
- Under `listings/templates/listings/hello.html`:
```
{% extends 'listings/base.html' %}
{% block content %}
	<h1>Welcome in VeryKoolGames!</h1>
	<p>We are an indie video game studio created by {{players|length}} co-founders:</p>
	<ul>
		{% for player in players%}
		<li>{{player.name|upper}}</li>
		{% endfor%}
	</ul>
{% endblock %}
```
- la meilleure pratique consiste à ajouter notre application en bas de la liste afin qu'elle soit la dernière à se charger.
- mvt(emplate) is a fresh take on the classic mvc design pattern ([django](https://www.askpython.com/django/django-mvt-architecture))
- [Static files](https://docs.djangoproject.com/fr/3.1/howto/static-files/#configuring-static-files)
- Style.css to put in `listings/static/listings` + `{% load static %}` in model with `{% static 'listings/styles.css' %}`
- **Système de Gestion de Base de Données** :
- [Validateurs](https://docs.djangoproject.com/fr/3.2/ref/validators/)
- https://openclassrooms.com/fr/courses/7172076-debutez-avec-le-framework-django/7516421-capturez-des-donnees-avec-des-modeles-et-des-champs
- Do not forget to makemigrations and migrate, if ask to put default value, press '1' and define
- **CRUD** in Django :
- `python manage py. createsuperuser`
- In `/admin` you can go to the Django Administration and do your CRUD there
- To display the models' name add to the models' class : `def __str__(self): return f'{self.name}'`
- To display other fields add in `admin.py`:
```
class PlayerAdmin(admin.ModelAdmin):
	list_display = ('field1', 'field2')
	
admin.site.register(Player, PlayerAdmin)
```
- `python manage.py showmigrations`
- Vue en liste = affiche tous les objets
- Vue détaillée = un objet avec tous les détails et champs
- Notez comment nous terminons chaque chemin par un slash (« / »), c'est une convention Django.
- In `urls.py` : `path("games/<int:game_id>", views.games_detail)`
- In `views.py`, update the games_detail def
- In template, you can use whatever you have
- `get_VAR_display`, VAR being the name of the field to display it
- 404 when not found `obj = get_object_or_404(Game, id=game_id)`
- Form to send mails
- "Ne jamais faire confiance au client"

### [Mettez en place une API avec Django REST Framework](https://openclassrooms.com/fr/courses/7192416-mettez-en-place-une-api-avec-django-rest-framework)

- `pip install djangorestframework`
- `pip install markdown`
- `pip install django-filter`
- Under INSTALLED_APPS, add 'rest_framework'
- Serializer : pour transformer des modèles Django en format exploitables par une API ou recevoir JSON et transforme en objet
- https://openclassrooms.com/fr/courses/7192416-mettez-en-place-une-api-avec-django-rest-framework/7424498-gerez-des-donnees-avec-un-endpoint

## Flask

- `flask run`, opt: --port 5001
- `flask --app app shell` or `flask shell`
	- `db`
- `flask db init`
- `flask db stamp head` if not up to date
- `flask db migrate -m "yourcommenthere"`, generates migration script, it does not make any changes to the db
- Create the db in db server before running upgrade
- `flask db upgrade` applies changes to the db -> do it when in prod
- `flask db history`
- After tests :
	- `flask db downgrade base`
	- `flask db upgrade`

### [Designing a RESTful API with Python and Flask](https://blog.miguelgrinberg.com/post/designing-a-restful-api-with-python-and-flask)
- The easiest way to secure our web service is to require clients to provide a username and a password. In a regular web application you would have a login form that posts the credentials, and at that point the server would create a session for the logged in user to continue working, with the session id stored in a cookie in the client browser. Unfortunately doing that here would violate the stateless requirement of REST, so instead we have to ask clients to send their authentication information with every request they send to us.
- Protect the functions by adding `@auth.login_required` decorator

### [Flask mega-tutorial I: Hello-World](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world)
- `from app import routes` is imported at the bottom to avoid circular imports
- `export FLASK_APP=path/to/app.py`

### [Flask meta-tutorial IV: Database](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-iv-database)
- "To accomplish this seemingly difficult task, Alembic maintains a migration repository, which is a directory in which it stores its migration scripts. Each time a change is made to the database schema, a migration script is added to the repository with the details of the change. To apply the migrations to a database, these migration scripts are executed in the sequence they were created."
- `user_id` is called a *foreign key* because it references a primary key of another table.
- Since not all databases automatically create an index for foreign keys, the index=True option is added explicitly, so that searches based on this column are optimized.

### [Flask mega-tutorial VII: Error Handling](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-vii-error-handling)

### [Flask mega-tutorial XV: A better app structure](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xv-a-better-application-structure)
- Not use a global vairable for the application and instead use an application factory function to create the function at runtime
- In Flask, a blueprint is a logical structure that represents a subset of the app. A BP can include elements such as routes, view unctions, forms, templates, and static files. If your write your blueprint in a sepatate Python package, then you have a component that encapsulates the elements related to specific feature of the app -> as a temporary storage for app functionality that helps in organizing your code

# MySQL

## [mysql tutorial for beginners, full course](https://www.youtube.com/watch?v=7s_tz1z_5ba)
- database is a collection of data stored in a format that can easily be accessed
- using a dbmanagementsystem :
	- relational (structured query language) : store data into tables linked to each other using relationships (ex. mysql, oracle)
- administration tab to start or stop a server, import/export data
- for each db you have :
	- tables : to store data
	- views : like virtual cables, to combine data from multiple tables and put them in a view. powerful to create reports.
	- stored procedures and function : store functions inside our db for querying data
- clauses : 
	- `select` : `col1 + 10 as new_col1`, if `select distinct` removes duplicates
	- `from` 
	- `where` : `in ('cond1', 'cond2')` to avoid or, or; `between 10 and 100` to avoid <= and >=; `like 'b%'` search everything which begins with b* and _ for single char; `regexp` ^ to say beginning of string, $ to represent the end of a string, | to seach multiple search pattern, `[abc]e` a b or c before e
	- `order`
	- `limit` : at the end, choose the x first rows
	- `join`
- comment by using two hyphens "--"
- 1:40


# rest
## [saison 20-21- part 3 - web services rest concepts de base](https://www.youtube.com/watch?v=jzk1mboe33e) :
- representational state transfert es tun style d'architecture pour les systèmes hypermédia distribués
	- [explaining distributed systems like i'm 5](https://www.youtube.com/watch?v=ceskgdnikjw) :
		- client->api server->db : synchronous so blocking people from uploading, question is : what is we have dozens of concurrent uploads?
		- irl, for icecream vendor -> you create queues! -> but what if a lot of people? -> so hire a security guard
		- a ds is a collection of indipendent computers that appear to its users as one computer (tanenbaum a.) -> what matter to the user is the speed and possibility to ask for many different icecream at the same time
		- rules :
			- all computers operate concurrently
			- all computers fail concurrently
			- all computers do not share a global clock
				- we will never have synchronized hours, e.g., latency due to speed of light, [ntp ptp](https://www.geeksforgeeks.org/difference-between-ntp-and-ptp/)
- [what are http requests?](https://www.youtube.com/watch?v=-zea7gb2owa) :
	- hypertext transfer protocol : used to structure requests and responses over the internet
	- transmission control protocol : manages the channels bw your browser and the server
	- get, post, etc. are an http method.
- une norme avec 5 règles :
	1. l'uri (uniforme resource identifier) comme identifiant des ressources
		- request parameter, ex. "/books?filtre=policier"
		- path parameter, ex. "/books/87"
	2. les méthodes http comme identifiant des opérations
		- pour une ressource, il y a 4 opérations possibles (crud):
			- create -> post = ajouter,
			- read -> get = consulter,
			- update -> put = mettre à jour,
			- delete -> delete = supprimer
	3. les réponses http comme représentation des ressources : la réponse envoyée n'est pas une ressources mais la représentation d'une ressource, c'est au client de définir quel format de réponse il souhaite recevoir via le header http "accept: application/json"
	4. les liens comme relation entre ressources : https://www.iana.org/assignments/link-relations/link-relations.xhtml
	5. un paramètre comme jeton d'authentification avec un token. deux type de sécurité :
		- stateful -> quand utilise session et cookies, stocké dans la mémoire du serveur et géré par lui, identifiant comme cookie. inconvénients quand utilise rest
		- stateless -> quand utilise token d'identification. votre session est gérée par le client. ex. json web token, on trouve username, rôle, date d'expiration user. c'est votre session.
- rest ou restful? rest respecte les 3 premières règles, restful on respecte les 5 règles.
- différence entre :
	- serveur d'application jee: peut être glassfish, jboss (wildfly) plus performant, websphere. opensource plus performant et possibilités que commercial. démarre plusieurs services, ex. web container (tomcat) servlet, jsp. et des spec / apis.
	- springioc : utilise tomcat, utilise les specs que tu veux.
- un web service restful est un objet.
```
 @path("/banque")
 public class banquerestservice {
 
 @path("/comptes")
 @get
 @produces(mediatype.application_json)
 public list<compte> listcomptes() {
	list<compte> cptes=new arraylist<>();
	...
	return cptes;
}
@path("/comptes/{code}")
@get
@produces({mediatype.application_json,mediatype.application_xml})
public compte getcompte(@pathparam(value="code")long code) {
return new compte(1l, math.random()*9999, new date());
}
...
```

## [adopter les api rest pour vos projets web](https://openclassrooms.com/fr/courses/6573181-adoptez-les-api-rest-pour-vos-projets-web) :
- api comme intermédiaire entre données de l'application et le client
- api peuvent communiquer - d'un logiciel à un logiciel; - d'un client à un serveur; - d'un logiciel à des développeureuses
- api privée permet uniquement aux utilisatrices autorisées d'utiliser l'api et accéder à la base de données
- contraintes rest:
	1. client/server separation
		- client  récupération et afficache de l'information, et serveur = stockage et manipulation des donées
	2. stateless (sans état)
		- le serveur ne sauvegarde aucune des requêtes ou réponses précédentes.
		- le fait dêtre stateless rend chaque réponse déterminée et compéhensible
	3. cachable (sauvegardable)
		- si l'user formule deux fois la même requête (ex. revoir page) et que les informations n'ont pas changé, alors le serveur n'a pas besoin de rechercher les informations une deuxième fois
		- permet de réduire le nombre de fois où un client et serveur interagissent -> ne pas réduire le temps de chargement pour l'user
	4. uniform interface
		- utilisation de la même norme
	5. layered system
		- composants indépendants donc facilite remplacement ou mise à jour, ex. si requête pour recevoir livres, le client n'a aucune idée des composants avec lesquels l'api communique.
	6. code-on-demand architecture
		- le serveur peut étendre sa fonctionnalité en envoyant le code au client pour téléchargement (facultatif)
- simple object access protocol (soap) est un protocole et non un style d'architecture
- les données rest sont représentées dans :
	- (nominal) des *ressources*, ex. superhero = {name, description, img}
	- (pluriel) des *collections*, ex. superheroes = {superhero, superhero}
- uri = uniform ressource identifier (comme le path), ex. /characters/001 ([anapioficeandfire.com](anapioficeandfire.com))
- toutes les url sont des uri, mais toutes uri ne sont pas url. uri pour identifier une ressource, url permet de localiser
- endpoint = comme adresse complète d'un fichier -> domainname + uri
- data = information envoyée ou reçue
- collection = groupe de ressources
- ressource = contient des données que le client veut obtenir ou manipuler
- idée : use [hpapi](https://github.com/laboratoria/lim011-data-lovers/blob/master/src/data/potter/potter.json)
- requête :
	- verbe http (get, put, post, delete)
	- uri : `/users/:user_id` :user_id est un placeholder, en vrai on aurait mis `users/145`
	- version http
	- [header](https://developer.mozilla.org/fr/docs/web/http/headers) : in key-value pair. it is supplementary information, ex. language, date, logiciel utilisé, clé auth
	- body facultatif : only with put ou post
- réponse :
	- [code de réponse http](https://developer.mozilla.org/fr/docs/web/http/status):
		- 100+ ➡ information
		- 200+ ➡ succès
		- 300+ ➡ redirection
		- 400+ ➡ erreur client
		- 500+ ➡ erreur serveur
	- header
	- body : contient toute l'info
- authentification: dans post, header, authorization: bearer
- path parameters -> dans uri
- curl : you can send requests with it
- définir les fonctionnalités :
	- quels types d'endpoints?
	- quelles ressources?
- api sont créées par des devs pour des devs
- filter:
	- get /photos?location={locationid} // location est un paramètre
- recherche:
	- get /photos?search=snowboard
	- /search?q=snowboard
- trier:
	- get /users/{userid}/followers?sort=lastname&order=asc
- paginer vos résultats:
	- si endpoint /photos très lent, doit faire pagination entre 10:100
	- get /photos?page=23
- versionner:
	- s'assurer que votre applli puisse être compatible pour les versions antérieures
	- get /v1/photos
- quel framework?
	- [express js](https://expressjs.com/) (js)
	- [ror](https://rubyonrails.org/) (ruby)

# unity

## [20 unity tips in 10 min](https://www.youtube.com/watch?v=4nnayvhcwjq)
- inspector debug view > upright corner normal to debug, it allows to see private fields, do not use debug.log!, press option key to see real var names
- hierarchy lock and visibility button
- anonymous lambda functions : .onclick.addlistener(() => {});
- destroy(this) # destroys script, useful when unit dies but keep animation
- debug.drawline(currentpos,nextpos)
- shift+space : fullscreen
- cmd+d : duplicate
- f : focus on object
- cmd+shift+f : match object with scene camera

## [10 unity tips you (probably) didn't know about](https://www.youtube.com/watch?v=fmbylyu7z9y)
- private ienumerator start() -> turns start into co-routine that automatically starts at runtime (e.g., timer)
- to assign multiple objects, instead of locking, open properties window and drag-drop
- /// to write a summary of your function
- change "if (var != null)" by "var?"
- preferences > scene view > create objects at origin

## [scriptable objects](https://www.youtube.com/watch?v=apxvowvabpy)
- data containers
- act as a template
- monobehavior to `scriptableobject`
- add before public class `[createassetmenu(filename = "", menuname = "")]`

## [ml-agents](https://www.youtube.com/watch?v=zpfu30tbyks)
- `python -m venv venv`
- `source venv/bin/activate`
- `python -m pip install --upgrade pip`
- `pip install torch`
- `pip install mlagents`
- it did not work : i went with https://unity-technologies.github.io/ml-agents/installation/
- `conda create -n mlagents python=3.10.12 && conda activate mlagents`
- `conda info --envs`
- `cd /path/to/ml-agents`
- `python -m pip install ./ml-agents-envs`
- `python -m pip install ./ml-agents`
- `mlagents-learn --help` 
- `mlagents-learn --force` // overrides previous data
- `mlagents-learn --run-id=newid` // creates new id
- discrete branch = different actions:
	- branch to 2 actions = accelerating and braking

# github working in group setup

- `git pull`
- `git checkout -b <branchname>` (creation)
- `git push -u origin <branchname>` (creation)
- `git branch -d <branchname>` (delete)
- `git push origin -d <branchname>` (delete)
- `git fetch -p origin`
- `git branch -rd origin/*`
- `git pull origin main`

# how to learn (...) without following tutorials ?

https://www.youtube.com/watch?v=vfjxkoxdggo

1. learn the absolute **basics** and nothing more
2. **familiarize** with the basics through repetition and simple projects
3. over time, **experiment** and build a repertoire/knowledge base of tools

# mastering the vim language

25 sept. 2022

notes taken from : [mastering the vim language](https://www.youtube.com/watch?v=wlr5gyd6um0?link_credit=kennethrioja), [slides](https://ctoomey.com/mastering-the-vim-language-slides.pdf?link_credit=kennethrioja)

- [typing is not the bottleneck](http://anarchycreek.com/2009/05/26/how-tdd-and-pairing-increase-production/?link_credit=kennethrioja) : "the hard part of programming is thinking" - increase productivity in your team 1) writing a microtest that fails before you change any code, 2) adopt a "no-pair no-keep" agreement, 3) establish a shared understanding of code quality. what will slow you down is every flawed decision.
- power of `.`, `c`, `i[wt"p]`, `f`, `t` (cf. https://benmccormick.org/2014/07/02/learning-vim-in-2014-vim-as-language , https://blog.carbonfive.com/vim-text-objects-the-definitive-guide/ , https://medium.com/@mkozlows/why-atom-cant-replace-vim-433852f4b4d1 , https://stackoverflow.com/questions/1218390/what-is-your-most-productive-shortcut-with-vim/1220118#1220118 )
- [vim textobj user](https://github.com/kana/vim-textobj-user/wiki)

Why should you use a basic text editor?

08 sept. 2022

I will mostly focus on vim since I have been using this since the beginning

**Why should you use [vim](https://www.vim.org/?link_credit=KennethRioja) ?**

1. Keep it classy
2. Way more efficient (and less memory consumming !) than those fancy apps (*e.g.*, VSC, BrainJet, Atom,...)
3. Impress your peers

**How to begin your programming journey?**

1. Learn the basics
   - Open a terminal and execute the command [vimtutor](https://vimschool.netlify.app/introduction/vimtutor/?link_credit=KennethRioja)
2. Make it appealing to you
   - Configure your [.vimrc file](https://www.freecodecamp.org/news/vimrc-configuration-guide-customize-your-vim-editor/)
3. Keep track of your learning
   - Take notes using [VimWiki](https://github.com/vimwiki/vimwiki) and allow yourself to build a [secondbrain](https://www.buildingasecondbrain.com) !

**Going further**

- [How to Do 90% of What Plugings Do (With Just Vim)](https://www.youtube.com/watch?v=XA2WjJbmmoM?link_credit=KennethRioja)
