
### Install Git on Windows

1. Download the latest Git for Windows installer.

2. When you've successfully started the installer, you should see the Git Setup wizard screen. Follow the Next and Finish prompts to complete the installation. The default options are pretty sensible for most users.

3. Open a Command Prompt (or Git Bash if during installation you elected not to use Git from the Windows Command Prompt).

4. Run the following commands to configure your Git username and email using the following commands, replacing Emma's name with your own. These details will be associated with any commits that you create:
   
```bash
$ git config --global user.name "Pi Innovations"
$ git config --global user.email "sushantshah@pi-innovations.com.np"
```


### Install Git on Linux

1. From your shell, install Git using **apt-get**:
```bash
$ sudo apt-get update
$ sudo apt-get install git

OR

$ sudo dnf install git

```

2. Verify the installation was successful by typing git --version:
```bash
$ git --version
git version 2.9.2
```

3. Configure your Git username and email using the following commands, replacing Emma's name with your own. These details will be associated with any commits that you create:
```bash
$ git config --global user.name "Emma Paris"
$ git config --global user.email "eparis@atlassian.com"
```

### Git for Mac

Install Git with Homebrew

If you have installed Homebrew to manage packages on OS X, you can follow these instructions to install Git:

1. Open your terminal and install Git using Homebrew:
   
```bash
$ brew install git
```

2. Verify the installation was successful by typing which `git --version`:
```bash
$ git --version
```

### Initializing a new repository: git init

To create a new repo, you'll use the `git init` command. 
git init is a one-time command you use during the initial setup of a new repo. 
Executing this command will create a new `.git` subdirectory in your current working directory. This will also create a new main branch. 

```bash
cd /path/to/your/existing/code 
git init
```

### Checking Status of your repository : git status

To check the status of your repository you will use the command `git status`.
git status provide the status of any track and untrack files in your repository.

```bash
git status
```

### Staging the changes : git add

To stage the changes, you will use the `git add` command.
git add is a command you will use to track the changes so that you can commit in the next commit. git add allows git to keep track of the changes that you are making in the files. Here we can conclude that staging a changes is a way of keep track of changes by git that you desire and make in the files.

```bash
git add 'filename'
```

### Commiting Changes : git commit

To commit the changes that you have staged using `git add` command, you will use `git commit` command.
While commiting the changes you need to also include the logical commit message that provides clear insight of what changes that you committed in this very commit using flag `-m` as:
```bash
git commit -m 'commit message'
```

Use the `git commit` command to create a commit. 
This opens a text editor for you to write a commit message.

```bash
git commit
```

### Unstaging the changes : git reset

To unstage specific files, you can use the command `git reset`

```bash
git reset <file1> <file2>
```

To unstage all changes, you can use `git reset` as

```bash
git reset
```

To not only unstage but also discard the changes in your working directory you can use `--hard` flag
```bash
git reset --hard
```

### Viewing Project History

To see a list of commits, you can use the `git log` command. This command displays information about each commit, including the commit hash, author, date, and commit message.

```bash
git log
```
To view a more condensed log,

```bash
git log --online
```
To see a list of branches and their last commit,

```bash
git branch -v
```
To view the changes introduced by a specific commit,

```bash
git show <commit-hash>
```

To see a list of remote branches,

```bash
git branch -r
```

To see the changes between two commits,

```bash
git diff <commit1 hash> <commit2 hash>
```

To see a reference log that shows the history of branch references,
```bash
git reflog
```

### Removing commit from the project history : git revert/git reset

`git revert` command creates a new commit that undoes the changes introduced by a previous commit. This is a safer option, especially if the commit has been pushed to a shared repository because it does not alter the existing history.

```bash
git revert <commit-hash>
```
`git reset` command is more powerful but should be used with caution, especially if the commit has already been pushed to a shared repository. It allows you to move the branch pointer to a specific commit, effectively discarding all commits after that point.

```bash
git reset --hard <commit-hash> 
```

To move the branch pointer to a specific commit and add to staging the changes made in previous commit, you can use

```bash
git reset --soft <commit-hash> 
```
