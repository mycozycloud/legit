.. -*-restructuredtext-*-

Legit: Git for Humans
=====================

Inspired by GitHub for Mac.


The Concept
-----------

`GitHub for Mac <http://mac.github.com>`_ is not just a Git client.

This `comment <http://www.hackerne.ws/item?id=2684483>`_ on Hacker News
says it best:

    They haven't re-created the git CLI tool in a GUI, they've created something different. They've created a tool that makes Git more accessible. Little things like auto-stashing when you switch branches will confuse git veterans, but it will make Git much easier to grok for newcomers because of the assumptions it makes about your Git workflow.

Why not bring this innovation back to the command line?


The Interface
-------------

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

thoses are not usable as "git <alias>" yet. Use "<your legit alias> <alias>" ( see below in "The installation)

``update`` 
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

Installing Legit is easy with pip::

    $ pip install legit

You'll then have the wonderful ``legit`` command available. Run it within
a repository.

To install the git aliases, run the following command::

    $ legit install

To use the new aliases create and alias / link to the executable "legit_r"

Caveats
-------

- All remote operations are carried out by the remote identified in `$ git config legit.remote remotename`
- If a ``stash pop`` merge fails, Legit stops. I'd like to add checking for a merge failure, and undo the command with friendly error reporting.
- Pip install is cumbersome to people unfamiliar with Python. Package. (Py2App + PyInstaller)

Incoming updates
----------------

- possibility to use the aliases as "git <alias>"
- fix of devmerg
