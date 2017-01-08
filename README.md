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

2.  sign in to Github
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

You may not have permission to push project's master repository.
Then you have to create your own repository for pull request.
See <https://help.github.com/articles/creating-a-pull-request-from-a-fork/>.

1.  open a GitHub project which you want
2.  click "Fork"
3.  click "Clone or Download" and copy URL "https://..."
4.  run the following commands

        git clone <URL> # fetch repository to the current directory


Edit Repository
===============

Make development branch
-----------------------

1.  run the following commands

        git fetch                # fetch containts of remote repository
        git merge origin/master  # merge local branch into remote branch
        git branch development   # make new branch named "development"
        git checkout development # work on the branch

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


Push to remote repository
-------------------------

1.  run the following commands

        git push  # upload local repository

1.  if it fails, run the following commands

        git fetch               # fetch containts of remote repository
        git merge origin/master # merge local branch into remote branch

Create pull request
-------------------

1.  sign in to Github and open the project page
2.  click "New pull request"
3.  select the branch you pushed before
4.  click "Create pull request"


Merge pull request (if your own project)
------------------

1.  sign in to Github and open the project page
2.  click "Pull requests" tab
3.  click "Merge pull request"
4.  click "Confirm merge"


Delete development branch
-------------------------

1.  run the following commands

        git checkout master                 # select master as current branch
        git branch -d development           # delete local development branch
        git branch -d -r origin/development # delete remote development branch


Tips
====

The following commands are helpful to understand what happens in Git.

    git log --graph --oneline --decorate --all # show detailed commit log
    cat .git/config                            # show config of repository
    cat ~/.gitconfig                           # show global config

The Oliver Steele's image is helpful to understand workflow of Git.

![Oliver Steele's image](https://i.stack.imgur.com/XwVzT.png)


