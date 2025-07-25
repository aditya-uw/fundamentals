(env_setup-local_conda)=
# Install conda via Miniforge

[Conda](https://docs.conda.io/projects/conda/en/stable/user-guide/getting-started.html) (or its recent cousin, [Mamba](https://mamba.readthedocs.io/en/latest/)) is an environment manager that will help us set up a computational environment to run the tutorials. Using conda has the following benefits:
- Isolation of dependencies
- Reproducibility
- Ease of management
- Testing and development

If your computer does not have `conda` installed, we suggest install via [Miniforge](https://github.com/conda-forge/miniforge). 

We recommend installing Miniforge by downloading and running the installer for your operation system from [https://conda-forge.org/download/](https://conda-forge.org/download/). Below we summarize the steps.


## Mac & Linux

Download the shell script (the `.sh` file) and open a terminal to run the command:

```shell
$ bash Miniforge3-$(uname)-$(uname -m).sh
```

:::{warning}
At the time of writing this documentation, the installer for macOS arm64 is named `Miniforge3-MacOSX-arm64.sh` while the `uname` command returns `Darwin`. So performing the above command results in `bash: Miniforge3-Darwin-arm64.sh: No such file or directory`. To fix this, simply run:
```
$ bash Miniforge3-MacOSX-arm64.sh # (i.e., run `bash` on the installer's file name)
```
:::

You may need to `cd` (change directory) into the folder that contains your downloaded file first. For example, below we `cd` into the `~/Downloads` first before running the command:

(primers-miniforge_setup1_macOS)=
```{image} ../images/env_setup/miniforge_setup1_macOS.png
:width: 900px
:align: center
```
<br>
<br>

After running the above commands, complete the following steps from the installer:

1) Agree to license terms and confirm the default location for install. After pressing ENTER, Miniforge will begin installing the required packages and solvers.

(primers-miniforge_setup2_macOS)=
```{image} ../images/env_setup/miniforge_setup2_macOS.png
:width: 900px
:align: center
```
<br>

2) Type `yes` if prompted "Do you wish to update your shell profile to automatically initialize conda?" Automatically initializing `conda` makes it easier to use.

(primers-miniforge_setup3_macOS)=
```{image} ../images/env_setup/miniforge_setup3_macOS.png
:width: 900px
:align: center
```
<br>


3) **After Miniforge has finished installing, make sure to close and re-open the terminal for changes to take effect.**

(primers-miniforge_setup4_macOS)=
```{image} ../images/env_setup/miniforge_setup4_macOS.png
:width: 900px
:align: center
```
<br>



## Windows

Download and run the Windows installer (the `.exe` file).

(primers-miniforge_setup1_windows)=
```{image} ../images/env_setup/miniforge_setup1_windows.png
:width: 700px
:align: center
```
<br>

Follow the steps below as you go through the installer:

1) Agree to the License Agreement

(primers-miniforge_setup2_windows)=
```{image} ../images/env_setup/miniforge_setup2_windows.png
:width: 700px
:align: center
```
<br>

2) Install for "Just Me (recommended)"

(primers-miniforge_setup3_windows)=
```{image} ../images/env_setup/miniforge_setup3_windows.png
:width: 700px
:align: center
```
<br>

3) Install in the default folder

(primers-miniforge_setup4_windows)=
```{image} ../images/env_setup/miniforge_setup4_windows.png
:width: 700px
:align: center
```
<br>

4) Check the following options to ensure `conda`/`mamba` can be accessed from Windows terminal

(primers-miniforge_setup5_windows)=
```{image} ../images/env_setup/miniforge_setup5_windows.png
:width: 700px
:align: center
```
<br>

5) Wait for installation and click "Next" and "Finish"

(primers-miniforge_setup6_windows)=
```{image} ../images/env_setup/miniforge_setup6_windows.png
:width: 700px
:align: center
```
<br>

(primers-miniforge_setup7_windows)=
```{image} ../images/env_setup/miniforge_setup7_windows.png
:width: 700px
:align: center
```
<br>

Miniforge has now been installed on Windows!


To set Git Bash to automatically activate `conda` whenever a terminal is opened, run the following commands:

```
conda init bash
conda config --set auto_activate_base true
```

**Be sure to close and re-open GitBash after these commands for the changes to take effect.**

(primers-miniforge_setup8_windows)=
```{image} ../images/env_setup/miniforge_setup8_windows.png
:width: 900px
:align: center
```
<br>

(primers-miniforge_setup9_windows)=
```{image} ../images/env_setup/miniforge_setup9_windows.png
:width: 900px
:align: center
```
<br>

Once Git Bash has been re-opened, it should show you on start-up that you are in the `base` environment (you should see "(base)" on the left).

(primers-miniforge_setup10_windows)=
```{image} ../images/env_setup/miniforge_setup10_windows.png
:width: 900px
:align: center
```
<br>
