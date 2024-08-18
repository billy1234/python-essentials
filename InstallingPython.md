# Installing python

On a windows machine the easiest way to install
python on a windows machine is with the inbuilt package
manager `winget`, this tutorial will use Python 3.11

To install with winget open powershell and type:

    winget install -e --id Python.Python.3.11

To verify, open a new powershell terminal and run:

    python --version

Your output should be: 

    Python 3.11.9 

Note the bugfix version may be higher depending on when it is run, this is good, you always want the most up to date bugfix version.
Aslong as the version is `3.11.{anything}` you are ready to go.

