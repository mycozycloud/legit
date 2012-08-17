.. -*-restructuredtext-*-

CozyGit: Git for Humans for Cozy Cloud
======================================

CozyGit is a package of git command to help with git's workflow for cozy


The Interface
-------------

``update [<branch>]`` 
    Pull the changes of the branch from the server. By default it executes on current branch ::
    
    $ git checkout development
    $ git pull --no-ff
    $ git checkout <branch>

``mergemaster``
    Merge current branch in master ::
    
    $ git checkout master
    $ git merge --no-ff <current branch>
    $ git checkout <current branch>

``devmerge``
    Update dev and merge it in current branch //STILL IN DEVELOPMENT// ::

    $ git checkout development
    $ git pull --no-ff
    $ git checkout feature/1stFeature
    $ git merge -–no-ff development

``mergeclose``
    Merge current branch in dev and close it ::

    $ git checkout development
    $ git merge -–no-ff <current branch>
    $ git branch –d <current branch>

``newbranch <branch>``
    Create a new branch, push it to the server and link both branches ::

    $ git checkout -b <branch>
    $ git push origin <branch>
    $ git branch --set-upstream <branch> origin/<branch>

Legit's command
---------------

We can still use legit's command : 

``branches``
    Get a nice pretty list of available branches.

``sync [<branch>]``
    Syncronizes the given branch. Defaults to current branch.
    Stash, Fetch, Auto-Merge/Rebase, Push, and Unstash.
    You can only sync published branches.

``switch <branch>``
    Switches to specified branch.
    Defaults to current branch.
    Automatically stashes and unstashes any changes.

``sprout [<branch>] <new-branch>``
    Creates a new branch off of the specified branch.
    Swiches to it immediately.

``harvest [<branch>] <into-branch>``
    Auto-Merge/Rebase of specified branch changes into the second branch.

``graft <branch> <into-branch>``
    Auto-Merge/Rebase of specified branch into the second branch.
    Immediately removes specified branch. You can only graft unpublished branches.

``publish <branch>``
    Publishes specified branch to the remote.

``unpublish <branch>``
    Removes specified branch from the remote.

``install``
    Installs legit git aliases.


new aliases : 

``update [<branch>]`` 
    Pull the changes of the branch from the server. By default it executes on current branch

``mergemaste``
    Merge current branch in master

``devmerge``
    Update dev and merge it in current branch //STILL IN DEVELOPMENT//

``mergeclose``
    Merge current branch in dev and close it

``newbranch``
    Create a new branch, push it to the server and link both branches


The Installation
----------------

Installing CozyGit is easy.

First get the repository ::

    $ git clone https://github.com/locel/legit.git

Then create a link to the executable ::

    $ [sudo] ln -s <absolute path to the repo>/legit/legit_r /usr/local/bin/cozygit

Then install the aliases ::

    $ cozygit install

Then enjoy :D

