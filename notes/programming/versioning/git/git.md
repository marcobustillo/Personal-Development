# Git

## Table of Contents
- [Dictionary](#dictionary)
- [Common Used Commands](#common-used-commands)
- [Git Ignore](#git-ignore)
- [Help](#help)
- [Common Errors](#common-errors)
- [Deploying to GH pages](#deploy)


## Dictionary
- Master branch : default branch name
- HEAD : Last commit in the repository
- REPO_NAME : Repository name(Changeable)
- BRANCH_NAME : Branch name(Changeable)
- COMMAND : Chosen command in help list

## Common Used commands

Creating a new Repository
- Go to www.github.com and enter your credentials
- Create a new repository
- Choose a repository name
- Copy the HTTPS link/url provided to you by github
- Open terminal or command line
- Go to desktop or any directory you want to create a folder for your repository
- Since you are already in command line/terminal use mkdir FOLDER_NAME
- Change directory to the FOLDER_NAME you created
- Create a readme.md file using the command echo "# SAMPLE REPO_NAME" >> README.md
- Use the following Commands
```git
git init
git add README.md
git commit -m "Commit message"
git remote add origin HTTPS URL/LINK you have copied
git push -u origin master
```
- Once finished you now have created a new repository

Check repository status
```git
git status
```
Check commit history
```git
git log
```

Download repository and set user
```git
git clone URL
git config user.name "Name"
git config user.email "Email"
```

Clone a branch inside a repository
```git
git clone -b BRANCH_NAME REPO_NAME
```

Push commit from branch1 to branch2
```git
git push REPO_NAME BRANCH_NAME1:BRANCH_NAME2
```

A previously cloned repository on a server can now pull changes(**Note:** clone is only used for the first time you want a repository)

```git
git pull REPO_NAME BRANCH_NAME
```

Commit/Upload changes to repository
```git
git add .
git commit -m "Commit message"
git push REPO_NAME BRANCH_NAME
```

Prompt username and passwoord
```git
git config --local credential.helper ""
git push origin master
```

## Git Ignore

This is a list of files/folders to be ignored in commits. To use it, create a `.gitignore` file in the working directory, **NOT** inside `.git`.  

Each line in the file is a new ignore rule. Ex. To ignore `node_modules/`, just add that as one line.  

If the ignoring is added after committing the files to be ignored, they need to be untracked. Use `git rm -r --cached .` to untrack everything, and the `git add/git commit`. **Careful as this can lose progress to files.**   

Also, pattern matching can be used to ignore specific files in specific places. Ex. `*.txt` ignores all text files, while `routes/*.js` ignores all javascript files in that folder. To ingore a folder, use `FOLDER/`.

Finally, use `#` to comment.

## Help

List all help commands
```git
git help
```

Explain help command
```git
git help COMMAND
```
**Note:** Once you selected any command in the help list it will open a new browser tab

## Common Errors

## Deploying to Github Pages

- First create desired Repository
- Create react application
- Install gh-pages as dev dependency using `npm install --save-dev gh-pages`
- Add these things to the package.json
```javascript
"homepage":"http://username.github.io/<REPO_NAME>"
"scripts":{
  "deploy":"gh-pages -d build"
}
```
- Initialize git repository on the root react application
- Add the created repository as origin
- Run `npm run build` to build your application
- Run `npm run deploy` to deploy your build application to gh-pages
- [Optional] Commit your source code to the master branch of your git repository
