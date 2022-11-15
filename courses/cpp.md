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
	- ne plus faire "this->my_var = fun_var" mais direct apres instantiating
	  function in .cpp do " : my_var(fun_var) "
- 
	- 

