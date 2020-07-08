# Create R environment in miniconda
## Download the [Miniconda installer](https://repo.continuum.io/miniconda/)
At a command prompt, enter (Mac):
```terminal
curl -o ./Miniconda3-latest-MacOSX-x86_64.sh -k https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
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

#### To check if the Python has been installed successfully, in terminal:
```terminal
python -V
```
It's done if the python version is 3.x nor 2.x.

### For Mac users (macOS 10.15 Catalina, macOS 11.0 Big Sur, and later)
The default shell of terminal is now "zsh" instead of "bash". 

According to the offcial doc from [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/macos.html) (search "zsh" in the webpage), we need to find the path/direction of miniconda3's folder, for instance, in my case:
```terminal
/Users/realgjl/miniconda3
```
Then in the Terminal.app:
```terminal
source /Users/realgjl/miniconda3/bin/activate
```
```terminal
conda init zsh
```
Check the python version again and/or check if "conda" command works.

p.s., to show the hidden files in Mac, press: "command" + "shift" + ".".

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

### If you found you need to download Java packages
Check this [post](https://community.rstudio.com/t/java-problem-on-mac-mojave-solved/34223).

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

### Run in a code editor, like [CodeRunner for macOS](https://coderunnerapp.com)
1. Open "Preference" tab (command + ","), create a new language named "R" (or not :); 
2. In the section "Run Command", write your binary folder of the r environment like this:
```terminal
export PATH=/Users/realgjl/miniconda3/envs/r_env/bin:"${PATH}"
Rscript $filename
```
3. Other sections: extentions (R); Syntax mode (R); console type (terminal); debugger (pdb); indentation (default)

### Add to system's path
Go to the file "/etc/paths", add the path ("/Users/realgjl/miniconda3/envs/r_env/bin") in it. 
**Make sure this new miniconda directory is the first one, meaning that it will have precedence.**


## P.S.
1. I use the base environment for Python 3, see this [section](https://github.com/realgjl/summer19/blob/master/README.md#installing-python-3-applications-and-libraries-with-conda) from "summer19" repository;
2. Each time I want to actiavte r environment in Jupyter Lab, I need to activate r environment firstly by:
```terminal
conda activate r_env
```
