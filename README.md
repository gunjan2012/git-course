![image](https://initialcommit.com/img/initialcommit/baby-git-release.png)

# 1. Git Basics:

## What is Version Control System?

- It is a software that helps software developers to work together and maintain a complete history of their work.

## Types of VCS:

1. CVCS : Centralized version control system.

- it uses a central server to store all files. 
- The major drawback of CVCS is if the disk of the central server gets corrupted then you will lose the entire history of the project

![image](https://user-images.githubusercontent.com/125242584/219282906-5b90643d-6354-47b3-8349-29250edb548f.png)

2. DVCS : Distributed/Decentralized version control system .

- DVCS clients check out the latest snapshot of the directory and fully mirror the repository.
- If the server goes down, then the repository from any client can be copied back to the server to restore it. Every checkout is a full backup of the repository.

![image](https://user-images.githubusercontent.com/125242584/219284486-f2403e19-d4cc-4e27-959c-26a29317955b.png)


## What is Git?

- Git is Distributed version control system.
- Git is open source project.

## Workflow of Git:

![image](https://user-images.githubusercontent.com/125242584/219288681-8bbcc71c-6a9c-4393-89a3-57dc1a267331.png)

## Installation of Git Client:

- For GNU/Linux.

  sudo apt-get install git-core </br>
  password for ubuntu:

  git --version</br>
  git version 1.8.1.2

## Git Environment Setup:

1. Setting UserName:
- `git config --global user.name "user123"`

2. Setting email id:
- `git config --global user.email "user123@example.com"`

3. Listing Git settings:
- `git config --list`

## Git General workflow:

![image](https://www.tutorialspoint.com/git/images/life_cycle.png)

# 2. Setting up a repository:

## What is a Git repository?

- A Git repository is a virtual storage of your project. It allows you to save versions of your code, which you can access when needed.

## Initializing a new Git repo:
`git init` : Intializing the new repository. </br>

## Cloning an existing Git repo: 
`git clone` : Copy the existing repository.</br>

## Cloning specific branch:
`git clone --branch` 

## Deleting Git Repository:
`rm -rf .git` : Deleting the .git folder from our local.</br>

## Rename file:
`git mv old_name new_name`

## Ignoring files:
- `.gitignore` file is used for ignoring files that we don't want to share. <br/>
- For example a software that generates the logs stored in log file that are not important so in that case we ignore that file, another is we don't push `passwords`,`private-keys` to git repo.
- Also we don't push `node_modules` in our project.</br>
- Git will not track files and folders specified in `.gitignore` . However, the `.gitignore` file itself IS tracked by Git.

## Ignoring tracked files or folders:
`git rm --chached file_name ` : started ignoring file. <br/>
`git rm --chached -r folder_name/ ` : started ignoring folder.

## Configuration setting with `git config`:

## git config levels: 

- `--local` : By default, git config will write to a local level.
- `--global` : Global level configuration is user-specific.
- `--system` : System-level configuration is applied across an entire machine.

Command: `git config --global user.email "your_email@example.com"` <br/>

## Configuration with remote branch:
`git remote add <remote_name> <remote_repo_url>`

# 3. Saving changes:

## Add files to staging area:
`git add file_name` : Adding single file. </br>
`git add . ` : Adding all the files from working directory to staging area.

![image](https://user-images.githubusercontent.com/125242584/219566835-bc7f29f2-5003-4e49-be11-7f249e706122.png)

## Commit a snapshot of all changes:
`git commit -a`

## Committing a modified version of a file to the repo:
`git commit -m "Commit Message" `

## Viewing commit:
`git show commit_id` : showing particular commit.</br>
`git show HEAD~N` : N is how many steps you have to go forward.

## Modify the last commit:
`git commit --amend`

## Ignoring a previously committed file:
`git rm --cached file_name`

# 4. Inspecting a repository:

## Status of your repo:
`git status` : give the status of branch.</br>
`git status -s` : give short status message(file name only).

## Viewing Staged and Unstaged Changes:
`git diff`

## Viewing the history:
`git log` : shows detail history. </br>
`git log --oneline` : shows history in oneline.</br>
`git log --oneline --reverse` : shows history in reverse order.</br> 

## Filter history:
`git log --oneline --author="author_name" ` : filter commit by author name. </br>
`git log --oneline --before/--after="YYYY-MM-DD or yesterday" ` : filter commit before or after date. </br>
`git log --oneline --grep="ANYNAME" ` : filter commit with specific word </br> 

# 5. Undoing Changes:

## Git Checkout:
`git checkout commit_id`: we can checkout the commit. </br>

## Git Clean:
`git clean -f` : remove all untracked files. </br>
`git clean -n` : list all the files that are removed.

## Git Revert:
`git revert commit_id or HEAD~N` : Used for undoing changes.

![image](https://user-images.githubusercontent.com/125242584/219369799-bf3bc076-e5e8-4eb1-8803-94443d910778.png)

## Git Reset:

### Types of reset:
- Hard reset.
- Soft reset.
- Mixed reset.

### Hard reset:
`git reset --hard commit_id`: uncommit + unstage + delete changes, nothing left. </br> 
`git reset --hard HEAD^N`
 
### Soft reset:
`git reset --soft commit_id` : uncommit changes, changes are remain in staged (index).</br>

### mixed reset:
`git reset --mixed commit_id` : uncommit + unstage changes, changes are reamain in working tree.</br>

## Removing file from working directory as well as staging area:
`git rm file_name` </br>
`git rm *.txt` 

## Unstaging files:
`git restore --staged file_name` : restore file from stage to working directory. </br>
`git restore file_name` : undo all the local changes.

# 6. Branching:

## Git Branch:
`git branch branch_name` : creating new branch.<br/>
`git checkout/switch branch_name` : switch to another branch.<br/>
`git checkout/switch -b branch_name` : create and switch to new branch.<br/>
`git branch` : give list of available branch.

## Rename Branch: 
`git branch -m old_name new_name ` : changed branch with new name.

## Deleting Branch:
`git branch -D branch_name` : Delete branch.

## Compare Branches:
`git diff first_branch..second_branch`</br>
`git diff second_branch` : comparing current branch with second_branch.

## Stashing:
- Stashing means we can store our changes to safe place.</br>
`git stash push -m "MESSAGE"`  </br>
`git stash list` : list of all stash.</br>
`git stash drop 1` : remove the 1st stash. </br>
`git stash clear` : remove all stashes.

## Merging:
- Merging is about to bring one branch to another.

1. Normal Merge:
- It will add extra merge commit. </br>
- command: `git merge branch_name`

![image](https://user-images.githubusercontent.com/125242584/219355213-14c04a55-6b77-49c9-af16-ce662f49b94f.png)

2. Squash merge: 
- It will merge the feature branch's all commits into one commit and merge it with the master branch.</br>
- command: `git merge --squash branch_name `

## Rebase:
- It is used to add changes from feature branch to main/master branch without any commit message.</br>
- command : `git rebase feature_branch`.

![image](https://user-images.githubusercontent.com/125242584/219356237-cf262c47-c72e-417a-94cc-6dc7ea27115e.png)

## Rebase interactive:
- It is used to edit particular commit order after rebase.
- command : `git rebase -i commit_id`

## Cherry-pick:
- It is used when we want to take particular commit to our main/master branch.</br>
`git cherry-pick commit_id` : This command will add commit of cherry-pick operation. </br>
`git cherry-pick commit_id -n` : This command will not add commit of cherry-pick operation. </br>

![image](https://user-images.githubusercontent.com/125242584/219357401-00ba328b-50d7-479f-bf5c-f596a51175d2.png)

## Remote Repository:

`git remote` : List the remote connections you have to other repositories. </br>
`git remote -v` : List the remote connections you have to other repositories with url. </br>
`git remote add <name> <URL>` : Create new connection to remote repositoy. </br>
`git remote rm <name>` : Remove the connection to the remote repository.</br>

## Push:

- This command is used to write to a remote repository.<br/>
Command: `git push <remote-name> <branch-name>`

## Removing remote branch:

`git push origin -d <branch_name>` : Remove </br>

## Fetch:

`git fetch <remote>` : Only fetch all the branches from remote but not merge.<br/>
`git fetch <remote> <branch>` : fetch specific branch from remote.

## Pull:

- It is a combination of `merge` and `fetch`. <br/>
`git pull <remote>` : fetch all branches and merge.<br/>
`git pull --no-commit <remote>` : same as above but not generate merge commit.