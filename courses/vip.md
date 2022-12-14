# Jeux Vidéo Pédagogiques

## Equipe enseignante : Nicolas Szilas, Kim 

## Table of contents
<!-- vim-markdown-toc GFM -->

* [Introduction historique des JVP](#introduction-historique-des-jvp)
* [Bases du jeu vidéo](#bases-du-jeu-vidéo)
* [Définitions](#définitions)
* [Potentiels et limites](#potentiels-et-limites)
* [Conception](#conception)
* [Intervention de J. Theler - E-teach](#intervention-de-j-theler---e-teach)
* [Dimension narrative des JVP](#dimension-narrative-des-jvp)
* [Mécanique](#mécanique)
* [Retour sur Rendus](#retour-sur-rendus)
* [Références](#références)

<!-- vim-markdown-toc -->

# Introduction historique des JVP

- Piaget - avec notion de jeu chez le développement de l'enfant.
- Années 80/90 "ludo éducatif" : 
    - [Carmen Sandiego, Broderbund (1985)](https://carmensandiego.fandom.com/wiki/Carmen_Sandiego)
    - [Adibou, Coktel (1991)](https://en.wikipedia.org/wiki/Adibou)
    - [Versailles, Cryo (1996)](https://fr.wikipedia.org/wiki/Versailles_1685_:_Complot_%C3%A0_la_cour_du_Roi_Soleil)
- Années 2002 "serious games" : 
    -  America's Army, USA (2002)
    - FoodForce, ONU (2005)
    - Dr Kawashima, Nintendo (2005)
    - PeaceMaker, ImpactGames (2007)
    - StarBank, (also known as advergaming), BNPP (2009)
    - Zombie Division, Univ. (2009)
    - Start the Talk, Kognito (2013)
    - X-Torp (exergame pour Alzheimer, 2015)
- Jeux vidéo vs jeux traditionnels
    - Capacités informatiques : visualisation, imersion, rapidité de calcul, communication

# Bases du jeu vidéo

- Règles > Engagement = Amusement > Histoire > Visuel
- Un jeu c'est "une action libre, sentie comme "fictive" et située en dehors de la vie courante, capable néanmoins d'aboserber totalement le joueur; une action dénuée de tout intérê matériel et de toute utilité; qui s'accomplit dans un temps et dans un espace exprérrément circonscrits, se déroule avec ordre selon des règles données" - Johan Huizinga, 1938
- Les composantes d'un jeu :
    - Mécanique principale : ensemble minimal de règles qui définissent le jeu.
    - Mécaniques secondaires : règles, définit la complexité du jeu, comptent dans la qualité du jeu, sa "jouabilité"
    - Habillage : médias - graphisme, son; contexte -monde fictionnel, récit.

# Définitions

- Jeu comme... Objet, activité, théatral, mécanique
- Johan Huizinga (1938), dans sa définition, on trouve les dimensions d'*immersion*, d'un *isolement physique et temporel*, et de *motivation intrinsèque*, de *règles*, de *liberté*
- Définition de Karel Capek (1934) "Le jeu, c'est une chose sérieuse (à l'encontre de l'amusement), il a ses lois et imporse son règlement (*règles*). Jouer, c'est se plonger (*immersion*) dans un recueillement tendre et passionné, tout en orientant notre attention; pourvu que ce qui nous abosrbe soit bien isolé du reste du monde (*isolement*), bien délimité par des lois appropriées et extrait de la réalité environnante."
- Définition de Roger Caillois (1957) : libre, séparée, incertaine, improductive, réglée, fictive.
- Classification selon Roger Caillois (1957) :
    - Compétition (agôn)
    - Hasard (alea)
    - Théâtre (mimicry)
    - Vertige (ilinx)
- Dichotomie selon Roger Caillois (1957) : liberté/paidia/play VS. contrainte/Ludus/game
- Définition de Salen & Zimmerman (2003) : "A game is a *system* in which players engage in an artificial conflict, defined by rules, that result in a quantifiable outcome"
- Définition de Szilas & Acosta (2012) "A game is a dynamical system of signs in which the player acts, independently of any consequence outside the system, in order to reach a goal assigned by the game."
    - *Système Dynamique ...* : règles, se comporte et est dynamique
        - *... de signes* : pas objet matériel qui compte, c'est le signe qui est derrière
    - *Objectif* : donné par le système
    - *Sans penser aux conséquences hors de ce système* : Quand on joue, on joue.
- Ces définitions sont souvent subjectives - liées au/à la joueur·euse.
- Caractéristiques minimales *objectives* :
    - un objectif (quantifiable outcome)
    - des règles (system laws)
        - mécanique de jeu (règles constitutives) : spécifique (lignes puissances 4) et environnementale (apesanteur pour puissance 4)
            - comportement des entités (gestion des ressources)
            - nb de joueurs
            - objectifs du jeu
            - actions des joueur·eurse·s et leurs effets
        - règles de jeu (règles opérationnelles, Salen & Zimmerman, 2004)
- Caractéristiques *subjectives* (why we play?) :
    - Espace d'évasion - fiction, mécanique de jeu
    - Aspects motivationnels - challenge, curiosité, contrôle
    - Emotions positives générées - joie, surprise, suspense, esthérique
- Flow - compétence, contrôle, motivation intrinsèque, perte du temps
- Définition d'[Amato (2007)](http://www.omnsh.org/ressources/422/vers-une-instrumentalisation-communicationnelle-des-jeux-video-quelles-formes-de) du serious game : "Jeux vidéo utilitaires, c'est-à-dire productifs, dont la coception vise à opérer une transformation chez leurs destinataires allant dansn le sens d'une amélioration des compétences (entraînement), de l'adaptation au milieu (traitement des phobies), de la compréhension d'une phénomène (éducation= ou d'une plus grande adhésion au message véhiculé (promotion, publicité, jeux vidéo idéologiques [...])
- Types de Serious Games
    - Learning Games (edu)
    - Advergaming (pub)
    - Political Games (political)
    - Exergames (physical)
    - Citizen Science Games (jouer sert pour un projet scientifique plus large)A

# Potentiels et limites

- Potentialités théoriques : 
    - Etat positif pour l'apprentissage
    - Richesse des contenus
    - Stratégie pédagogiques multiples - répétition, transmission, contenu multimédia, apprentissage authentique, actif, immersion
- Simulations :
    - "a representation of the features and behaviors of one system through the use of another" Sivasailam & Thiagarajan (1998) in Becker (2008)
    - Intérêt pédagogique : authenticité, situation à moindre coût, dangereuses ou inaccessibles dans le réel
    - Difficultés : débriefing obligatoire mais induit une certaine compétence pour l'encadrement donc coûteuse
- Intégrer le contenu : 
    - Par la mécanique - app. d'un système, via les obstacles, + difficulté, + progression
    - Par le contexte - fiction, histoire
    - Par les media

# Conception

- Méthodologie générale :
	- Démarche linéaire : Analyse du besoin -> Conception -> Réalisation -> Evaluation; - : Souci de ne pas voir où on va
	- Démarche cyclique :
		- ADDIE; -: mais reste assez linéaire
		- Rapid Prototyping : prototype -> évaluation proto -> conception -> développement
		- Extreme Programming : scénatios utilisateurs -> conceptions tests -> développement en binômes (code informatique plus révisable) -> passages tests -> livraisons partielles et fréquentes; + : comment par évaluation
		- Développement Agile : collaboration interne & avec le client -> ouverture au changement -> planification court terme -> livraisons partielles et fréquentes; - : très stressant car beoin de produire ++
	- Bilan :
		- Meilleure réponse au besoin de l'user (s'adapter au besoin)
		- Réactualisation des besoins possibles
		- Anticiper les erreurs et incohérences très tôt
		- Risque : projet sans fin... contractualisation
		- Temps de developpement court
		- Plannification plus souple
	- Erreurs classiques :
		- Sous-estimer l'analyse des besoins
		- Passer directement à la recherche d'idées
		- S'arrêter à la première solution - aller au bout et voir l'ensemble des solutions possibles
		- Ne pas itérer
- Analyse des besoins :
	- Quid des besoins mal formulés ?
		- Besoins formulés en termes de solutions
		- Besoins multiples (*mais pourquoi?*) -> revenir au besoin ultimes, besoins cachés, besoins de qui (=/= opinions)
	- Acteurs : demandeur, apprenant, experts, services techniques, hiérarchie
	- Apprenant : besoin de formation (= écart entre les compétences nécessaires et les compétences réelles d'un individu)
	- Décrire les connaissances :
		- Savoir-faire, types de connaissances, +/- contextualisées, degrés d'expertise, liens (prérequis)
	- Caractériser les apprenant·e·s :
		- Niveau (compétence, "agilité"), âge, disponibilités, points de vue, valeurs, histoire, hétérogénéité
	- Rôles des autres acteurs :
		- Dans le dispositif de formation à venir (comm, gestion de contenu, maintenance), pendant le projet (qui le porte, qui le soutient?)
	- Analyser la situation actuelle :
		- Comment les apprenant·e·s sont formés, localisation des compétences, ressources disponibles
	- Contraintes et contexte :
		- Environnement technique, confidentialité, durée du projet, moyens, culture et valeurs
	- Comment : méthodes
		- Tests/observations en situation
		- Entretiens individuels avec demandeurs, autres acteurs
		- Réunions de groupe
		- Enquêtes
		- Recueil indirect : experts du domaine; études internes ou externes
	- Contenu d'un document d'analyse de besoins
		- Analyse du contexte (dont la demande)
		- Identification et caractérisation de *tous les acteurs*, ainsi que de leurs besoins
			- Apprenant avec ses besoins de formation et ses connaissances
		- Contraintes
		- Reformulation de la demande : Se mettre d'accord sur ce qu'on a compris
- Phases de conception :
	- Besoins - Inspiration (analyse concurrentielle) - Connaissances sur les techno - Recherche documentaire - Connaissances
	- Production -> Idées -> Sélection -> Solution(s) générale(s)
	- Technique :
		- Ne pas être technophile, ex. je veux dvper avec ça, quite à oublier le besoin initial
		- Ne pas être technophobe, se rabattre sur les technique qu'on connait
	- Production d'idées :
		- Innovation & la première idée n'est pas toujours la meilleure
		- Comment : "think out of the box"; quantité > qualité quite à produire de la mauvaise qualité, la qualité va être reportée après ; différer le jugement
		- Brainstorming :
			- Se réunir dans un lieu clos, s'isoler pour ne pas être dans le quotidien
			- Jeter les premières idées
			- Sortir tout ce qui passe par la tête, approche par la qtt
			- Ne pas critiquer les autres, mais piquer les idées !
			- APRES : sélectionner les plus pertinentes
	- Sélection :
		- Une solution parmi les autres argumentée selon :
			- objectifs pédagogiques, autres besoins des acteurs, contraintes
		- Choix pédago : approches, théories invoquées, logique du séquencement
		- Scénario pédagogique
- Outil auteur :
	- Pourquoi? Gagner du temps, élaragir le cercle des contributeurs
	- Dreamweaver, Google Site, Weebly, Carrd, Wordpress, Synfig, OpenToonz, Flash, Director, Mediator, Toolbook
	- E-learning : Articulate, H5P, ExE, MindOnSite Solo, LAMS, smartbuilder, LearningApps, GoConqr, Hot Potatoes, Quizlet, ViewletBuilder, Captivate, ITycom, InscapeVTS
	- Jeux : E-adventure, Adventure Maker, Inform, Storyspace, Twine, Construct, Clickteam Fusion, Game Maker, Gdevelop, RPG Maker, GameSalad, CraftStudio, Kodu, Struckd, GameGuru, NWN2, Unreal, Unity, Unreal Engine, Godot, Massive software
	- Fonctions :
		- Langage haut niveau, bibliothèques, navigation, débogage, aide intégrée, tests rapides (Integrated Development Environment)
		- Choix en fonction des fonctionalités 'types' que donne l'outil auteur donne
		- Tendance "technology driven" : suppression fonctionnalité "difficile" & ajouter fonctionalité "facile"
		- Critères de choix : Equipes et environnement technique, ergonomie, ouverture, extensibilité, coût, pérénnité (produit et code)
	- Construct 3 : jeux 2D
	- Clickteam Fusion 2.5 : jeux 2D + simple
	- Twine 2 : Hypertexte/hypermedia
	- RPG Maker MV : RPG
	- Unity : jeux 2D,3D 

# Intervention de J. Theler - E-teach

- Technopédagogue :
	- Met en oeuvre des stratégies de formation en utilisant les technologies
	- Coordination entre plusieurs acteurs; faire la gestion de projet; veille et recherche (trouver des sources : Linkedin, newsletter : http://sydologie.com/, https://latelierduformateur.fr/
	- Ne pas forcément tout savoir faire, avoir l'humilité de trouver la personne qui saura mieux faire que nous même
	- La finalité est la *formation*, le moyen et le *digital* : *formation digitale*
	- Ne jamais obliger le participant, concevoir comme si à tout moment "je pars" -> se dire à tout moment pourquoi il resterait plutôt que d'aller ailleurs
	- Comment faire une motivation motivante : la finalité est la motivation
		- Motivation = disposition à consacrer de la ressource (énergie, temps, effort ...) à atteindre un objectif ~= carburant, ça se consomme
- Scénarisation pédagogique :
	- 1) La base : faire scénario non-ludique. Quelles sont les étapes d'apprentissage, une fois scénarisé, quels éléments de motivations pour appuyer ce chemin
	- 2) Vise la *motivation* et le *feedback*; *Progression* changement d'état t0 et t1; *valorisation* du fait de progresser dans la formation
	- ex. https://www.ladragueautravail.ch/ :
		- Contexte - contenu initial - challenge
		- Problème principal : "pourquoi je suis là? pourquoi mon entreprise fait ça?"
		- Travailler sur la *curiosité* "drague au travail"
		- *Implication* pas passif
		- *Prise de conscience* : conséquences graves, peut arriver dans leur entreprise
		- *Diagnostic & Formation* : c'est un sujet dont je devrais avoir plus d'information, où et comment faire
		- *Changement* : faire évoluer son savoir-faire et son savoir-être
		- Il y a des modèles de scénario, mais on ne peut pas en avoir un qui se refait *ad vitam eternam*
		- Segmenter le contenu et le cheminement du participant afin de l'emmener à changer ses pratiques
- Gamification :
	- Comment faire pour que le participant puisse faire le pas d'après
	- Objectif d'un jeu = créer une émotion / du plaisir
	- Objectif d'une activité gamifiée = encourager une action :
		- ne ressemble pas forcément à un jeu
		- tient compte d'autant de la pédagogie que du game design
		- ne parle pas qu'aux joueurs
	- Objectif d'une formation gamifiée = encourager une action permettant l'acquisition de compétences
	- Ajustement du comportement jusqu'à celui de gagner : la personne exprime des comportements et feedbacks pour renforcer le bon comportement
	- Scénario - Objectif - Choix et conséquences - Feedback (omniprésence, boucle rétroactive)
	- Trilogie du mal : points - badge - classement
	- Duolinguo : cas d'école de gamification, découper, défis quotidien
	- Avoir des méthodes, s'appuyer sur des théories
	- https://www.gamified.uk/ :
		- Prendre en compte de la culture du client, filtrer avec le client sur les différents types de gamification
		- Bien aussi quand itérations, et donne des idées
		- As-tu pensé à... sorte de checklist d'avoir ces cartes
	- Boucle d'engagement : ... -> motivation -> action -> feedback -> motivation ...
	- Invitation -> Introduction -> Activités -> Conclusion -> Envie d'appliquer
- Trois questions :
	- Quelle est la situation actuelle ?
	- Quelle est la situation souhaitée (Que souhaitez-vous voir à la fin) ?
	- Quels sont les leviers et freins à cette formation chez vous (contexte) ?
- On nous engage pour que le personnel change, non pas pour faire un e-learning
- Être transparent sur les enjeux et important pour se protéger pour analyser les besoins, freins, quels sont les changements sur lesquels changer

# Dimension narrative des JVP

- Définition de 'narratif' : temporel < suite d'actions < causalité < quête/obstacles < Ryan < Adam < structure en 3 actes
- [Ryan, 2004](https://books.google.fr/books?hl=fr&lr=&id=wStBECWtPwcC&oi=fnd&pg=PP11&dq=Ryan,+M.-L.+narrative+across+media&ots=VtgFjuUMOv&sig=DENqnDPR0hwKvrglSD2UhMSry18&redir_esc=y#v=onepage&q=Ryan%2C%20M.-L.%20narrative%20across%20media&f=false) :
	- Monde peuplé de personnages et objets
	- Changements causés par des événements non routiniers
	- Permet de reconstruire buts, plans, relations causales, motivations (ermet à la personne de reconstruire histoire, se place dans le contexte d'un récit qui est perçu par qqun)
	- => assez englobante, même si ennuyante est quand même un histoire
- Adam, 1994 :
	- Succession temporelle d'actions
	- Protagoniste
	- Transformation
	- Unité d'action - toutes les actions sont liées dans une unité
	- Causalité - cohérence de l'histoire
	- Evaluation - histoire doit se positionner et des choses qui bien/pas bien, faire passer un système de valeurs
	- => récit doit faire passer un message
- Pourquoi le récit ?
	- Mémorisation et cognition :
		- Structure notre environnement sous forme narrative
	- Contextualisation :
		- Un récit nous met en scène dans un monde, et donne contexte à une action
		- Situation authentique - expérience, lecteur peut se projeter
	- Engagement :
		- Immersion
		- Emotions (empathie, discursive développe du discours, ambiance, spectaculaire)
	- Dimension communicationnelle/éthique :
		- Une histoire fonctionne si elle transmet un message éthique (valeurs), il y a aussi une interprétation selon le système de valeur et l'individu
- Pourquoi le récit interactif :
	- Engagement ++ (agency, possibilité d'action)
	- Apprentissage par l'action (constructiviste)
	- Types d'interaction :
		- Sans modification de l'histoire - interagir à côté de l'histoire *ou* sur le discours (ordre d'apparition) *ou* sur le point de vue (une même histoire via deux personnages) *ou* accès à l'histoire incluse
		- Avec modification de l'histoire - paramétrages de surface *ou* user comme metteur·trice en scène *ou* user comme personnage secondaire ou principal
- Récit linéaire
- Récit non linéaire (par la bifurcation, récit à embranchements)
	- MAIS Explosion combinatoire
- Solution 1 : re-converger, illusion de choix
- Solution 2 : liens conditionnels, si A au début, fin A, si mémorisé choix B au début, fin B, mais ne résoud pas explosion combinatoire
- Solution 3 : générativité narrative
	- Au delà des structure arborescentes :
		- Oublier la métaphore spatiale
		- Générativité du lien qui existe entre deux noeuds
	- Générativité narrative :
		- Système génératif : La sortie est le résultat s'un calcul dynamique
		- Ordinateur vu comme une base de donées, un moteur/engine
- Solution 4 : "distendre" les liens (ordre partiel) :
	- Simulation en avant
	- Planification part de la fin pour revenir en arrière
- Solution 5 : Evenements conditionnels :
	- E1 se déclenche si ... et ... et ... si E1 va ajouter Q fin, conséquence peut arriver si autre condition aussi
- Solution 6 : Evenements génératifs :
	- Informer, donner, échanger, définition d'un système informel, calculé en fonction de structure générique - forme prédicative
- Solutions n : Modèles :
	- Personnages intelligents bas niveau (Les sims), haut niveau (FearNot!), acteurs
	- Limite : l'émergence doit avoir quelque contraintes
	- Simulation narrative : verbes et rôles (Storytron), fin d'histoire (Mimesis), Dilemmes (Gadin)
	- Approche structurale (Idtension, faire travailler un conflit)
	- Conflit, suspense (Mimesis)
- Concrètement dans un JV commercial : bifurcation, convergence, variables

# Mécanique
- On a un état du jeu, un système **dynamique** : Sn+1 = f(Sn, In) avec State et Input.
- Mécanique où toujours dans état différent où mobilise les états suivants
- Ex. Lapin couard, si +4 mais faux, on devrait le faire montrer aussi et ne pas juste à interagir avec réponse juste

# Retour sur Rendus
- Conception JV :
	- Si une partie bien développée, mieux que d'avoir 4 parties mal ficelées.
	- Mécanique est la prémice du code, point par point. 
	- Confusion entre le joueur et le personnage. Le joueur clique sur l'écran.
	- Mettre images pour illustrer sur autres rendus.
- Analyse besoin :
	- Travailler sur acteurs : commanditaire et apprenant, creuser plus sur les acteurs, hiérarchie, groupe technique, toutes les personnes qui gravient autour du projet.
	- Se détacher de ce que dit le commanditaire (proche de l'analyse de demande) - répéter mais aller au delà, c'est vous qui analysez la situation, pourquoi elle dit ça, quel est le vrai problème, chercher informations sur le sujet, vous même apporter des choses. Quitte à ce que soit *votre* analyse et remettre en question ce que dit le commanditaire.
	- 

# Références

- Capek, K. : Une vie Ordinaire. Éditions l'Âge d'homme (1934/2002)
- [Huizinga, J.: Homo ludens. Essai sur la fonction sociale du jeu. Gallimard, Paris (1951).](https://www.amazon.fr/Homo-ludens-Johan-Huizinga/dp/2070712796)
- Caillois, R.: Les Jeux et les Hommes. Gallimard, Paris (1958).
- Fendt, M. W., Harrison, B., Ware, S. G., Cardona-Rivera, R. E., & Roberts, D. L. (2012). Achieving the Illusion of Agency. In D. Oyarzun, F. Peinado, R. M. Young, A. Elizalde, & G. Méndez (Éds.), Fifth International Conference on Interactive Digital Storytelling (ICIDS). LNCS, 7648 (Vol. 7648, p. 114‑125). Springer. https://doi.org/10.1007/978-3-642-34851-8
- [Salen, K., Zimmerman, E.: Rules of play: Game design fundamentals. MIT press (2004).](https://www.amazon.fr/Rules-Play-Game-Design-Fundamentals/dp/0262240459/ref=sr_1_15?__mk_fr_FR=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=2A9SHN7B0QWAT&keywords=salen+and+zimmerman+rules+of+play&qid=1665334022&qu=eyJxc2MiOiIwLjc3IiwicXNhIjoiMC4wMCIsInFzcCI6IjAuMDAifQ%3D%3D&sprefix=salen+and+zimmerman+rules+of+play%2Caps%2C91&sr=8-15)
- [Szilas, N., Acosta, M.: A Theoretical Background for Educational Video Games : Games , Signs , Knowledge. In: Felicia, P. (ed.) Handbook of Research on Improving Learning and Motivation through Educational Games: Multidisciplinary Approaches. IGI Global (2010).](https://www.igi-global.com/chapter/theoretical-background-educational-video-games/52497)
- Henriot, J. (1969). Le jeu. Paris: Presses Universitaires de France.
- Manzoni, A. : Proposing a Framework for the analysis of integration in Serious Games. Thèse de Master, TECFA-FPSE, Univ. de Genève. (2017)
