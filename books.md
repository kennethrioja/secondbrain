# Books

## Table of Contents
<!-- vim-markdown-toc GFM -->

* [Deep Work - Cal Newport](#deep-work---cal-newport)
* [Game Programming Patters - Robert Nystrom](#game-programming-patters---robert-nystrom)
* [Learning Vim Script The Hard Way - Steve Losh](#learning-vim-script-the-hard-way---steve-losh)
* [Making Games for Impact - Kirt Squire](#making-games-for-impact---kirt-squire)
* [The Gamer's Brain - Celia Hodent](#the-gamers-brain---celia-hodent)
* [Trillion Dollar Coach – Eric Schmidt, Jonathan Rosenber and Alan Eagle](#trillion-dollar-coach--eric-schmidt-jonathan-rosenber-and-alan-eagle)
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

# Trillion Dollar Coach – Eric Schmidt, Jonathan Rosenber and Alan Eagle

- XV : Project Aristotle @Google, key factors to excellent teams :
	1. Psychological safety;
	2. Clear goals
	3. Meaning
	4. Dependability (reliable and confident that the team's mission would make a difference)
	5. Impact
- p.22 : Engagement and productivity when part of a supportive community at work vs. job burnout
- p.39 : Great people flourish in an env that liberates and amplifies their energy to do well, capable of doing great things. You should create this environment through support, respect and trust.
- p.43 : Start with Trip Reports at begining of staff meeting + thank another team
- p.46 : 5 Word on a Whiteboard : after familiy talk, what are PEOPLE's top 5 items (what priorities of time and effort) ? (...) The most important thing a manager does is to help people be more effective and to grow & dvp (...) not so small talks -> it means performance : "What are you working on? How could he help?" & peer relationship -> teams (e.., clear direction? "Help them course correct, make them better"
- p.53 : Consensur leads to "gap think" and worse decisions. Instead, make everyone to provide their authentic and hidden opinions then if functional -> give it to the expert, if broader it's team leader's duty to handle it
	- 1-1 talk to prepare/give members the chance to come into the room prepared to talk about their point of view -> understand & ready to present it
- p.60 : Lead based on First Principles : define the "first principles" for the situation, the immutable truths that are the fondation for the company or product, and help guide the decision from those principles.
- p.89 : Only Coach the Coachable : the traits that make a person coachable, include honesty and humility, the willingness to persevere and work hard, and a constant openess to learning
- p.92 : When someone annoys or frustrates me, take a step back and find smth she does good. Then give constructive feedback only when she's feeling safe. Then "btw..." in 1-1 and always do this in a supportive way.
- p.105 : Full Identity Front and Center : People are most effective when they can be completely themselves and bring their full identity to work.
- p.113 : Work the team first : can they get it done ? Ensure the right team is on it -> then the problem.
- p.116 : Pick the right players "Smarts and Hearts" : Smart (able to make "far analogies"), Work Hard, Learn Fast, High Integrity, Grit, Empathy and a Team-First Attitude + how did you achieve that achievement ? We > I, Questions > Answers
- p.124 : Pair People : Peer relationships are critical and often overlooked, so seek opportunities to pair people up on projects or decisions
- p.125 : Peers are one of the most important evaluators, evaluate on those characteristics :
	1. Individual performance : at the job
	2. Relationship : with peers, groups
	3. Management and leadership
	4. Innovation
	5. Behavior in meetings
	6. Collaboration
	7. Product Vision (for product leaders)
	- Core Attributes : For the past 12 months, to what extent do you agree/ disagree that each person:
		- Displayed extraordinary in-role performance.
		- Exemplified world-class leadership.
		- Achieved outcomes that were in the best interest of both Google as a whole and his/her organization.
		- Expanded the boundaries of what is possible for Google through innovation and/or application of best practices.
		- Collaborated effectively with peers (for example, worked well together, resolved barriers/issues with others) and championed the same in his/her team.
		- Contributed effectively during senior team meetings (for example, was prepared, participated actively, listened well, was open and respectful to others, disagreed constructively).
	- Product Leader Attributes : For the past 12 months, to what extent do you agree/ disagree that each person demonstrated exemplary leader- ship in the following areas:
		- Product Vision
		- Product Quality
		- Product Execution
	- Open-Text Questions :
		- What differentiates each SVP and makes him/her effective today?
		- What advice would you give each SVP to be more effective and/or have greater impact?
- p.165 : The Lovely Reset : to care about people you have to care about people: ask about their lives outside of work, understand their families, and when things get rough, show up
- p.182 : The Elevator Chat : "How is it going? What are you working on?"

# [Rules of Play - Katie Salen Tekinbaş and Eric Zimmerman](https://gamifique.files.wordpress.com/2011/11/1-rules-of-play-game-design-fundamentals.pdf)

