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
