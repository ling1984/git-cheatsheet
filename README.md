# git-cheatsheet
Some of the most useful git commands, made for people who are new to git.
- [Setting Up](#setup)
- [Git Status](#status)
- [Branching](#branching)
- [Adding Changes](#add)
- [Committing](#commit)
- [Pushing](#push)
- [Merging](#merge)
- [Conflicts](#conflict)
- [Pull](#pull)
- [Reset](#reset)
- [Common Problems](#common)

## Setting up <a name="setup"></a>

```
git clone <repo web addres>
```
Makes a folder the same name as the repo, in current folder you are in on your terminal.

Downloads the repo to this folder.

## Git Status <a name="status"></a>

```
git status
```
Shows your current branch, all your changes, staged files, **VERY IMPORTANT COMMAND**.

## Branching <a name="branching"></a>
```
git branch
```
Shows all of your branches.

```
git checkout <branch name>
```
Makes the specified **(already existing)** branch your current branch. 
```
git checkout -b <branch name>
```
Makes a new branch with branch name, then changes you to it. 
```
git branch <branch name>
```
Makes the branch with the name, does not swap to it.

#### Branch naming
Please name the branch what feature/ bug you are changing/ implementing.
Make it short and descriptive.

Please do not call it "Your name's branch".
No one knows what you are doing if you do this.

## Adding changes <a name="add"></a>

```
git add <filename>
```
Adds the specified file to staged.
```
git add .
```
Adds **everything** from the folder you are in, even untracked things, to staged.

```
git add -u
```
Adds all **tracked files** that have changes to staged.

```
git restore --staged <filename or .>
```
Removes from staged.

## Committing <a name="commit"></a> 
```
git commit -m "your commit message here"
```
Adds all your staged changes to a commit.

**Always** add a message explaining what you changed:
1. It is much clearer what you did when you have to look through the commit history to fix something
2. If you reading this, I know you do not know how to use Vim.

## Pushing <a name="push"></a>
```
git push -u origin <branch name>
```
Pushes (uploads) your changes to the branch specified. After using this once, you can just:
```
git push
```

## Merging <a name="merge"></a>
```
git merge <branch name>
```
This merges the specified branch into your current branch.

**However, I recommend using the GitHub website to create a pull request as it makes it harder to make mistakes with merging.**

Go onto the pull requests tab in your repo, create a pull request with the source and target repos. Then you can review it and see if it can be automatically merged.
If it can, do so. If it cannot, read the next section.

## Conflicts <a name="conflict"></a>

#### What are conflicts
Conflicts are when the same thing has been changed twice, and git does not know which version you consider the one to keep and which one the one to get rid of.

#### How to avoid them
Communicate with other people what everyone is working on.

Try to only change one thing (page/ file) per branch and not change absolutely everything because this increases the chances of conflicts, especially if you wait until 30 minutes before the deadline of a project to try and merge in to main.

Folders/ files that consist of peoples' configs i.e. .vs, .vscode, .DS_Store probably shouldn't be included.

Also generated files i.e. Release, build, dist, Debug, .pdb or even .exe.

#### How to fix them
If the file is not "git readable" i.e. changes are shown in bits not lines of code, it is very hard so really avoid this.

Otherwise, github should provide a way that shows both changes and lets you delete what you want.

## Pull <a name="pull"></a>
```
git pull
```
Pulls changes from the repo, will change your current branch if something new has been pushed/ merged into it.

```
git fetch
```
Updates your information from the repo, downloads all the changes/ commits/ new branches.
Does not change your current branch.

```
git pull = git fetch + git merge
```
## Reset <a name="reset"></a>
```
git reset --hard HEAD
```
Resets you back to the commit on the current branch.

## Common problems <a name="common"></a>

#### Q: Why doesn't my branch show up on Github?
A: you have to push something to it for it to show.

