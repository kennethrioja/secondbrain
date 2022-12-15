# Design centré utilisateur·trice et ergonomie

## Equipe enseignante : Mireille Bétrancourt, Mattia Fritz, Julien Venni

## Table of contents
<!-- vim-markdown-toc GFM -->

* [Qu'est-ce que l'ergonomie ?](#quest-ce-que-lergonomie-)
* [Evolution des approches en ergonomie des IHM](#evolution-des-approches-en-ergonomie-des-ihm)
* [Démarche de conception centrée users](#démarche-de-conception-centrée-users)
* [Analyse de l'activité de l'utilisateur](#analyse-de-lactivité-de-lutilisateur)
* [Méthodes de base](#méthodes-de-base)
* [Méthode complémentaire](#méthode-complémentaire)
* [Persona](#persona)
* [Carte d'expérience](#carte-dexpérience)
* [Conception centrée utilisateur de site Web](#conception-centrée-utilisateur-de-site-web)
* [Les éléments de l'user expérience](#les-éléments-de-luser-expérience)
* [AttrakDiff](#attrakdiff)
* [Tri de cartes](#tri-de-cartes)
* [Notion d'hypertexte](#notion-dhypertexte)
* [TODO](#todo)
* [Refs](#refs)
	* [Base](#base)
	* [Cours](#cours)

<!-- vim-markdown-toc -->

# Qu'est-ce que l'ergonomie ?

- [Nielsen](https://www.nngroup.com/articles/usability-101-introduction-to-usability/), 4 critères que doit suivre une application informatique pour être ergonomique : 
    1. Facile à apprendre (*Learnability*)
    2. Efficient : atteindre les objectifs de l’user en un temps minimal (*Efficiency*)
    3. Est-ce qu'en revenant, on reprend rapidement ce qu'on a appris? (*Memorability*)
    4. Eviter un maximum d’erreurs et facilite leur correction (*Errors*)
    5. Agréable à utiliser (*Satisfaction*)
- L'ergonomie est l'étude scientifique et l'amélioration de la relation entre l'Homme (Nomos) et ses moyens, méthodes et milieux de travail (Ergon), son but est d'adapter l'environnement à l'individu et non le contraire. (SELF, 1969)
- L'ergonomie procède en plusieurs étapes : analyse de la demande, observation en contexte, entretiens, puis rapport de diagnostic et recommandations.
- Le modèle utilisé est celui de l'**adéquation** : entre la représentation des users (attentes et actions prévues) et les représentations induites.
- Approche interdisciplinaire : psychologique - sociologique - physiologique - technique

# Evolution des approches en ergonomie des IHM

1. Ergonomie humaniste (machine>utilisateur)
    - Adaptation du milieu à l'humain - applicatif, aboutir a une meilleure adaptation à l'homme des moyens technologiques
2. > Approche systémique (triangle humain-machine-contexte)
    - Etat de vigilance ~ Etat mécanique ~ Configuration
3. >> Conception centrée utilisateur (intégration user dès début, au moyen de mesures empiriques, de méthode de conception itérative et d'équipes de conception pluridisciplinaire)
    - cf. Gould & Lewis (1985) : première étape est de connaître les besoins utilisateurs.

# Démarche de conception centrée users

- [Technology Acceptance Model 3 (Venkatesh & Bala, 2008)](https://doi.org/10.1111/j.1540-5915.2008.00192.x) à partir du modèle initial TAM 1 de [Davis (1989)](https://www.jstor.org/stable/249008?origin=crossref)
    - <img src="https://edutechwiki.unige.ch/fmediawiki/images/9/9c/TAM.gif" width="700"> (retreived from https://edutechwiki.unige.ch/fr/Mod%C3%A8le_d%27acceptation_de_la_technologie)
    - Les représentations des objets ont des influences sur nos comportements (théorie de l'action plannifiée, [Azjen (1985)](https://doi.org/10.1007/978-3-642-69746-3_2), [Azjen (1991)](https://doi.org/10.1016/0749-5978(91)90020-T)
    - L'utilité perçue est le facteur ayant le plus de poids car il permet aussi de considérer le système comme améliorant sa productivité
    - Les *variables individuelles* (ex. perception de compétence), l'*influence sociale*, les *caractéristiques du système* et les *conditions organisationnelles* sont d'autres facteurs influençant ce modèle.
    - Critique : influence sociale influence la perception de l'utilité.
    - Meta-analysis de [Scherer et al., 2019](https://www.sciencedirect.com/science/article/abs/pii/S0360131518302458?via%3Dihub)
	- Quelque chose qui est facile à utiliser donne l'impression que cette application va leur être utile mais le fait qu'être utilisable ne suffit pas. TAM 1 de [Davis (1989)](https://www.jstor.org/stable/249008?origin=crossref)
	- Si facile -> utile, MAIS PAS INVERSE

- Expérience Utilisateur : [Hassenzahl, 2003](https://link.springer.com/chapter/10.1007/1-4020-2967-5_4)
    - Sont distinguées des qualités pragmatiques perçues par l'user (ex. perception de l'utisabilité -> p. de l'utilité -> acceptabilité (intention d'usage) -> acceptation (usage effectif), les qualités hédoniques
        - *Simulation*
        - *Identification*
        - *Evocation*
	- Intentions des concepteurs -> Qualités hédoniques (simulation, identité sociale) -> Qualités pragmatiques (clrté, structure, prévisibilité) -> Attractivité (esthétique,) ->

- Application au cas des formateurs HES santé (Lecoultre, mémoire MALTT 2017)
	- Sentiment d'efficacité personnelle des Technologies d'Information et de Communication des Enseignants (TICE) a un effet (.79) sur la perception de l'utilité pédagogique, ce qui va permettre un usage par les élèves (r =.27, "Front-office")
	- De plus le SEP TICE a un effet positif (.41) sur les usages "Front-Office"
	- Variables démographiques n'ont pas d'effet sur l'usage Front-Office, c'est bien le sentiment d'efficacité personnelle qui le permet (et surtout effet de l'âge).

# Analyse de l'activité de l'utilisateur

- Comment modélier l'activité humaine ? & Quelle relation avec la conception d'interfaces ?
	- Activité prescrite (règles, but) vs. activité réelle (critères implicites avec contraintes, liés à l'expertise aussi)
	- Leontiev (1981), Engeström (1987) :
		- L'outil permet la médiation entre le sujet et l'objet
		- Communauté d'acteur aussi entre le sujet et l'objet

- Affordance : Gaver (1991) & Borowska (2015) : Deux axes possibilité d'action x perçue, quatre quadrants.
- Catacrèse (Rabardel) : utilisation détournée d'un objet pour faire autre chose "Un bon outil doit permettre la catacrèse"

- Skill Rule Knowledge de Rasmussen
    - <img src="https://www.researchgate.net/profile/Joao_Carlos_Lima/publication/279226308/figure/download/fig1/AS:378915546779648@1467351914563/Behavioral-model-skill-rule-knowledge-SRK-Rasmussen-1983.png" width="500">(retreived from https://www.researchgate.net/figure/Rasmussens-model-automation-evolution-and-contributing-discipline-emergence_fig1_289849041)
    - Alertes lues mais pas souvent comprises par les users
    - Soit automatisé et le fait automatiquement (boucle automatique) - implicite
    - Comportement réglé par des règles, est-ce qu'on est bien dans la situation? Règles connue mais que je dois activer - peut être enseigné
    - Résolution de problèmes, signes contradictoires et on rentre dans ttt de résolution de problème, prendre décision sur raisonnement et plannification - ex. scénario, alien débarque, etc.
	- Régulation sur les automatismes -> Régulation sur les règles (identification des problèmes et plans d'actions à mettre en oeuvre) -> Régulation sur les connaissances (interpréter les conséquences)
	- Skills (automatisés) x Rules (activation de règles apprises) x Knowledge (résolution de problème)

- Thèse de Rolf Wipfli (2012) :
	- 50 et 100% des alertes ne sont pas prises en compte (Sijs et al., 2006)
	- Version adaptée permet :
		- moins de fixation sur les zones d'alerte
		- moins de transitions entre zones d'alerte et zone de prescription
		- moins de temps de résolution
		- plus de rejet d'alertes
		- moins d'ouvertures d'alertes
		- autant de corrections dans les prescriptions
		- autant de facilité d'utilisation
		- moins d'efficience
		- moins de support à l'activité
		- moins de satisfaction générale (habitudes)
	- Prendre en compte de l'activité réelle des users (design écologique)

# Méthodes de base

- [Entretien, questionnaire exploratoire, méthode complémentaire](../articles.md#lallemand--gronier-2016--méthodes-de-design-ux-30-méthodes-fondamentales-pour-concevoir-et-évaluer-les-systèmes-interactifs)
- Dans conception centré utilisateur, on s'adapte aux besoins du public cible, ex. si consultant et dit "je sais comment ça va être" alors pas forcément centré utilisateur
    
# Méthode complémentaire

- [Focus Group](../articles.md#baccino-t-bellino-c--colombi-t-2004-mesure-de-lutilisabilté-des-interfaces-hermes-science-publications)
- Pourquoi/Comment :
	- Objectif : Faire expliciter les tâches en buts et sous buts décomposés, mettre en évidence la structure hiérarchique des tâches
	- Participants : Interviewé et intervieweur + retranscripteur
	- Déroulement : Crayon-papier, enregistrement, Interview, et quand silence, repose, à la fin résumé.
	- Données : nom des tâches et descriptions
	- Traitement : 1) lecture des interviews (familiarisation), 2) description des tâches, 3) analyse de la tâche (lien des tâches entre elles, hiérarchie), 4) rechercher éléments manquants (repréparer interview), 5) formaliser la tâche (description précise, comparer des interviews)
	- Limites : long et lourde, débutants si pas experts, difficile de s'arrêter
	- Avantages : facile à appliquer, systématique, exhaustif, facile de comparer entre sujets et groupes
	- Quand :
		- Plutôt à faire au début, dégrossissement, structure avec l'arbre, arriver à de l'opérationnel : à faire le plus tôt possible
		- *Tâche prescrite*, à faire avant, la contraster avec la tâche prescrite, regarder les écarts entre les personnes ou la même personne
- Information à la demande :
	- Objectif : à travers un script, on va demander les pp de résoudre un problème
	- Participants : un expérimentateur, un expert si pas expert, et un participant
	- Déroulement : à travers questions, répondre, avoir données et résoudre le problème. L'expérimentateur sait
	- Données obtenues : informations réelles, besoin qu'a le participant et dand quel ordre le fait
	- Avantages : facilité de ttt des données
	- Limites : validité écologique, connaissance de l'expérimentateur
	- Quand : A faire avant la conception, et intérêt d'amélioration de l'interface.
	- Exemple :
		- Application de navigation, personne qui accompagnait, jouait le rôle de l'application et attendait "à la demande" les questions de l'utilisateur·trice
		- Marche très bien pour le classement de documents
- Technique de sincidents critiques :
	- Objectif : permet étude de terrain, étude de iagnostic, collecter des récits d'incidents (négatifs, positifs)
	- Participants : utilisateurs du système, pas un nombre précis, mais plus sur le nombre d'incidents
	- Déroulement : notes et moyen d'enregistrement, 1) quel est le but de l'activité étudié en interiewant le spécialiste, 2) mener l'interview, 3) expliciter les consignes pour être au clair sur les objectifs 
	- Données obtenues : 50/100 récits, ensemble de courts récits d'incidents
	- Traitement : classifier les incidents, puis interpréter l'ensemble des incidents
	- Avantages : peu rigide, simple, permet d'isoler rapidement les problèmes clés
	- Limites : plus de négatifs, et pp craignent que ce qui va être utilisé contre eux, évalue capacité de la personne et non de l'objectif; doit être suivie par d'autres études; d'arriver à avoir des incidents critiques
	- Quand : après la conception, plus pour évaluation
	- Arrêt du recueil quand saturation des données

# Persona
- "Raconte-moi la dernière fois que tu..." ou "Lorsque tu as fait..." : préciser une séquence précise
- On doit poser le moins de question possible, juste utiliser les relances (Pourquoi, Comment). Avoir un guide d'entretien pour explorer.
- Entretien semi-directif, on ne pose qu'une question large
- Pour bibliographie/infos personnelles : Demander de se présenter, mais ne pas trop être intrusif (question de brise-glace).
- Construction fictive mais ne pas être similaire, avoir une certaine créativité, pas nécessairement une personne réelle.
- **Synthèse avec éléments qui permettent d'avoir un profil cible**.
- Répondre à tous les profils d'users cibles. L'idée d'en avoir plusieurs ne pas s'enfermer dans un profil cible.

# Carte d'expérience
- Identifier des publics cibles, l'ergonomie, contenu et les fonctionalités
- Utilisabilité : adapter le contenu des fonctions par rapports aux users et leur expérience.
- Utilité : fournir un contenu utile

# Conception centrée utilisateur de site Web
- Stratégie :
	- Information : Objectif stratégique
	- User : Besoins utilisateur·trice, activités, trouver les points de contact entre ce qu'ils proposent et ce qu'ils font
	- Le but n'est pas de trouver comment faire l'activité, mais de faire l'activité (activité finalisée)
- Focus :
	- Information : Contenu
	- User : Fonctionalités
- ...

# Les éléments de l'user expérience

- Représentations (ce que j'en sais ou crois que j'en sais)
- Attitudes (ce que j'en pense, ce que j'aime ou non)
	- Lien avec Représentations grace aux dimensions pragmatiques (ce que je peux faire de l'interface) et hédonique (me plaît ou pas), cf. Hassenzahl
- Perceptions subjectives (évaluées par questionnaires/entretiens) et pratiques effectives (évalués par observations, traces, inthe wild ou en test UX)
- Grille heuristiques :
	- Conception pour informer les choix d'interface
	- Evaluation pour systématiser une inspection experte (expert ergonome ou UX) ou synthétiser les résultats d'un test UX
	- Finalités : permet structure l'argumentation et diagnostique pour savoir comment agir
- [Nielsen (1994) - 10 heuristiques](https://www.nngroup.com/articles/ten-usability-heuristics/) :
	- Facilité d'apprentissage, efficience, gestion des erreurs, satisfaction
- [Lee & Kozar (2012)](https://doi.org/10.1016/j.dss.2011.10.004) :
	- Sur les sites web, validés empiriquement par questionnaire
- [Bastien & Scapin (1995)](https://doi.org/10.1080/10447319509526114) :
	- Recueil d'un grand nombre de données expérimentales et de recommandations d'experts

# AttrakDiff

- [Lallemand et al. (2015)](#lallemand-et-al-2015--création-et-validation-dune-version-franc-aise-du-questionnaire-attrakdiff-pour-lévaluation-de-lexpérience-utilisateur-des-systèmes-interactifs)

# Tri de cartes 

- Matrice de similarité = similarité entre chaque
- Dendogramme = groupes

# Notion d'hypertexte

- Raisonnement argumentatif, ex. inversion de la charge de la preuve ("si ça n'a pas été prouvé, alors c'est juste")
- Positions / Attitudes épistémologiques, perception des connaissances individuelles et collectives
- Affirmations sur des phénomènes
- Croyances <-> Affirmation <-> Connaissances sociales
- Evaluation - sélection (contraintes situationnelles) - traitement (connaissances et compétences) (Rouet & Tricot, 1998; Sharit et al., 2008)
- TRACE model (Rouet & Britt, 2011)
- Logique sémantique (dans le texte, liens pour aller dans d'autres pages)
- Logique hiérarchique (rubriques et pages)
- Aide à la navigation : Plan du site, indicateur visuel, points de repère (pied de page, toujours au même endroit), fil d'Ariane (suite du chemin à parcourir sur cette page), prévisualise (évite d'ouvrir/fermer, etc).
- Outil de soutien pédagogique : Glossaire, nuage de mot, parcours conseillés.

# TODO

# Refs

## Base

[Lancry, A. (2016). L'ergonomie : «Que sais-je?» n° 1626. PUF.](https://www.amazon.fr/Lergonomie-Alain-Lancry/dp/2130749887)<br>
[Garrett, J. J. (2011). The elements of user experience (2e éd.). New Riders.](https://ptgmedia.pearsoncmg.com/images/9780321683687/samplepages/0321683684.pdf)<br>
[Lallemand, C. & Gronier, G. (2016). Méthodes de design UX. 30 méthodes fondamentales pour concevoir et évaluer les systèmes interactifs. Paris : Eyrolles](https://livre.fnac.com/a10497413/Carine-Lallemand-Methodes-de-design-UX-2e-edition)<br>

## Cours
[Thomas, J. (2000). A review of research on project-based learning. Autodesk Foundation. Retrieved 09.20.2022 from http://www.bobpearlman.org/BestPractices/PBL_Research.pdf](http://www.bobpearlman.org/BestPractices/PBL_Research.pdf)<br>

