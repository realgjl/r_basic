# Create R environment in miniconda
## Download the [Miniconda installer](https://repo.continuum.io/miniconda/)
At a command prompt, enter (Mac):
```terminal
curl -o ./Miniconda3-latest-MacOSX-x86_64.sh -k https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
```

## Run the installer
Mac:
```terminal
bash Miniconda3-latest-MacOSX-x86_64.sh
```

### Setting the install directory
Follow the prompts on the installer screens.

If you are unsure about any setting, accept the defaults. You can change them later.

To make the changes take effect, close and then re-open your terminal window.

To test your installation, in your terminal window or Anaconda Prompt, run the command ```conda list```.

For a successful installation, a list of installed packages appears.

## For Mac users
If the terminal is zsh, follow [this ariticle](https://medium.com/@sumitmenon/how-to-get-anaconda-to-work-with-oh-my-zsh-on-mac-os-x-7c1c7247d896).
If it's bash-based terminal, continue to the next step.

## Configuring Conda
Before first use, the conda package management system needs some initial configuration.

Make sure all the components are updated to their latest versions by entering (in "base" environment):
```terminal
conda update conda
```
```terminal
conda update --all
```
at the command prompt. If there are any updates, you will be prompted to agree their installation.


## Create R environment named "r_env" (you can change the environment name yourself)

### Install packages (r-essentials) with the name "r_env"
```terminal
conda create -n r_env r-essentials
```

### Install [jupyterlab](https://anaconda.org/conda-forge/jupyterlab)
```terminal
conda install -c conda-forge jupyterlab
```

### Again, make sure all the components are updated, in your r environment, to their latest versions, by entering:
```terminal
conda update conda
```
```terminal
conda update --all
```

## Exit the terminal app, then 👇

Activate r environment
```
conda activate r_env
```

### Open in Jupyter Lab
```terminal
Jupyter Lab
```
A big "R" icon should be appeared in the main page (http://localhost:8888/lab). Click it, you can edit & run your R script now!

### Run in a code editor, like [CodeRunner for macOS](https://coderunnerapp.com) (*not a paid AD)
1. Open "Preference" tab (command + ","), create a new language named "R" (or not :); 
2. In the section "Run Command", write your binary folder of the r environment like this:
```terminal
export PATH=/Users/realgjl/miniconda3/envs/r_env/bin:"${PATH}"
Rscript $filename
```
3. Other sections: extentions (R); Syntax mode (R); console type (terminal); debugger (pdb); indentation (default)


## P.S.
1. I use the base environment for Python 3, see this [section](https://github.com/realgjl/summer19/blob/master/README.md#installing-python-3-applications-and-libraries-with-conda) from "summer19" repository;
2. Each time I want to actiavte r environment in Jupyter Lab, I need to activate r environment firstly by:
```terminal
conda activate r_env
```
