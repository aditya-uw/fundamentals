(env_setup-local_create_env)=
# Create a conda environment

:::{note}
All setup steps below will be run through a terminal. If you are on Linux or MacOS, this is the "Terminal" app. If you are on Windows and have followed the guide on this site to [install Git](env_setup-local_git), this is the Git Bash.
:::

We will now use git and conda/mamba to clone the BOAT tutorial repository and create a computational environment to run a test Jupyter notebook to ensure everything works fine.


## Clone the tutorial repository

Git is a version control tool that can be used locally, while GitHub facilitates sharing and collaborating via web-hosted repositories. We can use the `git clone` command to download GitHub repositories to our own computer.

1) Launch a terminal and navigate (using `cd`) into the folder which you would like the BOAT tutoral repository to be save in. For example, the command below navigates into a directory called `git_repos`:
    ```shell
    $ cd git_repos
    ```

2) Run the command below to clone (download) the BOAT tutorial repository from GitHub. You should then have a new folder called `fundamentals` under `git_repos`.
    ```shell
    $ git clone https://github.com/BOAT-ocean-acoustics/fundamentals.git
    ```

3) Navigate into the `fundamentals` repository directory (assuming you are in `git_repos`)
    ```shell
    $ cd fundamentals
    ```

:::{tip}
If you have previously cloned the repository and want to get the latest version, run the following commands:
```shell
$ cd git_repos/fundamentals  # make sure you are in the tutorial repo
$ git fetch origin
$ git reset --hard origin/main
```
Note these commands will overwrite any changes you may have made in the repo folder. If you want to keep your changed files, rename the files or move them outside of the `fundamentals` folder.
:::



## Create a `conda` environment

All coding projects have a minimal set of required packages necessary for the code to run successfully. `conda`/`mamba` can help us install the compatible versions of these packages in isolated, project-specific environments. Here, we will use `conda` to create an environment that contains all packages specified in `requirements.txt` in the tutorial repository.

1) Assume the tutorial repository you just clone lives under the `git_repos` directory. In your terminal, navigate (using `cd`) into `git_repos/fundamentals/boat_tutorials`:
    ```shell
    $ cd git_repos/fundamentals/boat_tutorials
    ```

2) Run the command to create a `conda` environment called `boat-fundamentals`:
    ```shell
    $ mamba create --name boat-fundamentals --file requirements.txt
    ```

:::{note}
`Mamba` is a drop-in replacement for `conda` that is generally faster and better at resolving dependencies.
:::

3) Activate the `boat-fundamentals` environment:
    ```shell
    $ conda activate boat-fundamentals
    ```

4) Use `ipykernel` to install a Jupyter kernel for the `boat-fundamentals` environment. See the next section for why we want to use Jupyter.
    ```shell
    $ python -m ipykernel install --user --name=boat-fundamentals
    ```


## Launch a Jupyter notebook with JupyterLab

Now that we have create a conda environment for running the tutorials, let's test it by trying to run a Jupyter Notebook to make sure everything is working fine.

[Jupyter](https://jupyter.org/) Notebooks are interactive and shareable documents that integrates live code, equations, comments, and visualizations in a single file. The tutorial materials on this site are all executable Jupyter Notebooks with interactive "widgets" that can help us develop physical intuitions on ocean acoustics problems. We will run the notebooks using the JupyterLab interface.

:::{tip}
Check out Project [Jupyter](https://jupyter.org/) to understand the Jupyter ecosystem!
:::

Let's now we launch the JupyterLab:
    ```shell
    $ jupyter lab
    ```

You should be taken to a website as shown below:

(primers-jlab_launch1)=
```{image} ../images/primers/jlab_launch1.png
:width: 900px
:align: center
```
<br>

If this website has not launched, go back to the same terminal window and the provided URL (typically http://localhost:8888) into a browser to access the website:

(primers-jlab_launch2)=
```{image} ../images/primers/jlab_launch2.png
:width: 900px
:align: center
```
<br>

4) Using JupyterLab's file explorer window, navigate to the `boat_tutorials/env_setup` folder where we have stored a Jupyter notebook named `local_env_test.ipynb`. This notebook lets us test and ensure that the `boat-fundamentals` environment is working fine.

(primers-jlab_launch3)=
```{image} ../images/primers/jlab_launch3.png
:width: 900px
:align: center
```
<br>

After you have opened the Jupyter notebook, click `Python 3 (ipykernel)` on the upper-right corner and select the kernel named `boat-fundamentals` for this notebook.

Now you can start working through the Jupyter notebook!



## Work through the test Jupyter notebook

As mentioned earlier, Jupyter notebooks integrates live code, notes, and visualizations in a single file. The main components of Jupyter notebooks are known as cells. Cells can be designated as "Code" cells (to hold programming code), "Markdown" cells (to hold Markdown notes), or "Raw" strings ().

The `local_env_test.ipynb` notebook has 3 code cells and 3 markdown cells, and will produce an interactive widget once we run through all cells in the notebook. 

1) Run the markdown cell that introduces the notebook with a title, overview, and explanation for what the next cell is expected to do.

2) Run the code cell that imports all packages needed for running code in this notebook. If errors occur when you run this cell, your `conda` environment is not set up correctly.

3) Run the markdown cell that explains the plotting code that will be used later.

4) Run the code cell that contains the plotting code. Running this cell will not print anything because this is simply a function definition. The actual code content will be run as part of the widget in the last cell.

5) Run the markdown cell that explains the widget and range of values that can be provided for the variable `std`, which is the standard deviation for normal distribution.

6) Run the code cell that will produce an interactive widget, which would allow you to see how normal distribution changes with varying `std` value, like below:

(primers-normal_slider)=
```{image} ../images/primers/normal_slider.gif
:width: 700px
:align: center
```
<br>

If you can run the widget as seen above, you have everything you need to run all tutorials on this site!
