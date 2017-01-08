How to use Github
=================

?


Initial Setting
===============

Setup your Account
------------------

1.  sign up Github
2.  open your personal setting page
3.  open setting for Emails
4.  check "Keep my email address private"
5.  copy email-address `<username>@users.noreply.github.com`
6.  download Git client and do the following on bash

        # register username and email-address from bash
        git config --global user.name <username>
        git config --global user.email <email-address>


Make your own repository
------------------------

?


Clone exist repository
----------------------

1.  open a GitHub project which you want
2.  click "Clone or Download" and copy URL "https://..."
3.  do the following on bash

        git clone <URL> # fetch repository to the current directory


Edit Repository
===============

Make development branch
-----------------------

1.  do the following on bash

        git fetch                  # fetch master branch to make it up to date
        git branch <branch-name>   # make new branch
        git checkout <branch-name> # work on the branch

See <https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging>.


Edit source files and commit them
---------------------------------

1.  edit source files
2.  do the following on bash

        git add .  # add all modified files to commit list
        git status # check what is changed
        git commit # input description of the commit in text editor


Modify past commits (if necessary)
-------------------

1.  do the following on bash

        git log --oneline --graph # show commit id
        git rebase -i <commit id> # choose commit you want to rebase from

2.  edit source files
3.  do the following on bash

        git commit --amend    # commit the edit
        git rebase --continue # continue rebasing


Merge development branch
------------------------

1.  do the following on bash

        git checkout master
        git merge <branch-name>     # merge development branch to master branch
        git branch -d <branch-name> # delete development branch


Push to remote repository (if Git style)
----------------------------------------

1.  do the following on bash

        git fetch # fetch master branch to make it up to date
        git merge # merge your edits
        git push  # upload the repository


Pull request (if GitHub style)
------------------------------

?
