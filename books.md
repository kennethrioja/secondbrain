# Books

## Table of Contents
<!-- vim-markdown-toc GFM -->

* [Deep Work - Cal Newport](#deep-work---cal-newport)
* [Game Programming Patters - Robert Nystrom](#game-programming-patters---robert-nystrom)
* [Learning Vim Script The Hard Way - Steve Losh](#learning-vim-script-the-hard-way---steve-losh)
* [Making Games for Impact - Kirt Squire](#making-games-for-impact---kirt-squire)
* [The Gamer's Brain - Celia Hodent](#the-gamers-brain---celia-hodent)
* [Rules of Play - Katie Salen Tekinbaş and Eric Zimmerman](#rules-of-play---katie-salen-tekinba-and-eric-zimmerman)

<!-- vim-markdown-toc -->

# Deep Work - Cal Newport

# [Game Programming Patters - Robert Nystrom](http://gameprogrammingpatterns.com/contents.html?link_credit=KennethRioja)

http://gameprogrammingpatterns.com/architecture-performance-and-games.html#what-is-*good*-software-architecture

[Introduction](https://gameprogrammingpatterns.com/introduction.html)
- Challenges commonly encountered in games
    - Time and sequencing is important : have it done at right order at right time
    - Build rapidly without stepping on each other's toes or leaving footprints : github and clean code
    - Interactions in game must not add more difficulty : name each variable so that we can find them easily
    - Performance is critical in games : squeeze and be more efficient

[Architecture, Performance, and Games](https://gameprogrammingpatterns.com/architecture-performance-and-games.html)
- Architecture is about change : A "good software architecture" is when the entire program is crafted in anticipation of a change.
- "The measure of a design is how easily it accomodates changes"
- Software architecture : "minimize the amount of knowledge you need to have in-cranium before you can make progress"
- [YAGNI](https://en.wikipedia.org/wiki/You_aren't_gonna_need_it) = "You are'nt gonna need it"
- [Observers](https://gameprogrammingpatterns.com/observer.html)
- "Game design requires a lot of experimentation and exploration (...) it's common to write code that you *know* you'll throw away (...) Prototyping is a perfectly legitimate programming practice"
- If you prototype an idea, either make sure that it cannot be maintained and must be rewritten, either if you think it may be kept, you may have to defensively write it well - or write it in a different language.
- Get data structures and algorithms right in that order

[Design Patterns Revisited](https://gameprogrammingpatterns.com/design-patterns-revisited.html)

[Command](https://gameprogrammingpatterns.com/command.html)
- "A command is a 'thingyfy' method call"
- Callbacks = [function pointer in C](https://www.geeksforgeeks.org/callbacks-in-c/)
- [Virtual function](https://www.geeksforgeeks.org/virtual-function-cpp/) = can be overridden by a derived class
- Create a base class "Command", and each subclass for each different game action, then in inputHandler do Command* _buttonX, and in handleInput() { if (isPressed(X)) _buttonX->execute() }
- Useful when want to do something else while in the Command
- Undo & Redo : recording the set of commands every entity performed each frame

[Flyweight](https://gameprogrammingpatterns.com/flyweight.html)
- Flyweight = when you have objects that need to be more lightweight because you have too many of them
- It is purely about efficiency
- Tree { Model {Mesh;Bark;Leaves}; Params }
- Separation between intrinsic state, "context-free" stuff (ex. geom and textures of tree) AND extrinsic state (ex. pos, scale, col)
- 

Other resources :
- [Game Programming Gems](http://www.satori.org/game-programming-gems/?link_credit=KennethRioja) series.
- [Design Patterns: Elements of Reusable Object-Oriented Software by Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides](https://www.academia.edu/43687858/Design_Patterns_Elements_of_Reusable_Object_Oriented_Software_by_Erich_Gamma_Richard_Helm_Ralph_Johnson_John_Vlissides?link_credit=KennethRioja)
- 

# [Learning Vim Script The Hard Way - Steve Losh](https://learnvimscriptthehardway.stevelosh.com/?link_credit=KennethRioja)

# Making Games for Impact - Kirt Squire

- p.3 : "interactive entertainment technology or VG are now accepted as tools for learning (Squire, 2011), modes of persuasion (Bogost, 2007), and simply the expression of complex ideas and emotions"
- p.4 : "higher education institutions in particular are interested in diversifying income, but I will argue, they should leverage games todo what they do best: amplify the production of social and cultural capital for participants, rather than make money"
- 

# The Gamer's Brain - Celia Hodent

# [Rules of Play - Katie Salen Tekinbaş and Eric Zimmerman](https://gamifique.files.wordpress.com/2011/11/1-rules-of-play-game-design-fundamentals.pdf)

