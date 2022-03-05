# AI Project Template

A template for organizing projects that use AI to solve scientific problems.
The organization is designed with a few goals in mind:

1. *Reproducibility*: Ensure that all work towards a project is easy to capture.
1. *Development Best Practices*: Make it easy to develop complex code using established tools and practices
1. *Teamwork*: Create good entry points for others to join your project
1. *Publication*: Minimal effort should be required to archive the project
1. *Efficiency*: None of the above goals should interfere with executing the science

## How to use this repository

Easy ways to get started are either to create your own GitHub repository then mirror the layout here as you progress,
or to [download the repository](https://github.com/WardLT/ai-project-template/archive/refs/heads/main.zip) then 
delete or edit files to make it your own.

We offer a few routes to understanding how to use this structure:

1. [A step-by-step walkthrough](#first-steps)
1. [An overview of the project layout](#layout)
1. [A dive into the rationale behind it](#rationale)


### What do I expect you know already?

This guide is targeted at people who already have some exposure to scientific computing and, in some places, machine learning.
Specifically, you should be familiar with:

1. *Using the command line.* If you don't, check out [DjangoGirls' tutorial](https://tutorial.djangogirls.org/en/intro_to_command_line/). Also, prepared to experience a command-line text editor like [vim](https://www.openvim.com/) or [nano](https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/)
1. *Python basics.* Know how to make a script and execute it from the command line
1. *Jupyter*. I think Jupyter is a fantastic tool, if [used](https://docs.google.com/presentation/d/1n2RlMdmv1p25Xy5thJUhkKGvjtV-dkAIsUXP-AL4ffI/edit#slide=id.g362da58057_0_1) [effectively](https://www.youtube.com/watch?v=7jiPeIFXb6U). [Jupyter's website](https://jupyter.org/) does a good job of explaining what you can do with them.

We are going to teach you the basics of:

1. Version control, and how it helps you organize.
1. Python environments, and how they are necessary for reproducibility
1. CLI scripts, and how to use them to record experiments
1. Data publication, because publishing papers is not enough.

## First Steps

The following sections are a step-by-step on how to build your project from scratch

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

> Note: `git commit` is going to open a command line text editor. See the links to `vim` and `nano` tutorials in an [earlier section](#what-do-i-expect-you-know-already)

See [GitHub's tutorial](https://docs.github.com/en/get-started/quickstart) for a more in-depth guide to git. 

### Create a GitHub repository

Now that your have your first commit, it is time to push it to GitHub.

Go to GitHub and [follow their directions](https://docs.github.com/en/get-started/quickstart/create-a-repo) to create a new repository.
You do not need to initialize it with anything (e.g., a `README.md`, or ignore files) as we are doing that manually as part of this tutorial.

> Note: If you forget and just commit things anyway, that's OK. `git` will give you instructions on how to merge your changes.

GitHub will give you some lines on how to push your existing repository up to GitHub.

## Project Layout

TBD

## Rationale

TBD.