# Local environment setup

This page explains Git, Conda, and Mamba and how to install them. After installing these softwares, the page will show how to use each one towards running a Jupyter notebook. Instructions have been inspired from [similar documentation in other domain](https://biapol.github.io/blog/mara_lampert/getting_started_with_miniforge_and_python/readme.html) 


## Installing Git

[Git](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F) is a version control system that is designed to track changes in files stored within repositories. [GitHub](https://docs.github.com/en/get-started/start-your-journey) offers a platform for storing and collaborating on various Git repositories. 

:::{caution}
Installing Git requires administrator access to your computer.
:::

### Mac & Linux

Terminals come pre-installed with Git so there are no steps required to install Git.

To launch terminal, go to Spotlight Search or Applications and find the Terminal app to open.

(primers-git_launch1_macOS)=
```{image} ../images/primers/git_launch1_macOS.png
:width: 100px
:align: center
```
<br>

### Windows

[Download](https://git-scm.com/downloads) and run the Windows installer `.exe` file.  

After double-clicking on the installer `.exe` file, you will first be prompted to enter your administrator password.
Once the setup window has opened, complete the following steps:

1) Read the license and click on "Next" to continue

(primers-git_setup1_windows)=
```{image} ../images/primers/git_setup1_windows.png
:width: 400px
:align: center
```
<br>

2) Install Git in the default location and continue

(primers-git_setup2_windows)=
```{image} ../images/primers/git_setup2_windows.png
:width: 400px
:align: center
```
<br>

3) Leave the default components selected and continue

(primers-git_setup3_windows)=
```{image} ../images/primers/git_setup3_windows.png
:width: 400px
:align: center
```
<br>

4) Select the default Start Menu folder and continue

(primers-git_setup4_windows)=
```{image} ../images/primers/git_setup4_windows.png
:width: 400px
:align: center
```
<br>

5) Change the default editor used by Git to nano which is a simpler alternative to vim

(primers-git_setup5_windows)=
```{image} ../images/primers/git_setup5_windows.png
:width: 400px
:align: center
```
<br>

6) Override the default branch name for new repositories to be "main"

(primers-git_setup6_windows)=
```{image} ../images/primers/git_setup6_windows.png
:width: 400px
:align: center
```
<br>

7) Allow Git from the command line and also 3rd-party software

(primers-git_setup7_windows)=
```{image} ../images/primers/git_setup7_windows.png
:width: 400px
:align: center
```
<br>

7) Use the OpenSSL library as the HTTPS transport backend

(primers-git_setup8_windows)=
```{image} ../images/primers/git_setup8_windows.png
:width: 400px
:align: center
```
<br>

8) Checkout Windows-style, commit Unix-style line endings

(primers-git_setup9_windows)=
```{image} ../images/primers/git_setup9_windows.png
:width: 400px
:align: center
```
<br>

9) Use MinTTY as the terminal emulator to use with Git Bash

(primers-git_setup10_windows)=
```{image} ../images/primers/git_setup10_windows.png
:width: 400px
:align: center
```
<br>

10) Select fast-forward or merge as the default behavior for git pull

(primers-git_setup11_windows)=
```{image} ../images/primers/git_setup11_windows.png
:width: 400px
:align: center
```
<br>

11) Select Git Credential Manager

(primers-git_setup12_windows)=
```{image} ../images/primers/git_setup12_windows.png
:width: 400px
:align: center
```
<br>

12) Enable file-system caching and click on "Install"

(primers-git_setup13_windows)=
```{image} ../images/primers/git_setup13_windows.png
:width: 400px
:align: center
```
<br>
Git will now begin to install and show a progress bar. 

13) Click "Finish" once installed

(primers-git_setup14_windows)=
```{image} ../images/primers/git_setup14_windows.png
:width: 400px
:align: center
```
<br>

Downloading Git will provide users with a new Git Bash terminal which recommend for setting up the `conda` environments and downloading the Git repositories as it allows the use of `conda` and `git`, and commands like `cd` and `ls`.

To launch Git Bash, go to the search bar in the Windows task bar and type "Git Bash".

(primers-git_launch1_windows)=
```{image} ../images/primers/git_launch1_windows.png
:width: 400px
:align: center
```
<br>

When the Git Bash app appears, open it to launch Git Bash terminal.

(primers-git_launch2_windows)=
```{image} ../images/primers/git_launch2_windows.png
:width: 400px
:align: center
```
<br>

Windows users will use this Git Bash terminal later to setup `conda`, create virtual environments, and `clone` Git repositories.

## Conda installation via Miniforge

[Conda](https://docs.conda.io/projects/conda/en/stable/user-guide/getting-started.html) (or its recent cousin, [Mamba](https://mamba.readthedocs.io/en/latest/)) is an environment manager that will be useful in running the tutorials in this book on your local machine. Using conda has the following benefits:
- Isolation of dependencies
- Reproducibility
- Ease of management
- Testing and development

If your computer does not have `conda` installed, we suggest installing [Miniforge](https://github.com/conda-forge/miniforge) as a way to get access to [Conda](https://conda.io/), [Mamba](https://github.com/mamba-org/mamba) and Python, with `conda-forge` as default channel.  
Once Miniforge is installed, you should be able to use `conda` and `mamba` in your terminal.  

We recommend installing Miniforge by downloading and running the provided installer for your OS from [https://conda-forge.org/download/](https://conda-forge.org/download/)  

### Mac & Linux

Download the installer `.sh` file and open your computer's terminal to run the command:

```
bash Miniforge3-$(uname)-$(uname -m).sh
```

:::{warning}
At the time of writing this documentation, the installer for macOS arm64 is named `Miniforge3-MacOSX-arm64.sh` while the `uname` command returns `Darwin`. So performing the above command results in `bash: Miniforge3-Darwin-arm64.sh: No such file or directory`. To fix this, simply run:
```
bash Miniforge3-MacOSX-arm64.sh # (i.e., run `bash` on the installer's file name)
```
:::

You may need to `cd ...` into the folder that contains your downloaded file first.

(primers-miniforge_setup1_macOS)=
```{image} ../images/primers/miniforge_setup1_macOS.png
:width: 600px
:align: center
```
<br>
After running the above commands, complete the following steps from the installer:

1) Agree to license terms and confirm the default location for install.

(primers-miniforge_setup2_macOS)=
```{image} ../images/primers/miniforge_setup2_macOS.png
:width: 600px
:align: center
```
<br>
After pressing ENTER, Miniforge will begin installing the required packages and solvers.

2) Type `yes` if prompted "Do you wish to update your shell profile to automatically initialize conda?" 

(primers-miniforge_setup3_macOS)=
```{image} ../images/primers/miniforge_setup3_macOS.png
:width: 600px
:align: center
```
<br>

Automatically initializing `conda` makes it easier to use.

3) **After Miniforge has finished installing, make sure to close and re-open the terminal for changes to take effect.**

(primers-miniforge_setup4_macOS)=
```{image} ../images/primers/miniforge_setup4_macOS.png
:width: 600px
:align: center
```
<br>

### Windows

Download and run the Windows installer `.exe` file.  

(primers-miniforge_setup1_windows)=
```{image} ../images/primers/miniforge_setup1_windows.png
:width: 400px
:align: center
```
<br>

As you go through the installer, complete the following steps:

1) Agree to the License Agreement

(primers-miniforge_setup2_windows)=
```{image} ../images/primers/miniforge_setup2_windows.png
:width: 400px
:align: center
```
<br>

2) Install for "Just Me (recommended)"

(primers-miniforge_setup3_windows)=
```{image} ../images/primers/miniforge_setup3_windows.png
:width: 400px
:align: center
```
<br>

3) Install in the default folder

(primers-miniforge_setup4_windows)=
```{image} ../images/primers/miniforge_setup4_windows.png
:width: 400px
:align: center
```
<br>

4) Check the following options to ensure `conda`/`mamba` can be accessed from Windows terminal

(primers-miniforge_setup5_windows)=
```{image} ../images/primers/miniforge_setup5_windows.png
:width: 400px
:align: center
```
<br>

5) Wait for installation and click on Next and Finish.

(primers-miniforge_setup6_windows)=
```{image} ../images/primers/miniforge_setup6_windows.png
:width: 400px
:align: center
```
<br>

(primers-miniforge_setup7_windows)=
```{image} ../images/primers/miniforge_setup7_windows.png
:width: 400px
:align: center
```
<br>

Miniforge has been installed on Windows!

Now for Windows, to set Git Bash to automatically initialize `conda`, run the following commands in Git Bash:

```
conda init bash
conda config --set auto_activate_base true
```

**Be sure to close and re-open GitBash after these commands for the changes to take effect.**

(primers-miniforge_setup8_windows)=
```{image} ../images/primers/miniforge_setup8_windows.png
:width: 600px
:align: center
```
<br>

(primers-miniforge_setup9_windows)=
```{image} ../images/primers/miniforge_setup9_windows.png
:width: 600px
:align: center
```
<br>

Once Git Bash has been re-opened, it should show you on start-up that you are in the `base` environment.

(primers-miniforge_setup10_windows)=
```{image} ../images/primers/miniforge_setup10_windows.png
:width: 600px
:align: center
```
<br>

## Creating a conda environment for running tutorials

:::{note}
Following the above setup instructions, Git Bash for Windows and Terminal for macOS & Linux will now work similarly with functionalities such as `conda`/`mamba`, `git`, `cd`, and `ls`. These programs will be referred to simply as "terminal" and the following instructions will be presented as applicable for an OS.
:::

We will now begin using the softwares we installed to clone the BOAT workshop Git repository, create a `conda` environment, and run code stored within a test Jupyter notebook.

### Cloning the Git repository

As discussed, Git facilitates version control while GitHub facilitates sharing and collaborating on Git repositories. At the interface between Git and GitHub exists the `git clone` command which allows users to download Git repositories onto their computers when those repositories are hosted on GitHub and have been made accessible to them.

1) Launch terminal and navigate (using `cd`) into the folder which will be storing the BOAT workshop Git repository

2) Run the command:
```
git clone https://github.com/BOAT-ocean-acoustics/fundamentals.git
```

The `fundamentals` Git repository will be dowloaded from the [GitHub URL](https://github.com/BOAT-ocean-acoustics/fundamentals.git) and contain the files stored within the published GitHub page.

As the Git repository continues to be updated, be sure to stay up-to-date by running the following commands in terminal under the `fundamentals` repository:

:::{caution}
The below commands will overwrite any changes you may have made to any notebooks. If you want to keep your changed files, we recommend renaming the files or moving them outside of the `fundamentals` repository into another folder. The below commands will simply download those files again if Git does not find that they exist under the same name in the same location.
:::

```
git fetch origin
git reset --hard origin/main
```

### Creating the `conda` environment

All coding projects have a minimal set of required packages necessary for the code to run successfully. `conda`/`mamba` helps in installing the required packages in isolated, project-specific environments. Git repositories containing code often provide a list of the required packages in files named `requirements.txt` or `environment.yml`.

For `fundamentals` (the BOAT workshop Git repository), we have provided a `requirements.txt` under the `boat_tutorials` directory.

1) Use terminal to navigate (using `cd`) into `fundamentals/boat_tutorials`

2) Run the command to create the `conda` environment named `boat-fundamentals`:
```
mamba create --name boat-fundamentals --file requirements.txt
```

:::{note}
Mamba is a drop-in replacement for conda that is generally faster and better at resolving dependencies so we can use it particularly when doing computationally intensive tasks such as creating/removing environments.
:::

3) The `boat-fundamentals` environment can be activated by running the command:
```
conda activate boat-fundamentals
```

### Launching a Jupyter notebook with JupyterLab

Jupyter notebooks are interactive and shareable documents designed to integrate live code, equations, comments, and visualizations in a single file. For the tutorials of this workshop, Jupyter notebooks will be extensively used to introduce fundamental ocean acoustics concepts with interactive code outputs known as "widgets". JupyterLab will be the editing environment we will use to open, edit, and work through our Jupyter notebooks.

1) Launch terminal and activate the `boat-fundamentals` environment
```
conda activate boat-fundamentals
```

2) Use `ipykernel` to install a kernel for the `boat-fundamentals` environment
```
python -m ipykernel install --user --name=boat-fundamentals
```

3) Navigate into the `fundamentals` repository and launch the JupyterLab editor by running:
```
jupyter lab
```

After running the above command, you should be taken to a website as shown below:

(primers-jhub_launch1)=
```{image} ../images/primers/jhub_launch1.png
:width: 600px
:align: center
```
<br>

If a website has not launched, go back to the same terminal window and copy-paste one of the provided URLs into a browser to access the website:

(primers-jhub_launch2)=
```{image} ../images/primers/jhub_launch2.png
:width: 600px
:align: center
```
<br>

4) Using JupyterLab's file explorer window, navigate to `boat-tutorials/primers` where we have stored the Jupyter notebook titled `environment_test.ipynb` that will test that the `boat-fundamentals` environment is set up on your machine.

(primers-jhub_launch3)=
```{image} ../images/primers/jhub_launch3.png
:width: 600px
:align: center
```
<br>

After you have opened the Jupyter notebook, click on `Python 3 (ipykernel)` to select the kernel named `boat-fundamentals` for this notebook.

Now we can start working through the Jupyter notebook!

### Working through the Jupyter notebook

As mentioned earlier, Jupyter notebooks are designed to integrate live code, notes, and visualizations in a single file. The main components of Jupyter notebooks are known as cells. Cells can either be designated as code cells (to hold Python code) or markdown cells (to hold Markdown notes).

The notebook we are providing for this tutorial has 3 code cells and 3 markdown cells. As we will see, there will also be 1 interactive widget once we complete running the notebook. 

1) Run the markdown cell written to introduce the notebook with a title, overview, and explanation for what the next cell is expected to do

2) Run the code cell written to import all the packages that will be used throughout the BOAT workshop. Any errors with this cell would only occur if our `conda` environment was incorrectly set up

3) Run the markdown cell written to explain the plotting method that comes after.

4) Run the code cell which contains the plotting method described in the previous cell. Running this cell will not print anything because this is simply a method definition meant to describe the code that will be run when the method is provided a parameter `std`

5) Run the markdown cell written to explain the widget and range of values that can be provided for `std`

6) Run the code cell designed to plot the interactive widget that should allow you to seamlessly play around with varying `std` values and seeing what the PDF curve looks like. 

We have now successfully cloned the BOAT workshop Git repository titled `fundamentals`, successfully built a `conda` environment called `boat-fundamentals`, and worked through the Jupyter notebook called `environment_test.ipynb`.
