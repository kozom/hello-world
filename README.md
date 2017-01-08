How to use Git/Github
=====================

Initial setting
---------------

1.  open your personal setting page on GitHub
2.  open setting for Emails
3.  check "Keep my email address private"
4.  copy email-address `<username>@users.noreply.github.com`
5.  register username and the email-address to your Git client

        # example to register username and email-address from commandline
        git config --global user.name <username>
        git config --global user.email <email-address>


Get all source files
--------------------

1.  open a GitHub project which you want
2.  click "Clone or Download" and copy URL "https://..."
3.  clone project

        git clone <URL>

You will get all source files of the project in the current directory.


Make development branch
-----------------------

1.  make new branch

        git branch <branch-name>
        git checkout <branch-name>

See <https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging>.


Modify and commit source files
------------------------------

1.  make some changes to source files
2.  commit source files

        git add .  # add all modified files to commit list
        git status # check what is changed
        git commit # input description of the commit in text editor

Modified source files will be added to repository.


Modify containts of commit
--------------------------

1.  choose commit which you want to modify, in text editor

        git rebase -i root

2.  make some changes to source files
3.  commit the changes

        git commit --amend
        git rebase --continue


Merge development branch
------------------------

1.  merge development branch to master

        git checkout master
        git merge <branch-name>

2.  delete development branch

        git branch -d <branch-name>


Push to remote repository (Git style)
--------------------------------------------

1.  push commit to remote repository

        git push


Pull request (GitHub style)
---------------------------

(under construction)
