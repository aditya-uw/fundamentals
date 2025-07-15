# Local environment setup

This page explains what Conda/Mamba is and how to install it using Miniforge. After this, the page shows how to create a `conda` environment and will show how to test that the environment is working by using it to run a Jupyter notebook. Instructions have been inspired from [similar documentation in other domain](https://biapol.github.io/blog/mara_lampert/getting_started_with_miniforge_and_python/readme.html) 

## Conda installation via Miniforge

[Conda](https://docs.conda.io/projects/conda/en/stable/user-guide/getting-started.html) (or its recent cousin, [Mamba](https://mamba.readthedocs.io/en/latest/)) is an environment manager that will be useful in running the tutorials in this book on your local machine. Using conda has the following benefits:
- Isolation of dependencies
- Reproducibility
- Ease of management
- Testing and development

If your computer does not have `conda` installed, we suggest installing [Miniforge](https://github.com/conda-forge/miniforge) as a way to get access to [Conda](https://conda.io/), [Mamba](https://github.com/mamba-org/mamba) and Python, with `conda-forge` as default channel.  
Once Miniforge is installed, you should be able to use `conda` and `mamba` in your terminal.  

We recommend installing Miniforge by downloading and running the provided installer for your OS from [https://conda-forge.org/download/](https://conda-forge.org/download/)  

**Mac & Linux**: Download the installer and open your computer's terminal to run the command:
```
bash Miniforge3-$(uname)-$(uname -m).sh
```

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

3) After Miniforge has finished installing, make sure to close and re-open the terminal for changes to take effect.

(primers-miniforge_setup4_macOS)=
```{image} ../images/primers/miniforge_setup4_macOS.png
:width: 600px
:align: center
```
<br>

**Windows**: Download and run the Windows installer `.exe` file.  

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

We recommend using Git Bash for setting up the `conda` environments and downloading the GitHub repositories so please [download Git](https://git-scm.com/downloads) if you don't have Git already. This will give you access to Git Bash which is a terminal that allows the use of `conda`, `git`, and commands like `cd` and `ls`.

To set Git Bash to automatically initialize `conda`, run the following commands in Git Bash:
```
conda init bash
conda config --set auto_activate_base true
```

Be sure to close and re-open GitBash after these commands for the changes to take effect.

(primers-miniforge_setup8_windows)=
```{image} ../images/primers/miniforge_setup8_windows.png
:width: 400px
:align: center
```
<br>

(primers-miniforge_setup9_windows)=
```{image} ../images/primers/miniforge_setup9_windows.png
:width: 400px
:align: center
```
<br>

(primers-miniforge_setup10_windows)=
```{image} ../images/primers/miniforge_setup10_windows.png
:width: 400px
:align: center
```
<br>



## OOI-data-observations

The OOI-data-observations GitHub repository contains code developed for accessing and processing data from multiple instruments for various data rveiews and assessments and the production of QC test limits. For setup purposes, this repository contains the `environment.yml` file that we will parse using `conda` to create a virtual environment called `ooi` with all the required packages installed. This repository also contains the test notebook we will be using called `create_annotations.ipynb` which will import the packages, load data from the publicly available [OOI Gold Copy THREDDS catalog](https://thredds.dataexplorer.oceanobservatories.org/thredds/catalog/ooigoldcopy/public/catalog.html), and perform some analysis.

To download the OOI-data-observations GitHub repository, use the command:
```
git clone https://github.com/oceanobservatories/ooi-data-explorations.git
```

To create the `ooi` environment, after installing Miniforge and downloading the above repository, use the commands:
```
cd ooi-data-explorations/python
conda env create -f environment.yml
```

To enter your newly created `ooi` environment, use the command:
```
conda activate ooi
```

Once you have activated an environment, you can use the command `conda install ...` to install any specific packages not already installed. Because we created `ooi` using the environment.yml file, it will already have some packages installed. The list of packages installed can be seen in `ooi-data-explorations/python/environment.yml`

While you are in the `ooi-data-explorations/python` directory, run the command `conda develop .` so that the packages inside can be imported from anywhere on your computer.

Add the newly created `ooi` environment to the list of JupyterLab kernels using the command:
```
python -m ipykernel install --user --name=ooi
```

## OOI data access credentials

In order to access data and/or metadata (e.g., calibration coefficients) collected from the OOI, we need to set our access credentials. Once you have your credentials set up on your computer, you do not need to re-run these commands.

- If you haven't already done so, either create a user account on the [OOI Data Portal](https://ooinet.oceanobservatories.org/) (original OOI website and API server for the OOI M2M system), or use the [CILogon](https://cilogon.org/) button with an academic or Google account (login button is towards the upper right corner of the web page) to login to the portal.
- After you login, the “Log In” text will change to your username.
- Click on your username and then on the “User Profile” element of the drop down.
- Copy and save the following values from the user profile: `API Username` and `API Token`.

Users need to create a .netrc file in their home directory to store these access credentials. Using the below commands, create a .netrc file (replacing the `API_Username` and `API_Token` text below with the corresponding values from your login credentials for the [OOI Data Portal](https://ooinet.oceanobservatories.org/)) so that your computer can have the OOI data access credentials linked to your user account on the [OOI Data Portal](https://ooinet.oceanobservatories.org/):
```
# These 2 commands can be run separately
touch .netrc
chmod 600 .netrc

# Copy-paste the below command to set your OOINet credentials 
# (make sure to replace API_Username and API_Token below with your credentials!!)
cat <<EOT >> .netrc
machine ooinet.oceanobservatories.org
login API_Username
password API_Token
EOT
```

## Testing the setup

Now we can run the provided example notebook within the ooi-data-explorations directory to see if all the packages have been installed properly. You may wonder why we are copying over a notebook instead of just opening it. This will allow us to keep an original copy of the notebook in case we end up changing the notebook in testing and/or debugging. We will realize during the summer school that this is where forking GitHub repositories becomes useful! For now, let's just copy the single test notebook. 

```
# First, go to the home directory
cd ~
# Create a local folder for working with different OOI data sets
mkdir -p data/adhoc/testing
# Copy some example notebooks over from the code directory
cd code/ooi-data-explorations/python/examples/notebooks/phsen/
cp * ~/data/adhoc/testing
cd ~/data/adhoc/testing
```

Now in `~/data/adhoc/testing` launch the Jupyter notebook `creating_annotations.ipynb`. We recommend using VSCode to launch this notebook.

:::{note}
In VSCode, you will need to first install the Python and Jupyter extensions in order to select the `ooi` kernel to run your notebook.
:::

## GitHub updates

The ooi-data-explorations code is a work in process and is being updated and refined regularly. To make sure
you have the most recent code, copy/paste the following code block into a terminal:
```
cd ~/code/ooi-data-explorations
git checkout master
git pull
```