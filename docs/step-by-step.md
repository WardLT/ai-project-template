## First Steps

The following sections are a step-by-step on how to build your project from scratch.

### Start a Git Repository

Git is a "version-control" system that lets you keep track of incremental changes in your project.
You can use git to record why you changed a specific line in a file,
create a "checkpoint" after finishing series of complicated steps in your project,
or keeping experiments you are unsure about seperate from what already works.
For your first steps, we'll detail the "create change, then record them" workflow that is 90% of what you'll use git for.

Start off by [installing Git](https://git-scm.com/) or your system, then using the command line to navigate to the folder that will be the home for your project.

Once in that folder, call `git init .`. `init` will add a new folder, `.git`, to your folder that will keep track of all of your future changes.

To start, make a file named `README.md` and type a bit about your project. `.md` files are interpreted by GitHub (and many other places) as "Markdown" files that contain formatted text. [See the Markdown tutorial](https://www.markdowntutorial.com/) to learn how to use them for your benefit.

Now that you have your first file, call `git add README.md` then `git commit` to register `README.md` and any later changes to your repository. 
Calling `git commit` will ask you for a short description about the changes you made.
"Initial commit" is the standard for your first commit, but you should be prepared to write more later.

> **Note**: `git commit` is going to open a command line text editor. See the links to `vim` and `nano` tutorials in an [earlier section](#what-do-i-expect-you-know-already)

See [GitHub's tutorial](https://docs.github.com/en/get-started/quickstart) for a more in-depth guide to git. 

### Sync your repository to GitHub

Now that your have your first commit, it is time to push it to GitHub.

Go to GitHub and [follow their directions](https://docs.github.com/en/get-started/quickstart/create-a-repo) to create a new repository.
You do not need to initialize it with anything (e.g., a `README.md`, or ignore files) as we are doing that manually as part of this tutorial.

> **Note**: If you forget and just commit things anyway, that's OK. `git` will give you instructions on how to merge your changes.

GitHub will give you some lines on how to push your existing repository up to GitHub.

### Add a Python environment

Keeping track of which versions of libraries you use is key for others to reproduce your science later.

My recommended route is to define your computational environment with an Anaconda "environment" file.
I name this file, `environment.yml`, and it looks something like the following:

```yaml
name: projname  # Memorable name for the project (no whitespace!)
channels:  # List of anaconda "channels" to search for packages. Typically just the defaults and conda-forge are necessary
  - defaults  # List "defaults" first so Anaconda tries here first
  - conda-forge 
dependencies:
  # Start with a specific version of Python (pick a newer one!)
  - python==3.9.*  #  Says any 3.9 version is OK
  
  # Put in the main libraries you may need (I always use Pandas and matplotlib)
  - pandas==1.4.*
  - matplotlib>3
  
  # Then put in development tools and Jupyter
  - jupyterlab
  - pytest
  - pip
  
   # Add packages only accessible via pip later
   - pip:
       - pytest-timeout  # Might be available on conda 🤷
  
```

A few bits of advice: 

- [*Learn YAML*.](https://www.cloudbees.com/blog/yaml-tutorial-everything-you-need-get-started) It is easy to write it "by hand" and later read it in software.
- *Specicify at least [a minor version](https://semver.org/).* I.e., list at least two numbers for major packages (3.9.* not 3.*). The minor versions will ensure you get the latest bug fixes for a package but without major changes in the API.
  - I use `matplotlib>3` above because matplotlib has changed very little over years
- *Be selective about adding new packages.* Only specify the packages you call import on, and delete ones you no longer loose. Larger environments are harder to recreate.

Once you have this environment file, try to build it:

```
conda env create --file environment.yml --force
```

Once you've done this, follow Anaconda's instructions to active your new environment and get ready to do reproducible research!

> **Note**: Rather than adding new packages to an environment using `conda install`, I typically edit the environment file and re-build the environemnt from scratch. Rebuilding it myself each time I make changes helps ensure someone else can build it later.
