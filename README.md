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

### Install [jupyterlab](https://anaconda.org/anaconda/jupyterlab)
```terminal
conda install -c anaconda jupyterlab
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

## For existing conda users: create a new and isolated R environment
Open terminal and run:
```terminal
conda create -n r_env r-essentials
```
p.s., This command will install the package [r-essentials](https://docs.anaconda.com/anaconda/user-guide/tasks/using-r-language/#:~:text=The%20R%20Essentials%20bundle%20contains,interpreter%20installed%20into%20new%20environments.) when creating new environment.
The ```new and isolated R environment``` is named ```r_env``` here.

### Open Jupyter Notebook
Open terminal & activate your R environment:
```terminal
conda activate r_env
```
Open Jupyter Notebook:
```terminal
jupyter notebook
```
Exit the current Jupyter environment: press ```control``` ```c``` at terminal

### Install new packages for R
Open terminal & activate your R environment:
```terminal
conda activate r_env
```
Google: "conda + install + 'package name'":
![](https://i.loli.net/2020/11/11/CmctZKLaVk13z6i.png)
You can search packages in Anaconda Cloud as well:
![](https://i.loli.net/2020/11/11/2CyjwKpDrhTbRLZ.png)

For popular packages, I suggest installing packages from these two package owners: **r** and **conda-forge**:
![](https://i.loli.net/2020/11/11/oIExn5U8zpFLdkV.png)

Select package, copy and paste the code and run:
![](https://i.loli.net/2020/11/11/5QPBfTN1OXdmrAu.jpg)



## P.S.
1. I use the base environment for Python 3, see this [section](https://github.com/realgjl/summer19/blob/master/README.md#installing-python-3-applications-and-libraries-with-conda) from "summer19" repository;
2. Each time I want to actiavte r environment in Jupyter Lab, I need to activate r environment firstly by:
```terminal
conda activate r_env
```
