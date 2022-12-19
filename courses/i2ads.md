# Introduction to Applied Data Science (I2ADS)

## Equipe enseignante : Michael Dayan

## Table of contents
<!-- vim-markdown-toc GFM -->

* [20.09.2022 - Linux 1](#20092022---linux-1)
* [26.09.2022 - Linux 2](#26092022---linux-2)
* [03.10.2022 - Linux 3](#03102022---linux-3)
* [10.10.2022 - Linux 3 & Git 1](#10102022---linux-3--git-1)
* [24.10.2022 - Git 3](#24102022---git-3)
* [31.10.2022 - Git 4](#31102022---git-4)
* [07.11.2022 - Python 1](#07112022---python-1)
* [14.11.2022 - Python 2](#14112022---python-2)
* [21.11.2022 - Python 3](#21112022---python-3)
* [28.11.2022 - Python 4](#28112022---python-4)
* [05.12.2022 - Machine Learning 1](#05122022---machine-learning-1)
* [12.12.2022 - ML2](#12122022---ml2)
* [19.12.2022 - ML3](#19122022---ml3)

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

# 10.10.2022 - Linux 3 & Git 1

[exercises](https://www.dropbox.com/sh/oavy913p611zc97/AABzZC1jUTlfq-vwi0rTbMRza?dl=0)
- `$1` takes the first argument after the script
- DRY = Don't Repeat Yourself
- script : `getops ":cn:" ARG; do` // c option, but n accepts args so `n:`
- `export PATH=${PATH}:~/my_dir` // now I can execute shellscript located in my_dir
- string manip : `#*.` shortest from start, `##*.` longest from start, `%.*` shortest from end, `%%.*` longest from end

- `git show`
- `git diff`
- `git difftool`
- `gitk`

# 24.10.2022 - Git 3

[exercises](https://www.dropbox.com/s/agmlri3k5voe7sf/git_part3_ex.pdf?dl=0)
- `git add remote ALIAS GITADDRESS` // add a remote address
- `git remote -v` // list all remotes
- `git push -u ALIAS main`// -u to track
- `git branch -vv` // display all branches
- `git cherry-pick COMMITID` // take only COMMITNO
- `git cherry-pick COMMITT1~..COMMITTN` // ~ means one before
- `git reset --hard COMMITID` // do to before pushing, take back in time
- `git revert COMMITID` // if pushed, commit to revert changes 
- vMAJOR.MINOR.PATCH // convention, semantic versioning : MAJOR = possible breaking changes, MINOR = backward-compatible, PATCH = backward compatible bug fixes
- `git tag -a ANNOTATION COMMITID -m MESSAGE`
- `git push --follow-tags`

To merge a branch into main and see the history clearly :
- `git rebase main` as it began like main
- `git merge BRANCH --no-ff` 

# 31.10.2022 - Git 4

[exercises](https://www.dropbox.com/s/duk9r6b04aheq5a/git_part4_ex.pdf?dl=0)
- after a fork :
	- `git remote add upstream GITADDRESSOFUPSTREAM`; //upstream is the git you have forked from
	- then `git pull upstream main`;
	- `git checkout -b fix`;
	- then do your changes, add, commit -m "#ISSUE_ID", push origin fix ; 
	- and see your issue linked on Github ;
	- on your forked repo : make a pull request using your fix branch

# 07.11.2022 - Python 1

- .ipynb :
	- `y` to go Code
	- `m` to go Markdown
	- `dd` to delete cell
- `print(...,..., sep = ' ')` you can separate while printing
- `print(f"it's my {25+1}th bday")` displays 26, it is a formatted string, note the f
- `print?` help
- `dir(obj)` see the list of all methods applying to an object
- `dictionary = { 'one': 1, 'two': 2 }` `.keys()` `.values()` Note : a dic is not ordered
- `tuple = (42, 'method1', 3.14)` these are fixed, ex. longitude/latitude
	- `sub-tuple1, sub-tuple2 = tuple` unpack tuple
- `np.unique(vector)` shows unique value of vector
```python
my_dict = {
    'one': 1,
}
methods = dir(my_dict)
proper_methods = []
for meth in methods:
    if not meth.startswith('_'):
        proper_methods.append(meth)
print(proper_methods)
```

# 14.11.2022 - Python 2

[exercises]()
- `def` to define a fonction
	- `def my_function(arg1:type, arg2:type) -> List[str]` // what comes after '->' is what he function returns
- `None` special Python keyword
- Function docstring
```python
def my_function(p1: int, p2: str) -> str :
'''	Description of the function

	Parameters
	----------
	p1
		whatyouwant
	p2
		whatyouneed
	
	Returns
	-------
	whatitreturns
		description
'''	
```
- `import sys` > `sys.path.append("pathwhereyouaddedanewfunction")` > ìmport `filewithout.py` > now you can use 
- Two ways to import :
	- `import package`
	- `from package import my_function`
- `import importlib` > `importlib.relad(my_module)`
- In Python code : `if __name__ == "__main__"`
	- When called from cmd line : __name__ == "__main__"
	- When imported : __name__ == "filename"
- `assert ifelsestatement, "INTERNAL BUG: ..."` statement to say internal error
- `raise ValueError("EXTERNAL ERROR: ...")` statement to say external error
- `pytest` package to test all the 'test' files
	- you can also test documentation by adding flag `--doctest-modules`

# 21.11.2022 - Python 3
- Numerical python = numpy
- `import numpy as np` // to get the abbreviation 'np'
- To create an environment and activate it (it will change your path) :
* `conda create --name datascience38 python=3.8`
* `conda activate datascience38`
- To install packages in an environment (once activated):
* `conda install numpy`
- You can use conda to switch between environments:
* `conda activate proj27`
* `conda deactivate`
* `conda activate proj38`
- To list packages in current environment
* `conda list`
- To remove a package, e.g. `numpy`
* `conda remove numpy`
- To list environments:
* `conda info --envs`
- To remove an environment:
* `conda remove -n datascience38 --all`
- `import requests` > `raise requests.exceptions.RequestException("Function not sucessful")`
- `pytest your.py` // to test the environment

# 28.11.2022 - Python 4
- Activating a conda environment allows to work on a specific version of python
- `matplotlib`is a core Python plotting lib, works well with `numpy`
- `from matplotlib import pyplot as plt`
- `shift + tab` to see information/help about function on jupyter nb
- `plt.tight_layout()` to optimize the overall plot display
```python
with open(first_file, 'r') as file_handler:
    for file_line in file_handler:
        print(f"Line: {file_line}")
```
- list comprehension : `files = [f for f in files_all if not 'small' in f]`
- `np.where()==0` to checker where it is == 0
- `import pandas as pd`
- `pd.read_csv(path)` to open csv
- `df.describe()` to show mean std etc. for each num var
- `df["categoricalVariable"].value_counts()` like 'table()' in R
- `df.isna().sum()`to see na
- `df.iloc[5:10, 0:4]` to filter 0 to 3 column and 5 to 9 rows - if use labels, use `loc`
- `df.shape` to see rows and cols
- `df.isna().sum()` to see where NAs are
- `df.dropna()` to drop na
- `seaborn` for plotting with nicer attributes
- `df['colname'].value_counts()` to count the values of colname

# 05.12.2022 - Machine Learning 1
- Error (what if pos and neg?) > Squared Error (if 20 points > 10 points) > mean Squared Error (MSE)
- Model with too many parameters = over-fitting
- Fitting a model on data and looking at errors is not enough, if much parameters and low MSE, you divide your df, and keep unseen data to make prediction and compare with real observation to test if the new observation fit the model
- Total error is the sum of Error and Model Complexity
- `from sklearn.model_selection import train_test_split` allows to split training data to test model
- `lm.fit` # to train a model
- `lm.predict` 
- `fit.transform()` # to transform for any deg X model
- Values of R2 and MSE are always lower on test than on training
- Cross-validation, training set in 4 train and 1 test (5-fold cross-validation)

# 12.12.2022 - ML2
- Underfitting not enough flexible
- Overfitting : depends a lot on data, performance terrible, model too much tuned to training data, did not see global pattern
- x = feature
- y = label
- Testing data is worse because model fitted on training data : over or underfitting
- Supervised learning (labels provided by the user is the 'supervision') : reg when continuous and classification when categorical
- A logistic regression is a classification algorithm
- `df.loc[mask, "colName"]` loc allow to extract
```python
from sklearn.preprocessing import LabelEncoder
label_encoder = LabelEncoder()
y = label_encoder.fit_transform(y_label) # y_label is a categorical label
from sklearn.model_selection import train_test_split
Y_train, X_test, y_train, y_text = train_test_split(X, y, test_size=0.3, stratify=y)
from sklearn.linear_model import LogisticRegression
lr = LogisticRegression(penalty=None, class_weight="balanced")
from sklearn.metrics import accuracy_score, confusion_matrix, ConfusionMatrixDisplay
```

# 19.12.2022 - ML3
- COURSE TO CHECK
- Hyperparameters (Lambda), for each score, you have few HP because CV, how to know the best? -> do grid-search
	- Regularization
	- How to choose ? Nested cross-validation, cross-validation within cross-validation and chose most frequent hyperparameters
	- Grid-search, list of hyperparam to test
	- Nested vs grid-search ? GS is the list of the HP to test, for that we have to do nested-CV
- PCA : first dim is the one that has most variance, looking at the component explaining the maximum variance, once explained, the second dimension the other direction
	- Components are always orthogonal (perpendicular)
- K-Means : means initialization -> Cluster assignment -> means update (center of mass of all obs) and repeat -> convergence (until no more cluster membership)
	- It's just looking at features regarding labels; classes can be defined in any number of ways
- Estimator = model
- Supervised learning : when knowing the label (ex. regression when label continuous, classification when label cat)
	- Regression :
		- Ridge reg, with penalty L2
		- Lasso, with penalty term L1
		- Elastic with L1 and L2
	- Classification
- Unsupervised learning : when not knowing the label :
	- Dimensionality reduction
	- Clustering

TODO : 
- ex3 ifelse and while, case, getops
- see last 15 min of git
- Git Capstone :
	- do not begin with linux capstone, but you can begin with the git capstone
	- when ready to be graded, you need to tag
	- shellcheck before pushing
	- you can create a new issue and tag eyap and michael, describe issue and submit : to have support
- https://github.com/davidhalter/jedi-vim
- Git capstone
- Do not do python ML capstone
- Answer all the one you do not need to think, then come back to others
- Prediction on stroke dataset, python part of lecture
