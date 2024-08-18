Git is an open source version control system.

While not essential for this course it is encouraged to learn as the
materials are hosted in a public git repository.

Git can be incredibly useful to save the sate of your code, experiment
and if you decide you want to roll back to a working copy of the code
it can be done easily and quickly.

This tutorial will cover CLI git, 


## Installation

This tutorial assumes you are trying to install git on a windows environment,
Linux and WSL Linux are also viable options but will not be covered here.

To install git open up a Powershell session and run:

    PowerShellGet\Install-Module posh-git -Scope CurrentUser -Force


## Getting started

When using Git the first step is always one of 2 things,
create a **new** repository or "import" an existing one someone has made
for you.

To make a new repository (I recommend you do this for any code you write during
this course)


First navigate your Powershell to the folder you wish to make a git repository.
Lets say we wish to use the folder `C:\Users\me\PythonCourse` we can move our
Powershell to this folder with the change directory command:

    cd C:\Users\me\PythonCourse

To check you are in the correct folder the text before your cursor should say: `PS C:\Users\me\PythonCourse>`


To verify you can also run the `ls` command to list all files in this folder.
If you have any existing files in the folder they should be listed here.

Now you have navigated to the correct directory simply run:

    git init

After running this command you have turned the folder you are in into a
git repository, this means you can make changes and track versions.
More on this later.


However sometimes you don't want to create a brand new repository but rather want to
begin from someone else's code or copy your code from one computer to another via git

To do this you need to "clone" or download the code from a remote, a remote is just a server that
git uses to download and upload code from.

This project is hosted on GitHub so for this example lets download the repoitory that has these
markdown files in it.
To do this run:

    git clone https://github.com/billy1234/python-essentials.git

This will create a folder called python-essentials and store the code within that
If you want to store the code in a different folder you can set the destination folder with an
extra command line argument:

    git clone https://github.com/billy1234/python-essentials.git PythonCourse

Here this example will clone into a folder called `PythonCourse`

## Making changes

Now that you have set up a git repository there are 4 essential commands for using git:

- add
- commit
- push
- pull
- status

A brief explanation of these:

*add* This adds the selected files read for a commit.
The most common ways to use add are:

    git add .
    #or
    git add -A

    git add file.txt

Add . or -A will add all files ready to commit, if instead a file name is specified 
just that file will be added instead.

At this point nothing has been saved to git, these files are just ready to be *committed*


*commit* think of this command as creating a distinct version of your code,
it will only do this locally however and use only the files you "added" with the above command.

To make a commit you need to provide a commit message and use the "-m" flag:

    git commit -m "My first commit"

*push* Now that you have the commit created on your laptop to synchronize your changes with the remote server
(if you have on set up) you now need to "push" or upload your commit.

To do this run:

    git push

Now you have uploaded your code to the remote server and it is now backed up off your machine.
If it is the first time pushing a new *branch* not on the server, you may receive an error:

    fatal: The current branch new-branch has no upstream branch.
    To push the current branch and set the remote as upstream, use

    git push --set-upstream origin new-branch

To resolve this just use the command recommended in the error message, this will make the branch that
does not yet exist on the remote server then push your changes to it.


*pull* If someone else in the team makes a change to the code or you swap machines and need to
download the latest version you will need to "pull" or download the latest changes.
To do this we need the pull command:

    git pull

This should download the code assuming that your local copy has not added any commits not on the sever,
if not you will have to merge, this is out of scope for this tutorial, however as a solo developer using git
this is unlikely to happen as long as you always *pull* before making any changes to your code.


## Gitignore files

Sometimes we have files that we don't want Git to track such as binaries, python virtual environments or
3rd party library installs.

Git provides a mechanism to ignore either single files, entire folders or even all files that end with a certain
pattern using the `.gitignore` file, these can be placed in any folder 
however it is best practice to always place one in the root folder Git is tracking.

This project has an auto generated python [.gitignore](.gitignore), if you ever
create a new git repo for python copy past this one or google an example python `.gitignore`
and ensure it is set up from day one.

## Further reading

So far everything explained here has been on one *branch*
typically in a team with multiple contributors branches are used to
separate out code.

This is where git gets a bit harder and requires some further reading
to use git in a professional setting developers should know how to:

- create branches
- checkout branches
- merge branches
- create pull requests
- git diff

Thankfully Git is a very well documented tool and many free resources online
cover these topics in great detail.

