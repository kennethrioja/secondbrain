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

- ctrl + alt(opt) + t // open terminal on linux
- whoami 
- hostname
- tldr // man with example
- man -key <cmd> // display keys containing the cmd
- history // see all past commands
- tree -L <nb> // display only <nb> subfolders
- ? // any char
- [Pp] // any char in list
- [0-9] // any char in range
- {.txt,.pdf} // any sequence
- more
- less // works like vim
- head
- tail
- sort -n timesData.csv | head -n 15 // sort

# 26.09.2022 - Linux 2

[exercises](https://www.dropbox.com/s/oif66jnezaerlio/linux_part2_ex.pdf)
- mkdir -p // to create parents
- cp -R // copy recursively DIR1 to DIR2
- ls -ld / // to see root
- su // to become sudo, exit to exit
- chown user:group DIRPATH // take ownership of dir, -R of all
- chgrp GROUP FILE/DIR // change grp ownership of dir
- IP + port = socket
- `ping` _address_ // see if address is alive
- `nmap -p` _portnumber_ _address_ // see status of portnumber of address
- `md5sum` _file_ // hash
- `sha256`
- `ssh-keygen -lf` _pubfile_
- `ssh-copy-id` _user@remotehost_ 
