# Programming

## Table of Contents

<!-- vim-markdown-toc GFM -->

* [Tabby](#tabby)
* [MonitorControl](#monitorcontrol)
* [Rectangle](#rectangle)
* [Yabai](#yabai)
* [AutoRaise](#autoraise)
* [Python](#python)
	* [Python 101: Learn the 5 Must-Know Concepts](#python-101-learn-the-5-must-know-concepts)
	* [Ecrivez du code python maintenablehttps://openclassrooms.com/fr/courses/7160741-ecrivez-du-code-python-maintenable](#ecrivez-du-code-python-maintenablehttpsopenclassroomscomfrcourses7160741-ecrivez-du-code-python-maintenable)
	* [Débutez avec le framework Django :](#débutez-avec-le-framework-django-)
* [rest](#rest)
	* [saison 20-21- part 3 - web services rest concepts de base :](#saison-20-21--part-3---web-services-rest-concepts-de-base-)
	* [adopter les api rest pour vos projets web :](#adopter-les-api-rest-pour-vos-projets-web-)
	* [mysql tutorial for beginners, full course](#mysql-tutorial-for-beginners-full-course)
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

## [Débutez avec le framework Django](https://openclassrooms.com/fr/courses/7172076-debutez-avec-le-framework-django?archived-source=4425076) :

Commands:

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
- **GABARIT** est un fichier HTML permet d'interprêter du code python
- MVT : Modèle(stock données)-Vue(récupère données)-Template(affiche données)
- To render this HTML file in `listings/views.py` : `return render(request, 'listings/hello.html', {'players':players})`
- Under `listings/templates/listings/hello.html`:
```
<html>
    <head><title>VeryKoolGames</title></head>
    <body>
        <h1>Welcome in VeryKoolGames!</h1>
        <p>We are an indie video game studio created by {{players|length}} co-founders:</p>
        <ul>
            {% for player in players%}
            <li>{{player.name|upper}}</li>
            {% endfor%}
        </ul>
    </body>
</html>
```
- 

notes:

- la meilleure pratique consiste à ajouter notre application en bas de la liste afin qu'elle soit la dernière à se charger.
- mvt(emplate) is a fresh take on the classic mvc design pattern ([django](https://www.askpython.com/django/django-mvt-architecture))
- 

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
