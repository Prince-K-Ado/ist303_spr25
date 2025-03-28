---
marp: true
theme: gaia
#size: 4:3
#_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
---
# First github commit 
getting updates from your machine into a github repo
![bg right:60% 80%](rsc/anxious.gif)

---
### Set up your workspace
1) Login to Github.com and create a new repository
2) Open a terminal window, create a directory to house your project: \
`mkdir test_dir`
3) Navigate to the directory: \
`cd test_dir`
4) Initialize Git: \
`git init`
5) make a new file, _file1.txt_, with some text in it: \
`echo "orange persimmons" > file1.txt` 

---
<style scoped>
{font-size: 32px;}
</style>
### In search of the first commit: Connecting to Github
Workspace is set up and there are local changes you want to send to github. Connect your local machine to a github repo via the terminal (only need to do once per repo):

1. Establish a connection to a remote (github) repository:
    #### `git remote add REMOTENAME https://github.com/GITHUBUSERNAME/GITHUBREPONAME.git`
2. Verify the connection with `git remote -v`

Recommend using _origin_ for REMOTENAME. You can also get the url from the github repo (navigate on github to: code->https->copy button) if unsure about formatting above.

---
<style scoped>
{font-size: 31px;}
</style>
## The first commit

1) stage local changes for commit (saved locally to INDEX):
    - `git add .` (all files/changes not in your working repo), or
    - `git add 'fileName'` (specify single file)
4) See what will be committed: `git status`
4) Commit local changes (saved locally to HEAD):
    - `git commit -m "your message describing the changes"`
5) Push changes in local repo to remote repository:
    - `git push -u REMOTENAME BRANCHNAME` \
    _Note that -u denotes upstream (remote); downstream is local. REMOTENAME is the name you used in the 'git remote add' command; BRANCHNAME is the name of the local branch to push (i.e. main)_
---
## Check your github repository!
![bg right:60% 100%](rsc/first_commit.jpg)

---
#### Github Exercise
Refer to the previous slides for help with the exercise.
You will also need the `git clone` command, which copies a complete remote repository into a local repository:

`git clone https://github.com/GITHUBUSER/GITHUBREPO.git LOCALDIRNAME`

example: \
`git clone https://github.com/damapak/ist303_spr2025.git clone_test`

_what will the directory name be on your local machine in the above example?_

---
#### Other Git commands that may help with the assignment (not necessary)
- check remote repo connections in your working directory: \
`git remote -v`
- list the names of all branches (local in green, remote in red) \
`git branch --all`

---
# Virtual Environments and Git
(Still in the terminal)
- Add a virtual environment to the working directory so you can install flask, pytest, and any other needed python packages
- Tell Git to ignore the virtual environment 

_Can you think of reasons for the second step?_

---
## Project setup update: add a virtual environment
From your project directory in the terminal, create a virtual environment and store it in a dir named _venv_:
- ## `python -m venv venv`

---
## Configure virtual environment
- Activate the virtual environment (`./venv/Scripts/activate`) 
- Install needed python packages
- ignore the venv folder to prevent it from being uploaded to github

---
<style scoped>
{font-size: 31px;}
</style>
## Ignoring files in Git
There are a few options for telling Git to ignore certain directories and files.
#### Option 1: create a _.gitignore_ file
- this file is not created by Git - you create it and place it in the project directory
- create it as you would any new text file, except the complete file name is simply _.gitignore_
- open and edit the file in a text editor, adding the name directories/files to ignore
- see [recommended gitignore file for python](https://github.com/github/gitignore/blob/main/Python.gitignore)
- works on a per-project basis (not global)
---
<style scoped>
{font-size: 38px;}
</style>
#### Option #2: edit the _.git/info/exclude_ file
- Git creates this file when your project is initiated
- notice the _exclude_ file has no extension, in contrast with _.gitignore_ which is only an extension
- open with text editor and add directories/files you want excluded
- works on a per-project basis (not global)
---

### Where is the _.git_ folder? (A word on hidden files and folders)
The _exclude_ file (no extension) is within a "hidden" directory. Hidden directories begin with a `.`

To view all files from terminal, including hidden files:
- windows (powershell): `ls -Force`
- mac/linux: `ls -la`

Now navigate to _.git/info_ and type `cat exclude` to output its contents to the terminal 

---
## Recap
We've seen how to:
- Navigate in the terminal
- Use the terminal to create directories for our projects
- Initialize Git in the project folder
- Create a virtual environment in our project folder
- Activate the venv and install needed python packages 
- Use Git in the terminal to connect to Github repositories

_folder, directory, and repository all describe where project files are_

---
## You are here:
![](rsc/dilbert_envt.png)

---
### Optional (advanced) resources for understanding how Git functions
(You do not need to know any of this for the class)
- [Julia Evans: where do Git files live](https://jvns.ca/blog/2023/09/14/in-a-git-repository--where-do-your-files-live-/)
- [All Julia's posts on Git](https://jvns.ca/#git)
---

## Additional Github features
This will be helpful for the team projects, but not required.
- Github Projects: trello-like tracking boards
- Github Actions: CI tools to automate builds, tests, etc.


### [next: Flask](./week02_05_slides_flask)
