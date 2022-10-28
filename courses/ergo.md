# Design centré utilisateur·trice et ergonomie

## Equipe enseignante : Mireille Bétrancourt, Mattia Fritz, Julien Venni

## Table of contents
<!-- vim-markdown-toc GFM -->

* [Qu'est-ce que l'ergonomie ?](#quest-ce-que-lergonomie-)
* [Evolution des approches en ergonomie des IHM](#evolution-des-approches-en-ergonomie-des-ihm)
* [Démarche de conception centrée users](#démarche-de-conception-centrée-users)
* [Analyse de l'activité de l'utilisateur](#analyse-de-lactivité-de-lutilisateur)
* [Méthodes de base](#méthodes-de-base)
	* [Entretien](#entretien)
	* [Questionnaire exploratoire](#questionnaire-exploratoire)
	* [Observation](#observation)
* [Méthode complémentaire](#méthode-complémentaire)
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

- [Hassenzahl, 2003](https://link.springer.com/chapter/10.1007/1-4020-2967-5_4)
    - Sont distinguées des qualités pragmatiques perçues par l'user (ex. perception de l'utisabilité -> p. de l'utilité -> acceptabilité (intention d'usage) -> acceptation (usage effectif), les qualités hédoniques
        - *Simulation*
        - *Identification*
        - *Evocation*

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

- Skill Rule Knowledge de Rasmussen
    - <img src="https://www.researchgate.net/profile/Joao_Carlos_Lima/publication/279226308/figure/download/fig1/AS:378915546779648@1467351914563/Behavioral-model-skill-rule-knowledge-SRK-Rasmussen-1983.png" width="500">(retreived from https://www.researchgate.net/figure/Rasmussens-model-automation-evolution-and-contributing-discipline-emergence_fig1_289849041)
    - Alertes lues mais pas souvent comprises par les users
    - Soit automatisé et le fait automatiquement (boucle automatique) - implicite
    - Comportement réglé par des règles, est-ce qu'on est bien dans la situation? Règles connue mais que je dois activer - peut être enseigné
    - Résolution de problèmes, signes contradictoires et on rentre dans ttt de résolution de problème, prendre décision sur raisonnement et plannification - ex. scénario, alien débarque, etc.
	- Régulation sur les automatismes -> Régulation sur les règles (identification des problèmes et plans d'actions à mettre en oeuvre) -> Régulation sur les connaissances (interpréter les conséquences)

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

## Entretien

## Questionnaire exploratoire
    
## Observation
    
# Méthode complémentaire

# TODO

- idée : 
    - DIB74
    - ask Nico pour asso roller street
- lire les trois méthodes de base puis répondre au QCM
- s'inscrire à méthode complémentaire, lire article et produire carte conceptuelle
- 4 techniques aliées à l'entretien pour avoir informations.
    - pourquoi
    - événements remarquables, mal/très bien passé/problème
    - focus group : entretiens structurés pour recueil de besoins

# Refs

## Base

[Lancry, A. (2016). L'ergonomie : «Que sais-je?» n° 1626. PUF.](https://www.amazon.fr/Lergonomie-Alain-Lancry/dp/2130749887)<br>
[Garrett, J. J. (2011). The elements of user experience (2e éd.). New Riders.](https://ptgmedia.pearsoncmg.com/images/9780321683687/samplepages/0321683684.pdf)<br>
[Lallemand, C. & Gronier, G. (2016). Méthodes de design UX. 30 méthodes fondamentales pour concevoir et évaluer les systèmes interactifs. Paris : Eyrolles](https://livre.fnac.com/a10497413/Carine-Lallemand-Methodes-de-design-UX-2e-edition)<br>

## Cours
[Thomas, J. (2000). A review of research on project-based learning. Autodesk Foundation. Retrieved 09.20.2022 from http://www.bobpearlman.org/BestPractices/PBL_Research.pdf](http://www.bobpearlman.org/BestPractices/PBL_Research.pdf)<br>

