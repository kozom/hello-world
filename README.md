How to use Github
=================


Initial Setting
===============

Setup your Account
------------------

1.  sign up Github
2.  open your personal setting
3.  open setting for Emails
4.  check "Keep my email address private"
5.  copy email-address `<username>@users.noreply.github.com`
6.  download Git client and run the following commands

        # register username and email-address from bash
        git config --global user.name <username>
        git config --global user.email <email-address>


Make your own repository (if you start your own project)
------------------------

1.  run the following commands

        # start versioning with Git
        cd <your-project's-directory>
        git init                      # create local repository
        git add .                     # add all files to index for versioning
        git commit -m "First commit"  # commit the files to current branch

2.  sign in Github
3.  create new repository
4.  click "Clone or Download" and copy URL "https://..."
5.  run the following commands

        # asociate local repository with remote repository
        git remote add origin <URL> # register remote server as name "origin"
        git fetch                   # fetch containts of remote repository
        git merge origin/master --allow-unrelated-histories
                                    # merge local branch into remote branch
        git push -u origin master   # push the merged branch to remote server


Clone exist repository (if you join exist project)
----------------------

1.  open a GitHub project which you want
2.  click "Clone or Download" and copy URL "https://..."
3.  run the following commands

        git clone <URL> # fetch repository to the current directory

If you don't have permission to push project's master repository,
you have to create your own repository for pull request.
See <https://help.github.com/articles/creating-a-pull-request-from-a-fork/>.


Edit Repository
===============

Make development branch
-----------------------

1.  run the following commands

        git fetch                  # fetch master branch to make it up to date
        git branch <branch-name>   # make new branch
        git checkout <branch-name> # work on the branch

How should you make branch depends on your project's policy.
See <https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging>.


Edit source files and commit them
---------------------------------

1.  edit source files
2.  run the following commands

        git add .  # add all modified files to commit list
        git status # check what is changed
        git commit # input description of the commit in text editor


Modify past commits (if necessary)
-------------------

1.  run the following commands

        git log --oneline --graph # show commit id
        git rebase -i <commit id> # choose a commit to rebase onto

2.  edit source files
3.  run the following commands

        git commit --amend    # commit the edit
        git rebase --continue # continue rebasing


Merge development branch
------------------------

1.  run the following commands

        git checkout master
        git merge <branch-name>     # merge development branch to master branch
        git branch -d <branch-name> # delete development branch


Push to remote repository
-------------------------

1.  run the following commands

        git fetch # fetch master branch to make it up to date
        git merge # merge your edits
        git push  # upload the repository


Pull request
------------

1.  sign in Github
2.  click "compare & pull request"
2.  click "compare & pull request"


Tips
====

The following commands are helpful to understand what happens in Git.

    git log --graph --oneline --decorate --all # show detailed commit log
    cat .git/config                            # show config of repository
    cat ~/.gitconfig                           # show global config

The Oliver Steele's image is helpful to understand workflow of Git.

![Oliver Steele's image](https://i.stack.imgur.com/XwVzT.png)


