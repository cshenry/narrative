# Introduction

This is the new IPython based Narrative Interface repo.
The previous version has been branched into the pre-sprint branch for archival purposes.
All relevant code has been migrated under the src/ directory. A virtualenv based installer
and standard KBase makefile targets are in the works.

# Running

The ipython narrative is a "profile" of the ipython notebook. The setup and instructions are run using the Python [virtualenv](https://pypi.python.org/pypi/virtualenv) module. If you haven't ever used this module, you should take some time to go familiarize yourself with it now.

## Current instructions

For the impatient, the following commands should work to start the KBase notebook.

    ./install.sh
    source narrative-venv/bin/activate
    profile_name=narrative run_notebook.sh notebook

That will run the KBase narrative version of the notebook (via the profile_name variable). If you do not set profile_name, then a base IPython Notebook will be started up with no KBase specific code - all KBase code is contained in the narrative profile so that we do not need to fork/branch the base IPython.

Now we will describe these commands step-by-step, and show how you can integrate with an existing set of Python virtual environments.

**Step 1**

    ./install.sh

This script creates a new Python virtual environment (see virtualenv). It takes command-line options controlling the destination of that virtual environment and the name of the environment itself. For example, to put the virtual environment under `~/.virtualenvs` (a common place to keep them) and to call it `kbase-narr`, you would instead run this variation on the `install.sh` command:

    ./install.sh -p ~/.virtualenvs -v kbase-narr 

**Step 2**

    source narrative-venv/bin/activate

This line activates the virtual environment. If you use the [virtualenvwrapper](http://virtualenvwrapper.readthedocs.org/en/latest/) module, and have installed the notebook under your usual virtual environment location, you can also simply use `workon <name>`, where `<name>` is whatever you chose to call the environment.

**Step 3**

    profile_name=narrative run_notebook.sh notebook

Finally, `run_notebook.sh` sets up some environment variables and runs ipython in "notebook" mode with the profile specified in profile_name ("narrative"). The notebooks themselves (i.e. files ending in `.ipynb`) are stored in `~/.narrative`. 

Last updated: Steve Chan (sychan) 9/2/2013
Last updated: Dan Gunter (dang) 8/19/2013


