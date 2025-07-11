# OOI data access for local machine

Note: Some of the instructions presented below will have been a part of the setup for OOI JupyterHub access and coding. These instructions have been provided here with the purpose of being able to set up OOI data access and environment installation on your local machine without needing JupyterHub as a platform.

## Miniforge

JupyterHub comes with conda installed so that users can create virtual environments from the start. However, if your computer does not have conda installed, we suggest installing [Miniforge](https://github.com/conda-forge/miniforge) as a way to get access to [Conda](https://conda.io/), [Mamba](https://github.com/mamba-org/mamba) and Python, with conda-forge as default channel.  
Once Miniforge is installed, you should be able to use `conda` and `mamba` in your terminal.  

We recommend installing Miniforge by downloading and running the provided installer for your OS from [https://conda-forge.org/download/](https://conda-forge.org/download/)  

**Mac & Linux**: Download the installer and open your computer's terminal to run the command:
```
bash Miniforge3-$(uname)-$(uname -m).sh
```
You may need to `cd ...` into the folder that contains your downloaded file first.

**Windows**: Download and run the Windows installer.  

Follow the installer and type `yes` if prompted "Do you wish to update your shell profile to automatically initialize conda?" 

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

Note: In VSCode, you will need to first install the Python and Jupyter extensions in order to select the `ooi` kernel to run your notebook.

## GitHub updates

The ooi-data-explorations code is a work in process and is being updated and refined regularly. To make sure
you have the most recent code, copy/paste the following code block into a terminal:
```
cd ~/code/ooi-data-explorations
git checkout master
git pull
```