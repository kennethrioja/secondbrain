# C++

<!-- vim-markdown-toc GFM -->

* [D00 - Basics](#d00---basics)
* [D01 - Basics 2](#d01---basics-2)
* [D02](#d02)
* [D03](#d03)
* [D03](#d03-1)
* [D04](#d04)

<!-- vim-markdown-toc -->

leaks -atExit -- ./executableName

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
	- on ne peut pas faire d'assignation a une const
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

- Allocate on stack or heap ?
	- Automatic variables are automatically destroyed when going out of context
	- Variables allocated on the stack are automatic variables
	- Members are automatic variables whose destructors get called when its
	  owner is destroyed
	- Variables/Members that you have to call delete on, are not automatic
	  variables and are on the heap

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
	- If a class is optionnally present somewhere, if another class needs to
	  take it, ask to take it as a reference

- Filestream :
	- ifs = input file stream

# D02

- https://www.cprogramming.com/tutorial/floating_point/understanding_floating_point.html
- Ad-hoc Polymorphisme :
	- Surcharge de fonction = definir plusieurs fonctions ayant le meme nom mais prenant parametres differents
	- Definir sur meme nom mais pas meme parametre

# D03

- Inheritance :
- Operator Overload :
	- Notation infix : 1+1
	- Prefix (fonctionnelle) +11 ou +(1,1) ou 1.+(1) instance 1 et fonction membre de cette instance '+' a laquelle envoie param 1
	- Postfix 11+

- Canonical form :
	- 1 constructeur par default : Sample(void);
	- 1 constructeur par copie prenant une instance de la classe qu'on est en
	  train de declarer pour faire une copie de cette classe (nouvelle instance
	  de cree): Sample(Sample const & src);
	- 1 operateur d'assignation permettra une assignation a partir d'une autre
	  instance cette nouvelle classe (mise a jour de l'instance courante) :
	  Sample& operator=(Sample const & rhs)
	- 1 destructeur

# D03

- Inheritance :
	- : public ClassName, pour heriter

# D04

- Sub-typing polymorphism :
	- virtual function = methode
	- grace a virtual la resolution de l'appel de fonctions a devenir dynamique
- Abtract classes and interfaces :
	- Methode pure when = 0, means that no definition on this method, means that
	  cannot intanciate it
	- ADD A prefix for Abstract (some methods will be pure)
	- En gors, le mettre c'est pour dire que le parent n'en a aucune utilite
	  mais que les enfants peuvent en avoir un comportement difference (surtout
	  si virtual)
	- Certains comportements sont definis et d'autres non
	- ADD I prefix for Interface = all methods are pure and NO attributes
