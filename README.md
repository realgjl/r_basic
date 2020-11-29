# Install miniconda & set base environment (Python)
### Download the [Miniconda installer](https://repo.continuum.io/miniconda/)
At a command prompt, enter (Mac):
```terminal
curl -o ./Miniconda3-latest-MacOSX-x86_64.sh -k https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
```
In Linux (Ubuntu, CentOS, ...):
```terminal
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

### Run the installer
Mac:
```terminal
bash Miniconda3-latest-MacOSX-x86_64.sh
```
Linux:
```terminal
bash Miniconda3-latest-Linux-x86_64.sh
```

### Install libraries
Follow the prompts on the installer screens. If you are unsure about any setting, accept the defaults. You can change them later. To make the changes take effect, close and then re-open your terminal window. To test your installation, in your terminal window or Anaconda Prompt, run the command ```conda list```. For a successful installation, a list of installed packages appears.

Check if the Python has been installed successfully (in version 3.x), in terminal: ```python -V```

Install necessary Python packages:
```terminal
conda install -c conda-forge scipy jupyterlab pandas matplotlib
```

### Update conda and libraries
```terminal
conda update conda
```
```terminal
conda update --all
```

# For existing conda users: create a new and isolated R environment
Open terminal and run:
```terminal
conda create -n r_env r-essentials
```
p.s., This command will install the package [r-essentials](https://docs.anaconda.com/anaconda/user-guide/tasks/using-r-language/#:~:text=The%20R%20Essentials%20bundle%20contains,interpreter%20installed%20into%20new%20environments.) when creating new environment.
The ```new and isolated R environment``` is named ```r_env``` here.

### activate your R environment:
```terminal
conda activate r_env
```

### Open Jupyter Notebook:
```terminal
jupyter notebook
```
Exit the current Jupyter environment: press ```control``` ```c``` at terminal

### Install new libraries for R
tidyverse corrplot MASS randomforest neuralnet
```terminal
conda install -c conda-forge r-tidyverse r-corrplot r-mass r-randomforest r-neuralnet
```

### Update all
```terminal
conda udpate --all
```

# P.S.
1. For Mac users (macOS 10.15 Catalina, macOS 11.0 Big Sur, and later), the default shell of terminal is now "zsh" instead of "bash". 
According to the offcial doc from [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/macos.html) (search "zsh" in the webpage), we need to find the path/direction of miniconda3's folder, for instance, in my case:
```terminal
/Users/realgjl/miniconda3
```
Then in the terminal:
```terminal
source /Users/realgjl/miniconda3/bin/activate
```
```terminal
conda init zsh
```
Check the python version again and/or check if "conda" command works.

2. To show the hidden files in Mac, press: "command" + "shift" + ".".

3. If you found you need to download Java packages, check this [post](https://community.rstudio.com/t/java-problem-on-mac-mojave-solved/34223).

4. If you would like to run R in a code editor ([CodeRunner for macOS](https://coderunnerapp.com)),
 - Open "Preference" tab (command + ","), create a new language named "R" (or not :); 
 - In the section "Run Command", write your binary folder of the r environment like this:
```terminal
export PATH=/Users/realgjl/miniconda3/envs/r_env/bin:"${PATH}"
Rscript $filename
```
 - Other sections: extentions (R); Syntax mode (R); console type (terminal); debugger (pdb); indentation (default)

5. Add the binary file to system's path: Go to the file "/etc/paths", add the path ("/Users/realgjl/miniconda3/envs/r_env/bin") in it. **Make sure this new miniconda directory is the first one, meaning that it will have precedence.**

