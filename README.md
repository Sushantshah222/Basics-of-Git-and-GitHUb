
### Install Git on Windows

1. Download the latest Git for Windows installer.

2. When you've successfully started the installer, you should see the Git Setup wizard screen. Follow the Next and Finish prompts to complete the installation. The default options are pretty sensible for most users.

3. Open a Command Prompt (or Git Bash if during installation you elected not to use Git from the Windows Command Prompt).

4. Run the following commands to configure your Git username and email using the following commands, replacing Emma's name with your own. These details will be associated with any commits that you create:
   
```bash
$ git config --global user.name "Pi Innovations"
$ git config --global user.email "sushantshah@pi-innovations.com.np"
```
To check the configured username and user email in your Git configuration,

```bash
git config user.name
```
```bash
git config user.email
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

To check the configured username and user email in your Git configuration,

```bash
git config user.name
```
```bash
git config user.email
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

To check the configured username and user email in your Git configuration,

```bash
git config user.name
```
```bash
git config user.email
```

### Basic Unix based commands

List Files and Directories

```bash
ls
```

Change Directory

```bash
cd <directory-path>
```
Create a Directory

```bash
mkdir <directory-name>
```
Create a File

```bash
touch <file-name>
```

Remove (Delete) a File

```bash
rm <file-name>
```

Remove (Delete) a Directory

```bash
rm -r <directory-name>
```
Copy File

```bash
cp <source-file> <destination-file>
```

Move/Rename File or Directory
```bash
mv <source> <destination>
```
Display File Content

```bash
cat <file-name>
```
Edit a File

```bash
nano <file-name>
```
Print Working Directory

```bash
pwd
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

To unstage and discard the changes in your working directory

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
git log --oneline
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
### Branching in Git

To create a new branch, use the git branch
```bash
git branch <branch-name>
```

To switch to the newly created branch, 
```bash
git checkout <branch-name>
```

```bash
git switch <branch-name>
```

A more concise way to create and switch to a new branch
```bash
git checkout -b <branch-name>
```

To see a list of existing branches and identify the current branch,
```bash
git branch
``` 

After making changes in a branch, you can merge those changes back into the main branch. First switch back to the branch you want to merge into then,

```bash
git merge <branch-name>
```

To delete a branch,
```bash
git branch -d <branch-name>
```

```bash
git branch --delete <branch-name>
```

To rename the current branch,
```bash
git branch -m <new-branch-name>
```

### Pushing changes to remote repository

Ensure remote repository is properly configured,
```bash
git remote -v
```

It's a good practice to pull changes from the remote repository before pushing to avoid conflicts,

```bash
git pull <remote-name> <branch-name>
```

Use the `git push` command to push your local changes to the remote repository,
```bash
git push <remote-name> <branch-name>
```

Using flag `-u` allows you to set up tracking, which means that your local branch is associated with a remote branch.It's often used the first time you push a branch to a remote repository, after the first time you can simply use command `git push`.

```bash
git push -u <remote-name> <branch-name> 
```


In some cases, you might need to force-push changes using flag `-f `  if the remote branch has diverged from your local branch. However, use force-push cautiously, especially on shared branches, as it rewrites the history.

```bash
git push -f <remote-name> <branch-name>
```

### Stashing Changes

To stash your changes,

```bash
git stash save "stash message"
```
If you want to include untracked files in the stash,

```bash
git stash -u
```

To view the list of stashes,
```bash
git stash list
```

To apply the most recent stash and remove it from the stash list,
```bash
git stash apply
```

If you have multiple stashes and want to apply a specific one, you can specify the stash by its ID,

```bash
git stash apply stash@{}
```

To apply the most recent stash and remove it from the stash list in a single command,
```bash
git stash pop
```

If you want to create a temporary branch from a stash,
```bash
git stash branch <branch-name> 
```

To remove a stash without applying it,
```bash
git stash drop stash@{2}
```
To remove all stashes,
```bash
git stash clear
```
