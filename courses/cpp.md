# C++

<!-- vim-markdown-toc GFM -->

* [D00 - Basics](#d00---basics)
* [D01 - Basics 2](#d01---basics-2)
* [D02](#d02)
* [D03](#d03)

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
	- Initialisation de list
	- Const

# D01 - Basics 2

- New and delete :
	- Quand on veut allouer memoire : utilise new
	- On ne peut pas passer en parametre dans un new Array[n], pour passer de parametres il faut le faire manuellement.

- References :
	- Une reference est un pointeur qui est constant, toujours dereference (on dereference quand on met l'etoile devant le pointeur) et jamais nul
	- Quand reference on SAIT qu'elle pointe sur quelque chose !
	- On ne peut pas avoir une reference et ne pas l'initialiser au debut
	- Quand pas encore de valeur, peut mettre un pointeur.
	- Si ca ne doit pas exister ou que ca doit changer => pointeur
	- Si ca doit toujours exister et ne jamais changer => reference
	- Const <type>& myfunction(void); is the same than <type> const & myfunction(void) : the first one is preferred in the web, the last one is normally how it should be written
	- "myfunction(void) const" in cpp is only when you do not change something in the class while doing this->_something = somethingelse
	- Remember : static myfunction is used in C just for use in the C file
	- Return-by-value = he copy-constructor is called, and a temp instance is created on the stack vs return-by-reference nope
	- Return-by-const-ref only protects
	- A pointer stores the address of the variable A; it points to the mem loc of A
	- A reference to A just makes an alias for it; it does not point to A by storing its address in a separate mem loc + a reference shares the same mem address
	- References are usually preferred over pointers whenever you don't need reseating. This usually means that references are most useful in a class's public interface. References typically appear on the skin of an object, and pointers on the inside.

- Filestream :
	- ifs = input file stream

# D02

- https://www.cprogramming.com/tutorial/floating_point/understanding_floating_point.html
- Ad-hoc Polymorphisme :
	- Surcharge de fonction = definir plusieurs fonctions ayant le meme nom mais prenant parametres differents
	- Definir sur meme nom mais pas meme parametre

# D03

- Inheritance :
	- 
