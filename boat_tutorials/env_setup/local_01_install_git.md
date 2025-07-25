(env_setup-local_git)=
# Install Git

[Git](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F) is a version control system that is designed to track changes in files stored within repositories. [GitHub](https://docs.github.com/en/get-started/start-your-journey) offers a platform for storing and collaborating on various Git repositories. 

:::{caution}
Installing Git requires administrator access to your computer.
:::

## Mac & Linux

Terminals come pre-installed with Git so there are no steps required to install Git.

To launch terminal, go to Spotlight Search or Applications and find the Terminal app to open.

(primers-git_launch1_macOS)=
```{image} ../images/primers/git_launch1_macOS.png
:width: 100px
:align: center
```
<br>

## Windows

Git can be installed in two different ways on Windows. The first is through using Windows' command-line interface (CLI). The second is by downloading the Windows installer with a graphical user interface (GUI). 

If this is the first you install Git, we recommend using the GUI installer to see where Git will be installed on your computer and to easily select the settings specific to your Git software.



### Install using CLI

Git may be installed using a CLI as long as the user has the `winget` tool (installed by-default on Windows 10 and Windows 11), can access the internet, and have a CLI like Windows Powershell or Command Prompt (should be available by default). We will be using Windows Powershell in the screenshots below.


1) Launch your CLI and enter the command below:
    ```
    winget install --id Git.Git -e --source winget --custom '/o:Components=ext,gitlfs,assoc,assoc_sh /o:EditorOption=Nano /o:SSHOption=OpenSSH /o:CurlOption:OpenSSL /o:BashTerminalOption=MinTTY'
    ```

(primers-winget_git_setup1)=
```{image} ../images/primers/winget_git_setup1.png
:width: 700px
:align: center
```
<br>

(primers-winget_git_setup2)=
```{image} ../images/primers/winget_git_setup2.png
:width: 900px
:align: center
```
<br>

2) You will be prompted for administrator password and `winget` will proceed to download and install Git

(primers-winget_git_setup3)=
```{image} ../images/primers/winget_git_setup3.png
:width: 900px
:align: center
```
<br>

:::{note}
The command provided above installs Git with the same settings as the GUI install explained in the section below. If you want to install with different settings, you can refer to [this guide](https://gitforwindows.org/mapping-between-git-installer-gui-settings-and-command-line-arguments.html) to configure the settings.

A command commonly found online is `winget install --id Git.Git -e --source winget`
:::



### Install using GUI

[Download](https://git-scm.com/downloads) and run the Windows installer `.exe` file.  

After double-clicking on the installer `.exe` file, you will first be prompted to enter your administrator password.
Once the setup window has opened, complete the following steps:

1) Read the license and click on "Next" to continue

(primers-git_setup1_windows)=
```{image} ../images/primers/git_setup1_windows.png
:width: 700px
:align: center
```
<br>

2) Install Git in the default location and continue

(primers-git_setup2_windows)=
```{image} ../images/primers/git_setup2_windows.png
:width: 700px
:align: center
```
<br>

3) Leave the default components selected and continue

(primers-git_setup3_windows)=
```{image} ../images/primers/git_setup3_windows.png
:width: 700px
:align: center
```
<br>

4) Select the default Start Menu folder and continue

(primers-git_setup4_windows)=
```{image} ../images/primers/git_setup4_windows.png
:width: 700px
:align: center
```
<br>

5) Change the default editor used by Git to nano which is a simpler alternative to vim

(primers-git_setup5_windows)=
```{image} ../images/primers/git_setup5_windows.png
:width: 700px
:align: center
```
<br>

6) Override the default branch name for new repositories to be "main"

(primers-git_setup6_windows)=
```{image} ../images/primers/git_setup6_windows.png
:width: 700px
:align: center
```
<br>

7) Allow Git from the command line and also 3rd-party software

(primers-git_setup7_windows)=
```{image} ../images/primers/git_setup7_windows.png
:width: 700px
:align: center
```
<br>

8) Use the OpenSSL library as the HTTPS transport backend

(primers-git_setup8_windows)=
```{image} ../images/primers/git_setup8_windows.png
:width: 700px
:align: center
```
<br>

9) Checkout Windows-style, commit Unix-style line endings

(primers-git_setup9_windows)=
```{image} ../images/primers/git_setup9_windows.png
:width: 700px
:align: center
```
<br>

10) Use MinTTY as the terminal emulator to use with Git Bash

(primers-git_setup10_windows)=
```{image} ../images/primers/git_setup10_windows.png
:width: 700px
:align: center
```
<br>

11) Select fast-forward or merge as the default behavior for git pull

(primers-git_setup11_windows)=
```{image} ../images/primers/git_setup11_windows.png
:width: 700px
:align: center
```
<br>

12) Select Git Credential Manager

(primers-git_setup12_windows)=
```{image} ../images/primers/git_setup12_windows.png
:width: 700px
:align: center
```
<br>

13) Enable file-system caching and click on "Install"

(primers-git_setup13_windows)=
```{image} ../images/primers/git_setup13_windows.png
:width: 700px
:align: center
```
<br>
Git will now begin to install and show a progress bar. 

14) Click "Finish" once installed

(primers-git_setup14_windows)=
```{image} ../images/primers/git_setup14_windows.png
:width: 700px
:align: center
```
<br>

:::{note}
If there are any Git installation steps not covered in the instructions above, we recommend using default settings or using other online tutorials as found on [Hostman](https://hostman.com/tutorials/installing-git-on-windows/), [PhoenixNAP](https://phoenixnap.com/kb/how-to-install-git-windows), or [How-To Geek](https://www.howtogeek.com/832083/how-to-install-git-on-windows/). 
:::

### Post-installation

Downloading Git will provide users with a new Git Bash terminal which recommend for setting up the `conda` environments and downloading the Git repositories as it allows the use of `conda` and `git`, and commands like `cd` and `ls`.

To launch Git Bash, go to the search bar in the Windows task bar and type "Git Bash".

(primers-git_launch1_windows)=
```{image} ../images/primers/git_launch1_windows.png
:width: 700px
:align: center
```
<br>

When the Git Bash app appears, open it to launch Git Bash terminal.

(primers-git_launch2_windows)=
```{image} ../images/primers/git_launch2_windows.png
:width: 900px
:align: center
```
<br>

Windows users will use this Git Bash terminal later to setup `conda`, create virtual environments, and `clone` Git repositories.
