## Table of contents
<!-- vim-markdown-toc GFM -->

* [20.09.2022 - Linux 1](#20092022---linux-1)
* [26.09.2022 - Linux 2](#26092022---linux-2)

<!-- vim-markdown-toc -->

# 20.09.2022 - Linux 1

[exercises](https://www.dropbox.com/s/h29ar582qy0th2f/linux_part1_ex.pdf?dl=0)
- trad resarch between maths and stats and subject matter expertise
- Goals : 
    1) linux, shell, scripts, adminsys
    2) git, changes/history, branches/mergees
    3) python, basiscs, data struct, fun, OOP, conda/jupyter
    4) ML into, data representation, model fitting, regression/classification
    FINAL : implementing full project, with Terminal + Git + Python + Sci-kit learn
- Exam : 80% presence and "what does the command ... does?" MCQ.

- `ctrl` + `alt`(opt) + `t` // open terminal on linux
- `whoami` 
- `hostname`
- `tldr` // man with example
- `man -key _cmd_` // display keys containing the cmd
- `history` // see all past commands
- `tree -L _nb_` // display only <nb> subfolders
- ? // any char
- [Pp] // any char in list
- [0-9] // any char in range
- {.txt,.pdf} // any sequence
- `more`
- `less` // works like vim
- `head`
- `tail`
- `sort -n timesData.csv` | head -n 15 // sort

# 26.09.2022 - Linux 2

[exercises](https://www.dropbox.com/s/oif66jnezaerlio/linux_part2_ex.pdf)
- `mkdir -p `// to create parents
- `cp -R`// copy recursively DIR1 to DIR2
- `ls -ld` / // to see root
- `su` // to become sudo, exit to exit
- `chown user:group DIRPATH` // take ownership of dir, -R of all
- `chgrp GROUP FILE/DIR` // change grp ownership of dir
- IP + port = socket
- `ping _address_` // see if address is alive
- `nmap -p _portnumber_ _address_` // see status of portnumber of address
- `md5sum _file_` // hash
- `sha256`
- `ssh-keygen -lf _pubfile_`
- `ssh-copy-id _user@remotehost_` 
  
  # 03.10.2022 - Linux 3
  
  [exercises](https://www.dropbox.com/s/igh77gyrhx3gll8/linux_part3_ex.pdf?dl=0)
  - `shellcheck _script_` // help checking
  - use `${}` in shell script to call the variable
  - file name expansion = "globbing" = /home/ada/*/
  - when creating an array (e.g., `LIST=("a" "b" "c"`) : to get all elements as an @rray use `LIST[@]`, as a string `LIST[*]` (* = Star), counting number of elements as `${#LIST[@]}`
  - in script `-f`, `-d`, `-z` = X exists and is a file, dir, empty string
  - `read _var_` // reads what you typed

TODO : 
- ex3 ifelse and while
