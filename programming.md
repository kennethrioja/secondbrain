# Programming

## Table of Contents

<!-- vim-markdown-toc GFM -->

* [REST](#rest)
* [Unity](#unity)
	* [20 Unity Tips in 10 min](#20-unity-tips-in-10-min)
	* [10 Unity Tips You (Probably) Didn't Know About](#10-unity-tips-you-probably-didnt-know-about)
	* [Scriptable Objects](#scriptable-objects)
	* [ML-agents](#ml-agents)
* [Github working in group setup](#github-working-in-group-setup)
* [How to learn (...) without following tutorials ?](#how-to-learn--without-following-tutorials-)
* [Mastering the Vim Language](#mastering-the-vim-language)

<!-- vim-markdown-toc -->

# REST
- [Saison 20-21- Part 3 - Web services REST Concepts de base](https://www.youtube.com/watch?v=jzK1mBOe33E) :
	- REpresentational State Transfert es tun style d'architecture pour les systèmes hypermédia distribués
		- [Explaining Distributed Systems Like I'm 5](https://www.youtube.com/watch?v=CESKgdNiKJw) :
			- Client->API server->DB : synchronous so blocking people from uploading, question is : What is we have dozens of concurrent uploads?
			- IRL, for Icecream vendor -> you create queues! -> but what if a LOT of people? -> So hire a security guard
			- A DS is a collection of indipendent computers that appear to its users as one computer (Tanenbaum A.) -> what matter to the user is the speed and possibility to ask for many different icecream at the same time
			- Rules :
				- All computers operate concurrently
				- All computers fail concurrently
				- All computers do not share a global clock
					- We will never have synchronized hours, e.g., latency due to speed of light, [NTP PTP](https://www.geeksforgeeks.org/difference-between-ntp-and-ptp/)
	- [What are HTTP requests?](https://www.youtube.com/watch?v=-Zea7GB2OwA) :
		- HyperText Transfer Protocol : used to structure requests and responses over the internet
		- Transmission Control Protocol : manages the channels bw your browser and the server
		- GET, POST, etc. are an http method.
	- Une norme avec 5 règles :
		1. l'URI (Uniforme Resource Identifier) comme identifiant des ressources
			- Request Parameter, ex. "/books?filtre=policier"
			- Path Parameter, ex. "/books/87"
		2. Les méthodes HTTP comme identifiant des opérations
			- Pour une ressource, il y a 4 opérations possibles (CRUD):
				- Create -> POST = ajouter,
				- Read -> GET = consulter,
				- Update -> PUT = mettre à jour,
				- Delete -> DELETE = supprimer
		3. Les réponses HTTP comme représentation des ressources : la réponse envoyée n'est pas une ressources mais la représentation d'une ressource, c'est au client de définir quel format de réponse il souhaite recevoir via le HEADER HTTP "Accept: application/json"
		4. Les liens comme relation entre ressources : https://www.iana.org/assignments/link-relations/link-relations.xhtml
		5. Un paramètre comme jeton d'authentification avec un token. Deux type de sécurité :
			- Stateful -> quand utilise session et cookies, stocké dans la mémoire du serveur et géré par lui, identifiant comme Cookie. Inconvénients quand utilise REST
			- Stateless -> quand utilise token d'identification. Votre session est gérée par le client. Ex. Json Web Token, on trouve username, rôle, date d'expiration user. C'est votre session.
	- REST ou RESTful? REST respecte les 3 premières règles, RESTful on respecte les 5 règles.
	- Différence entre :
		- Serveur d'application JEE: peut être GlassFish, JBOSS (Wildfly) plus performant, WebSphere. OpenSource plus performant et possibilités que Commercial. Démarre plusieurs services, ex. Web Container (TomCat) Servlet, JSP. Et des Spec / APIs.
		- SpringIOC : utilise Tomcat, utilise les Specs que tu veux.
	- Un web service RESTful est un objet.
```
 @Path("/banque")
 public class BanqueRestService {
 
 @Path("/comptes")
 @GET
 @Produces(MediaType.APPLICATION_JSON)
 public List<Compte> listComptes() {
	List<Compte> cptes=new ArrayList<>();
	...
	return cptes;
}
@Path("/comptes/{code}")
@GET
@Produces({MediaType.APPLICATION_JSON,MediaType.APPLICATION_XML})
public Compte getCompte(@PathParam(value="code")Long code) {
return new Compte(1L, Math.random()*9999, new Date());
}
...
```
- [Adopter les API REST pour vos projets web](https://openclassrooms.com/fr/courses/6573181-adoptez-les-api-rest-pour-vos-projets-web) :
	- 

# Unity

## [20 Unity Tips in 10 min](https://www.youtube.com/watch?v=4NNAYvhCWjQ)
- Inspector Debug View > UpRight corner Normal to Debug, it allows to see private fields, do not use debug.log!, press option key to see real var names
- Hierarchy Lock and Visibility Button
- Anonymous Lambda Functions : .onClick.AddListener(() => {});
- Destroy(this) # destroys script, useful when unit dies but keep animation
- Debug.Drawline(currentpos,nextpos)
- Shift+Space : fullscreen
- Cmd+D : Duplicate
- F : Focus on object
- Cmd+Shift+F : Match object with scene camera

## [10 Unity Tips You (Probably) Didn't Know About](https://www.youtube.com/watch?v=fmbYlYU7z9Y)
- private IEnumerator Start() -> turns start into co-routine that automatically starts at runtime (e.g., timer)
- To assign multiple objects, instead of locking, open Properties window and drag-drop
- /// to write a summary of your function
- Change "if (var != null)" by "var?"
- Preferences > Scene View > Create Objects at Origin

## [Scriptable Objects](https://www.youtube.com/watch?v=aPXvoWVabPY)
- Data containers
- Act as a template
- Monobehavior to `ScriptableObject`
- Add before public class `[CreateAssetMenu(fileName = "", menuName = "")]`

## [ML-agents](https://www.youtube.com/watch?v=zPFU30tbyKs)
- `python -m venv venv`
- `source venv/bin/activate`
- `python -m pip install --upgrade pip`
- `pip install torch`
- `pip install mlagents`
- It did not work : I went with https://unity-technologies.github.io/ml-agents/Installation/
- `conda create -n mlagents python=3.10.12 && conda activate mlagents`
- `conda info --envs`
- `cd /path/to/ml-agents`
- `python -m pip install ./ml-agents-envs`
- `python -m pip install ./ml-agents`
- `mlagents-learn --help` 
- `mlagents-learn --force` // overrides previous data
- `mlagents-learn --run-id=newid` // creates new id
- Discrete branch = different actions:
	- Branch to 2 actions = accelerating and braking

# Github working in group setup

- `git pull`
- `git checkout -b <branchname>` (creation)
- `git push -u origin <branchname>` (creation)
- `git branch -d <branchname>` (delete)
- `git push origin -d <branchname>` (delete)
- `git fetch -p origin`
- `git branch -rd origin/*`
- `git pull origin main`

# How to learn (...) without following tutorials ?

https://www.youtube.com/watch?v=vFjXKOXdgGo

1. Learn the absolute **basics** and nothing more
2. **Familiarize** with the basics through repetition and simple projects
3. Over time, **experiment** and build a repertoire/knowledge base of tools

# Mastering the Vim Language

25 sept. 2022

Notes taken from : [Mastering the Vim Language](https://www.youtube.com/watch?v=wlR5gYd6um0?link_credit=KennethRioja), [slides](https://ctoomey.com/mastering-the-vim-language-slides.pdf?link_credit=KennethRioja)

- [Typing is not the bottleneck](http://anarchycreek.com/2009/05/26/how-tdd-and-pairing-increase-production/?link_credit=KennethRioja) : "the hard part of programming is thinking" - increase productivity in your team 1) writing a microtest that fails before you change any code, 2) adopt a "no-pair no-keep" agreement, 3) establish a shared understanding of code quality. What will slow you down is every flawed decision.
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
