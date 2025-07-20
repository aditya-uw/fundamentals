(env_setup-local_create_env)=
# Create an conda environment

:::{note}
Following the above setup instructions, Git Bash for Windows and Terminal for macOS & Linux will now work similarly with functionalities such as `conda`/`mamba`, `git`, `cd`, and `ls`. These programs will be referred to simply as "terminal" and the following instructions will be presented as applicable for an OS.
:::

We will now begin using the softwares we installed to clone the BOAT workshop Git repository, create a `conda` environment, and run code stored within a test Jupyter notebook.

## Cloning the Git repository

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

## Creating the `conda` environment

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

## Launching a Jupyter notebook with JupyterLab

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

4) Using JupyterLab's file explorer window, navigate to the `boat-tutorials/env_setup` folder where we have stored a Jupyter notebook titled `local_env_test.ipynb`. This notebook lets us test and ensure that the `boat-fundamentals` environment is set up on your machine.

(primers-jhub_launch3)=
```{image} ../images/primers/jhub_launch3.png
:width: 600px
:align: center
```
<br>

After you have opened the Jupyter notebook, click on `Python 3 (ipykernel)` to select the kernel named `boat-fundamentals` for this notebook.

Now we can start working through the Jupyter notebook!

## Working through the Jupyter notebook

As mentioned earlier, Jupyter notebooks are designed to integrate live code, notes, and visualizations in a single file. The main components of Jupyter notebooks are known as cells. Cells can either be designated as code cells (to hold Python code) or markdown cells (to hold Markdown notes).

The notebook we are providing for this tutorial has 3 code cells and 3 markdown cells. As we will see, there will also be 1 interactive widget once we complete running the notebook. 

1) Run the markdown cell written to introduce the notebook with a title, overview, and explanation for what the next cell is expected to do

2) Run the code cell written to import all the packages that will be used throughout the BOAT workshop. Any errors with this cell would only occur if our `conda` environment was incorrectly set up

3) Run the markdown cell written to explain the plotting method that comes after

4) Run the code cell which contains the plotting method described in the previous cell. Running this cell will not print anything because this is simply a method definition meant to describe the code that will be run when the method is provided a parameter `std`

5) Run the markdown cell written to explain the widget and range of values that can be provided for `std`

6) Run the code cell designed to plot the interactive widget that should allow you to seamlessly play around with varying `std` values and seeing what the PDF curve looks like. Results for this cell will be similar to what's shown below:

(primers-normal_slider)=
```{image} ../images/primers/normal_slider.gif
:width: 400px
:align: center
```
<br>

We have now successfully cloned the BOAT workshop Git repository titled `fundamentals`, successfully built a `conda` environment called `boat-fundamentals`, and worked through the Jupyter notebook called `local_env_test.ipynb`.
