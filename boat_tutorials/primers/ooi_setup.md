# OOI setup

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
