# Programming

## Table of Contents

<!-- vim-markdown-toc GFM -->

* [Mastering the Vim Language](#mastering-the-vim-language)
* [How to learn (...) without following tutorials ?](#how-to-learn--without-following-tutorials-)
* [Github working in group setup](#github-working-in-group-setup)
* [Unity](#unity)
	* [20 Unity Tips in 10 min](#20-unity-tips-in-10-min)
	* [10 Unity Tips You (Probably) Didn't Know About](#10-unity-tips-you-probably-didnt-know-about)
	* [Scriptable Objects](#scriptable-objects)
	* [ML-agents](#ml-agents)

<!-- vim-markdown-toc -->

# Mastering the Vim Language

25 sept. 2022

Notes taken from : [Mastering the Vim Language](https://www.youtube.com/watch?v=wlR5gYd6um0?link_credit=KennethRioja), [slides](https://ctoomey.com/mastering-the-vim-language-slides.pdf?link_credit=KennethRioja)

- [Typing is not the bottleneck](http://anarchycreek.com/2009/05/26/how-tdd-and-pairing-increase-production/?link_credit=KennethRioja) : "the hard part of programming is thinking" - increase productivity in your team 1) writing a microtest that fails before you change any code, 2) adopt a "no-pair no-keep" agreement, 3) establish a shared understanding of code quality. What will slow you down is every flawed decision.
- power of `.`, `c`, `i[wt"p]`, `f`, `t` (cf. https://benmccormick.org/2014/07/02/learning-vim-in-2014-vim-as-language , https://blog.carbonfive.com/vim-text-objects-the-definitive-guide/ , https://medium.com/@mkozlows/why-atom-cant-replace-vim-433852f4b4d1 , https://stackoverflow.com/questions/1218390/what-is-your-most-productive-shortcut-with-vim/1220118#1220118 )
- [vim textobj user](https://github.com/kana/vim-textobj-user/wiki)

Why should you use a basic text editor?

08 sept. 2022

I will mostly focus on vim since I have been using this since the beginning

**Why should you use [vim](https://www.vim.org/?link_credit=KennethRioja) ?**

1. Keep it classy
2. Way more efficient (and less memory consumming !) than those fancy apps (*e.g.*, VSC, BrainJet, Atom,...)
3. Impress your peers

**How to begin your programming journey?**

1. Learn the basics
   - Open a terminal and execute the command [vimtutor](https://vimschool.netlify.app/introduction/vimtutor/?link_credit=KennethRioja)
2. Make it appealing to you
   - Configure your [.vimrc file](https://www.freecodecamp.org/news/vimrc-configuration-guide-customize-your-vim-editor/)
3. Keep track of your learning
   - Take notes using [VimWiki](https://github.com/vimwiki/vimwiki) and allow yourself to build a [secondbrain](https://www.buildingasecondbrain.com) !

**Going further**

- [How to Do 90% of What Plugings Do (With Just Vim)](https://www.youtube.com/watch?v=XA2WjJbmmoM?link_credit=KennethRioja)

# How to learn (...) without following tutorials ?

https://www.youtube.com/watch?v=vFjXKOXdgGo

1. Learn the absolute **basics** and nothing more
2. **Familiarize** with the basics through repetition and simple projects
3. Over time, **experiment** and build a repertoire/knowledge base of tools

# Github working in group setup

- `git pull`
- `git checkout -b <branchname>` (creation)
- `git push -u origin <branchname>` (creation)
- `git branch -d <branchname>` (delete)
- `git push origin -d <branchname>` (delete)
- `git fetch -p origin`
- `git branch -rd origin/*`
- `git pull origin main`

# Unity

## [20 Unity Tips in 10 min](https://www.youtube.com/watch?v=4NNAYvhCWjQ)
- Inspector Debug View > UpRight corner Normal to Debug, it allows to see private fields, do not use debug.log!, press option key to see real var names
- Hierarchy Lock and Visibility Button
- Anonymous Lambda Functions : .onClick.AddListener(() => {});
- Destroy(this) # destroys script, useful when unit dies but keep animation
- Debug.Drawline(currentpos,nextpos)
- Shift+Space : fullscreen
- Cmd+D : Duplicate
- F : Focus on object
- Cmd+Shift+F : Match object with scene camera

## [10 Unity Tips You (Probably) Didn't Know About](https://www.youtube.com/watch?v=fmbYlYU7z9Y)
- private IEnumerator Start() -> turns start into co-routine that automatically starts at runtime (e.g., timer)
- To assign multiple objects, instead of locking, open Properties window and drag-drop
- /// to write a summary of your function
- Change "if (var != null)" by "var?"
- Preferences > Scene View > Create Objects at Origin

## [Scriptable Objects](https://www.youtube.com/watch?v=aPXvoWVabPY)
- Data containers
- Act as a template
- Monobehavior to `ScriptableObject`
- Add before public class `[CreateAssetMenu(fileName = "", menuName = "")]`

## [ML-agents](https://www.youtube.com/watch?v=zPFU30tbyKs)
- `python -m venv venv`
- `source venv/bin/activate`
- `python -m pip install --upgrade pip`
- `pip install torch`
- `pip install mlagents`
- `mlagents-learn --help` 
- It did not work : I went with https://unity-technologies.github.io/ml-agents/Installation/
- `conda create -n mlagents python=3.10.12 && conda activate mlagents`
- `conda info --envs`
- `cd /path/to/ml-agents`
- `python -m pip install ./ml-agents-envs`
- `python -m pip install ./ml-agents`
