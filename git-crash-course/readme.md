## Git Hidden Folder 

There are an hidden folder called `.git` which tell you that our project is a git repo.

If you want to create a git repo in a new project we create the folder and initalize that repo using `git init`

```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md
git status
git add .

```

## cloning

We can clone three ways: HTTPS, SSH, Github CLI

Since we are using Github Codespaces we'll a create temparary directory in our workspace

```sh
mkdir /workspace/tmp
cd /workspace/tmp
```

### HTTPS

```sh
git clone https://github.com/mazin990/Github-Examples.git
cd Github-Examples
```
> You'll need to generate Github Access Token (PAT)
https://github.com/settings/tokens

You will use the PAT as your password when you login

- Give it access to Content for Commits

### GitHub SSH

```ssh
git clone git@github.com:mazin990/Github-Examples.git
cd Github-Examples
```

We will need to create our own SHH rsa key pair

```sh
sshe-keygen -t rsa
```
For WSL users and if you create a non defualt key you may need to add it 

```sh
eval `ssh-agent`
ssh-add /home/mazin/.ssh/alt-github_id_rsa
```



We can test our connection here :

```
ssh -T git@github.com
```

### GitHub CLI 

Install the CLI 

eg. Linux (Ubuntu) 
```sh
sudp apt update 
sudo apt install gh
```

```
gh login 
gh repo clone mazin990/Github-Examples
```

## Commits

When we want to commit code we can write git commit which will open up the commit edit message in the editor of choice.

```sh
git commit
```

Set the global editor

```
git config --global core.editor emacs
``` 

Make a commit and commit message without opening editor
```sh
git commit -m "add another exclamation"
```

## Branches

List of branchs

```
git branch
```

Create a new branch

```
git branch branch-name
```
Checkout the branch

```
git checkout dev
```

## Remotes

## staging

## Merging

## Add

When we want to stage changes that will be included in the commit
We can use the . to add all possible files.

```
git add Readme.md
git add .

```

## Reset

Reset allow you to move staged changes to be unstaged.
This is useful when you to revert all files not to be commited 

```
git add .
git reset
```
> git reset will revet a git add . 

## Status 

Git status shows you what files will or will not be commited.

```
git status
```

## Gitconfig file 

The git config file is what stores your global configuration for git such as email, name editor and more.

```
git config --list
```

When you first install Git on a machine you are suppose to set up your name and email

```
git config --global user.name "jhon Doe"
git config --global user.email johndoe@example.com
```

## Log

Git log will show recent git commits to the git tree.


## Push

When we want to push a repo to our remote origin

```
git push
```
