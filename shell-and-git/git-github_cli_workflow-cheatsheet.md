# Notes on Git and GitHub

## Preliminary Defintion

_Git_ is a software developed by Linus Torvalds to provide software developers with a tool for Version Control. It stores the current status of a software in a "repository", which one can imagine as 1-n safe state(s) called a "commit". A "commit" contains the current status of the software as well as the history of all commits which preceded the most recent commit. A git repo is safed locally on the hard drive by default but can be used to share Version Control for a software project with others. Git is controlled through the CLI.

_GitHub_ is a and web-app-based service which provides a GUI for Git and Version Control as well as software project management in the cloud. Its a service based on _Git_ providing services such as:

- Online Live Access to the repos
- Management of Branches and Commits in a GUI for better collaboration

## Important stuff about Git

- Don't initialize a repo within another repo
- Use iTerm to move into dir with repos, inside repos use terminal inside VS Code

## Important stuff about GitHub

- When pulling a remote repo from GitHub to (local) repo, use SSH and not HTTPS
- Commit to repo and then push it to remote repo

## Most Important CLI commands for Git and GitHub w/ workflows

👆🏻 hier müssen Unterkapitel zu den commands und ops aus "git-advanced" hinzugefügt werden

### Git/GitHub ops workflow in a nutshell

Given that repo is initialized(=exists) and on GitHub

1. git add
2. git commit -m ""
3. git push

👆🏻 das hier muss um die commands und ops aus "git-advanced" erweitert werden

### Initialize Repo - Git and Remote

#### Git (local)

1. Check Status of dir/repo

```shell
git status
```

2. Initialize repo

```shell
git init
```

#### GitHub (remote)

1. Create Repo on GitHub
2. Choose SSH as encryption method
3. Copy into terminal in local repo

```shell
git remote add origin git@github.com:GitHubUsername/repository-name.git
git branch -M main
git push -u origin main
```

4. Check status of new remote repo

```shell
git remote -v
```

### Create Commit Workflow

1. Add files to the stage

```shell
git add <filename>
```

```shell
git add .
```

if you want to add all

2. Create a commit with a good note

```shell
git commit -m "note"
```

3. Push to remote repo

```shell
git push
```

#### Get updates from GitHub

```shell
git pull
```

use this in the current branch if you made a commit from within GitHub

### Manage branches

```shell
git branch branch-name
```

create a new branch

```shell
git switch -c <branchname>
```

create a new branch and switch to it

```shell
git switch <branchname>
```

switch branches

```shell
git branch
```

list your branches

```shell
git branch -a
```

list all branches (local and remote)

```shell
git branch -d <branchname>
```

delete a branch

Remember: if you are in the current branch, just use git pull to fetch the status of your post PR review

Remove tracking branches from remote repos (on GitHub)

```shell
git fetch --prune
```

> Suppose you've previously fetched all branches from origin, including feature-branch. If someone deletes feature-branch from origin and you subsequently run git fetch --prune, Git will remove the remote-tracking branch origin/feature-branch from your local repository.

> In summary, git fetch --prune is a command that updates your local repository with the latest changes from the remote repository and removes any remote-tracking branches that have been deleted on the remote side. This helps keep your local repository up-to-date and free from obsolete references.

### Delete repo

```shell
rm -rf ./git
```

- Removing the git folder turns a git repo back into a regular dir
- This erases all commits as well
