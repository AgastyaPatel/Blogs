# What is Git?
Version Control System for programmers and track changes in the code.
# Git Commands
- git status
- git add 
- git commit -m "message"
- git log
- git stash, git stash pop, git stash drop
- git branch 'feature' , git checkout 'feature', git checkout -b 'feature-new' , git branch -d 'feature'
- **git restore** --staged filename.txt : to remove from tracked files
- **git reset HASHID** : resets the codebase to the specified commit.
- **git remote add origin URL** :  Your repository should be the origin repository. Origin is your repository now
- **git push origin master** : Push the commits into the origin repo/Master branch
- **git merge feature** : merges the branch to main
- https://education.github.com/git-cheat-sheet-education.pdf

## Forking and Pull request
Take a repository and fork it into your account.
- **git clone your-repo-url** : to clone the repository folder in the current active folder
- **git upstream source-repo-url** : adds the upstream 
- **git push origin agastya -f** : to be used if the earlier pushed online commit has been modified locally and is to be pushed
### Fetch commits is used to get updated code from the upstream repository
checkout origin branch in your main repository.


FYI: Although the usual workflow to start with the codebase of another project is to first fork it and then clone the fork, you may be tempted to simply clone the `upstream` project since it is quite convenient to do so from your local machine using the `git clone` command. If you do so, you will note that the project you clone from will by default become the `origin` repo. But since you likely don't have write access to the upstream repo that you cloned from, you will not be able to push your changes to it. Don't worry. You can easily rename the origin to upstream using the command `git remote rename origin upstream` and then add a new origin using `git remote add origin <url>` to point to the URL of a new GitHub repo that you have created or have access to, and use that repo for making your changes to the fork's code.

---

- ls la .git : Shows all the git files 
- git checkout -b my1stbranch : Creates new branch as well as switches to it
- echo 'Here is some text in my newfile.' >> newfile :: adds the text into newfile
- cat newfile: prints the newfile
- git branch -d my1stbranch :  delete my1stbranch
- git push :  transfer changes to remote repo
- git fetch : transfer changes to local repo
- git pull : git fetch + git merge

# Git Advance
#git_advance
```bash
# Change Directory
cd M:/
cd "M:\asdf"

git clone url
# Get config 
git config --list
git config --list --global/system/local
git config user.name
git config user.email

# Change config
git config --global user.name "My Name"
git config --global user.email "email@mail.com"

# Fetch all of the remote braches
git fetch 
# To show all hidden branches (remote along with local)
git branch -a

# Remove a file from stage
git reset HEAD <File>
git log --oneline
# Add selective parts of file to staging area
git add -p <file>

# Relink the local branch to origin branch if name changed 
git branch -u origin/new-branch local-branch
# Change name of local branch
git branch -m local-branch new-branch
# Show linking of local and remote branch
git branch -vv

# Remove a folder from being tracked after adding in .gitignore
git rm -r --cached <folder>

# Decorated logs
git log --oneline --decorate --all --graph
```


https://stackoverflow.com/questions/59561657/how-can-i-ignore-dist-folder-in-gitignore-file
