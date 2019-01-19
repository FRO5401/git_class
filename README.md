# Git Class for FROGRAMMERS

Welcome to team 5401's 'git_class' Repo! This Repo exists solely to teach good Git, GitHub, and Git workflow fundamentals. *It is currently not self-guided!* Below are some useful command line instructions:

## Basic Terminology

* Repository (repo) - a directory that manages saved versions of code for collaboration and display
* Remote - the saved files for the code which are stored on GitHub
* Local - your physical computer that you are currently working on
* Branch - a self-contained version of the code. If this were a game like Skyrim, then the save file for Krognar the Obliterator would be the branch of the Skyrim game.
* Commit - saved code states. If this were Skyrim again, then the commit would be Krognar, lvl 2, outside of Whiterun.
* Push - Send code from your local computer to the remote repository
* Pull - downloading code from the remote repository to your local system
* Checkout - switch

## Basic Command Line (These Commands work for UNIX Command Line and Windows Command Line)
* `pwd` print working directory. Shows which folder you're in.
* `cd [PATH]` change directory. Change working directory to the designated **PATH**
    * `cd ..` will go UP one directory in the tree
* `ls` list. List files within your current directory.
* `cat [FILE NAME]` concatenate. A fancy way to say 'read'. This will read the text of the **FILE** you designate.

## Interacting with the Remote Repository
* `git fetch` pulls all available branches from the remote repo and saves them on your computer
   * `git fetch --prune` Will both bring down all available branchs will removing local copies of deleted branches.
* `git pull origin [BRANCH NAME]` pulls a copy of the designated **BRANCH NAME** and attempts to merge it with the branch you are currently working in. 
    * `git pull origin HEAD` will merge the remote version of your *current* branch with the local version you're working in
* `git clone [REPO ADDRESS]` downloads a repository to your machine. Best done when updating your STAGING and MASTER branches.
* `git rebase [PREFERABLY A TRUNK]` Rebase will effectively rewrite the commit history of your current branch, making it act as if your local commits were added to whatever commit history exists in the remote 'trunk' (Master/Develop/Production/Staging, etc) commit history. Because this resets your current branch's history, **you must force push when updating the remote!!!!**

`git rebase` is a better alternative to `git merge`, since it turns your commit history into a linear progression. You can clearly trace back each change to the code base and easily revert unwanted changes. 

## Working with Git to make Local Changes
* `git checkout [DESIRED BRANCH]` switches from your branch to the **DESIRED BRANCH**
    * `git checkout -b [DESIRED NAME]` creates a new branch with the **DESIRED NAME** you input
* `git status` lists changes you've made locally to the branch since your last commit
* `git add .` stages *all* files you've changed to be saved with the next commit
    * `git add [PATH TO FILE]` stages a copy of a particular file, e.g. `git add ./README.md`
* `git commit -m "[YOUR MESSAGE]"` saves the staged changes to your branch. The Descriptive message you add will also be stored. Note that using single & double quotes may mess up your commit if you aren't careful. If you use contractions (can't, don't, won't), you're better off using double quotes like this:
```unix
git commit -m "I've made changes to some files you're not gonna believe!"
```
* `git push origin HEAD` pushes the changes you've made locally to the remotely save version of your branch
* `git pull origin [BRANCH]` will pull the remote **BRANCH** you request and attempt to merge it with the local version of the branch you're working in

## Whoops
* `git reset` will revert your files back to their last saved state. *THIS WILL NOT DELETE ANY ADDITIONS YOU'VE MADE!* Useful if you've deleted something you shouldn't've
* `git reset --hard` will revert your branch to its exact last state. New files will be removed, deleted ones will be restored, and good/bad changes will completely disappear. **GIT EQUIVALENT OF A NUKE FROM ORBIT**
* `git listhistory` shows, from most recent to oldest, a list of your commits. It'll look something like this
```
commit cc32728835d3d062f51d05b2010573e18b84e20b (HEAD -> gomez_makes_it_better)
Author: Devin Bombay <d.bombay@live.com>
Date:   Wed May 9 18:10:29 2018 -0400

    makes hello_world better.

M       hello_world.rb

commit 7de3ab656ee21ae12dab025e023905afc98a1ca5 (STAGING)
Merge: 690d031 0cd461a
Author: Devin Bombay <d.bombay@live.com>
Date:   Wed May 9 18:08:01 2018 -0400

    Merge https://github.com/FRO5401/git_class into STAGING

    'blah'

commit 690d031bdd8a239e051b03328608af9563188873 (origin/STAGING)
Author: Devin Bombay <d.bombay@live.com>
Date:   Wed May 9 18:04:28 2018 -0400

    merge conflict example

A       hello_world.rb
```
The series of letters and numbers after 'commit' can be used to reset DIRECTLY to that state, for example:
`git reset --hard 7de3ab656ee21ae12dab025e023905afc98a1ca5`

Useful if a freshman does a LOT of bad code and we need to start over...


Graduates
==========
* Devin
* Kevin
* David F.
