# C++

<!-- vim-markdown-toc GFM -->

* [D00 - Basics](#d00---basics)
* [D01 - Basics 2](#d01---basics-2)
* [D02](#d02)
* [D03](#d03)
* [D03](#d03-1)
* [D04](#d04)
* [Recap :](#recap-)
* [D05](#d05)
* [D06](#d06)

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
	  makenoise()
	- Certains comportements sont definis et d'autres non
	- ADD I prefix for Interface = all methods are pure and NO attributes

# Recap :

- Namespace :
	- p.ex. on a une variable globale 'gl_var = 1'
	- on peut creer un `namespace name { gl_var = 3 }`
	- Operateur de resolution de portee (en: scope resolution opeator) = `namespaceName::`
	- Au test si on fait : printf(gl_var) et printf(name::gl_var) on aura 1 et 3
	- Peut etre utile pour different tests avec meme variable globale?
- Fonction et attributs non-membres :
	- Non-membre = utile simplement au niveau de la Classe, et non au niveau des
	  instances.
	- Une fonction non-membre ne peut pas utiliser `this` (cpp ne passe pas
	  `this` en premier parametre, comme pour les autres fonctions membre)
	- Quand met `static` au debut d'une definition d'une fonction 'non-membre', ex. static int
	  getNbInst(), avec un attribut 'non-membre', ex. static int _nbInst, on
	  va devoir ecrire : `int ClassName::getNbInst(void) { return ClassName::_nbInst; }`
	  et l'initialisation de l'attribut static/non-membre dans le .cpp :
	  `int	ClassName::_nbInst = 0` (=/= var globale !!)
	- Utile quand veut compter le nombre d'instances
	- Ne pas oublier dans constructeur d'incrementer ClassName::_nbInst
- Travailler avec le plus de `const` possible, evitera les crash :
	- Quand on peut un attribut membre constant (ex. pi) :
		- ex. dans class definition (.hpp) on a : float `const` pi; ClassName(float `const` f)
		- dans .cpp, il faut que : ClassName::ClassName(float `const` f) : pi(f) {}
	- Quand on veut une fonction readonly ou qui ne modifie jamais rien dans this-> :
		- mets void bar( void ) `const` = a aucun moment on va modifier en
		  utilisant `this->attributeName = *`, cad, modifier l'instance couante de notre classe
- Quand tu as de l'heritance pour une methode, mets `virtual`, ex.
- `*` pointeur = non vide, `&` reference = can be empty
- Pour instancier une classe,
	- soit utilise : Class`*` name = `new` Class(); methods are called with
	  `->` ; `delete` name
	- soit utilise : Class name; methods are called with `.` ; then destructor at the end of main();
- Classe Abtraite : mets prefix `A` avant la classe, c'est une classe qui
  ne peut pas etre instanciee car contient au moins une methode pure.
  Methode pure est quand il n' a pas de definition dans la classe et donc finit par `= 0` (.hpp)
  : permet d'avoir des comportements specifiques aux classes enfants.
- ex. virtual void	makeSound(void) const = 0;
- Multiple Class instanciation :
	- Class* table[n];
	- for (int i = 0; i < n; i++) { delete table[i]; }
- leaks -atExit -- ./executableName

# D05

- Nested Classes :
	- In Cat Class definition, can put Leg class, in main to define Cat's Leg : Cat::Leg
- Exceptions :
	- hpp :
		- #include <stdexcept>
		- class NameException : public stdd:exception { public : virtual const char* what() const throw(); };
	- try {...; throw(Class::NameException());} catch (NameException &e) { cout << e.what() << endl; }

# D06

- (C) Type conversions :
	- Cast implicite (double b = int a;) induit une Conversion/Promotion : transformer le codage d'un octet vers un autre codage pour
	  garder une meme valeur
	- Cast explicite (double d; int f = (int) d) pour faire une Demotion de type
- (C) Type reinterpretation :
	- Conversion identitaire = reinterpretation
	- `void *` permet de contenir une adresse sur n'importe quel type : float
	  a = 42.42; void* b = (*void) &a; int* c = (int*) b //this oes not work 
- (C) Type qualifier reinterpretation :
	- from const to non-const BUT DON'T DO IT
- (C++) Upcast / Downcast (contexte d'arbre d'heritage de classe) : Parent to child and vice-versa (beware, can compile but in run time no !)
- (C++) Static cast :
	- `static_cast<void>(var)`
	- Se fait entre valeurs direct et aussi de maniere verticale au sein d'un meme arbre de classe
	- Se fait au moment de la compilation = static
- (C++) Dynamic cast :
	- `ChildClass &	= dynamic_cast<ChildClass *>(obj)`
	- Le seul a se faire au run time / a l'execution
	- Ne va fonctionner que dans le cas d'une instance polymorphique = au moins une des fonctions devra etre virtuelle
	- Uniquement pour un downcast
	- Uniquement sur des casts de pointeurs ou de reference
	- Utile pour des plugins
- (C++) Reinterpret cast :
	- `float	a = 420.42f;	void *	b = &a;`
	- `int *	c = reinterpret_cast<int *>(b);`
	- `int &	d = reinterpret_cast<int &>(b);`
	- Utile pour les retypages, quand on recoit donnes brutes et on veut les retyper (ex. socket)
- (C++) Const cast :
	- `const_cast<int *>(var)`
- (C++) Cast operators :
	- `operator	type()	{ return this->_classVar; }`
	- Va permettre de caster directement a la definition de la variable.
- (C++) Explicit keyword:
	- `explicit	C( B const & _ )	{ return; }` va permettre d'interdire le cast implicite de B en C;
- Cast :			| Conv. | Reint | Upcast | Downcast | Type qual.
- Implicit			|  Yes  |       |   Yes  |          |
- static_cast		|  Yes  |       |   Yes  |    Yes   |
- dynamic_cast		|       |       |   Yes  |    Yes   |
- reinterpret_cast	|       |  Yes  |   Yes  |    Yes   |       
- const_cast		|       |       |        |          |    Yes


