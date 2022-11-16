# C++

<!-- vim-markdown-toc GFM -->

* [D00 - Basics](#d00---basics)

<!-- vim-markdown-toc -->

# D00 - Basics

- Namespace :
	- namespace Name {}
- Stdio streams :
	- `std::cout << "something"`
	- `<< std::endl`
	- `std::cin >> var`
- Class & Instance :
	- `Name.Header.hpp` // .hpp for 'h for cplusplus'
	- Deux points a la fin de la classe
	- constructeur
	- ~destructeur
	- Ces deux derniers ne retournent rien
	- .hpp declare la classe avec fonction et attributs qu'elle contient
	- .cpp definition des fonctions qui sont dans cette classe
- Member attributes and member functions :
	- Par defaut, chaque function a une variable qui est un pointeur sur
	  l'instance courante
- This :
	- Pointeur qui pointe sur l'instance courante de notre classe
- Initialization list :
	- Ne plus faire "this->my_var = fun_var" mais direct apres instantiating
	  function in .cpp do " : my_var(fun_var) "
- Const :
	-  on ne peut pas faire d'assignation a une const
	- `Sample::Sample( float const f ) : pi( f ) {}` = on initialise attribut pi a
	  la valeur f
	- `void bar( void ) const` = a aucun moment on va utiliser `this->`, cad,
	  modifier l'instance couante de notre classe
	- REFLEXE A PRENDRE quand on veut une fonction readonly/const
- Visibility :
	- Public et private vont permettre de controler l'encapsulation des membres
	  de notre classe
	- Prive, seulement possible que par l'interieur = fonctionnement interne de
	  votre code, pas ce qui est accessible par l'user
- Class vs Struct :
	- La difference entre class et struct c'est que struct a un scope par
	  default public et qu'une classe a un scope par defaut prive
	- Donc utilise classe
- Accessors c++ :
	- Fonction proxy pour checker dans private
- Comparaison c++ :
	- Egalite physique = au niveau adresse d'une classe
	- Egalite structurelle = au niveau d'une instance d'une classe
- Attributs non membre et fonction non membre :
	- Variable et fonction d'instance = membre (utilise nom de la classe)
	- Variable et fonction de classe = non membre (possibilite d'utiliser this)
	- Une fonction non-membre en static n'a PAS le parametre this, donc on ne
	  peut jamais y faire appel
- Conclusion :
	- initialisation de list
	- const
