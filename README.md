# Verify installation

git --version → show the version installed <br>
git --help → show a list of git commands <br>

# Configure git

git config --global user.name “Flavio” → configure name <br>
git config --global user.email “flaviomaricato@gmail.com” → configure email <br>
git config --global color.ui auto → enables command line coloring output <br>
git config → lists available commands <br>
git config -l → list the configuration that was made previously <br>

# Initializing Git Repository

git init . → create a repository in the actual directory <br>
rm -rf .git → removes the repository created <br>

# Git add

git status → gives the status of changes that we’ve made <br>
git add index.html → adds index.html to the staging area <br>
git rm --cached index.html → removes index.html from the staging area <br>
git add . → add all the files to the staging area from the current directory downwards <br>
git rm -r --cached . → remove all the files from the staging area from the current directory downwards <br>
git add -A → add all the files no matter the folder you are <br>

# Commits

git commit -m “commit message” → creates a commit with files that are inside the staging area <br>
git log → see the changes we have committed <br>
git show b3c07e0a0de288e4ff3030cfcc49b9764da61364 → show the particular commit based on its hash <br>
git diff → Difference between what you have in the current working directory and what has been committed <br>
git restore index.js → Discard changes made <br>

# Amend commit messages

git commit --amend -m “updated message” → to amend a git commit message <br>

# Create a GitHub Repo

git remote add origin https://github.com/flaviomaricato/learning-git.git → sets the remote patch for the branch <br>
git branch → List the branches <br>
git branch -M main → Changing the default branch to main (renaming process by Git because of the pejorative term that master could have) <br>
git push -u origin main → push the content to the remote repository, after the first time use just git push. If you have two factor authentication, create a token for your machine at https://github.com/settings/tokens and paste it as your password when asked (first push)  <br>
git push → push fom local machine to remote <br>

# Git Pull

git pull → bring the latest changes from remote <br>

# Working with branches

git branch → shows the branch you are at that moment <br>
git branch -r → lists the branches on the remote server <br>
git branch -a → lists all branches (local and remote) <br>
git branch feature-a → create a new branch (copy of the actual) called feature-a <br>
git checkout feature-a → to switch branches (switched feature-a) <br>
git checkout feature-a → to switch branches (switched feature-a) <br>
git push --set-upstream origin feature-a OR git push -u origin feature-a → Push a new (not the main) branch to the server <br>
git checkout -b to-delete → create a new branch and checks out to it <br>
git branch -d to-delete → delete branch called to-delete <br>

# Pull Requests

You will never push to the main branch directly: create a branch, make changes, push the branch to remote so you won't lose your chances then raise a pull request. This way someone will review your changes and aprove it or not before merging them to the main. <br>

# Merging and Pull Requests

git merge feature-a → Take the changes from feature-a and merge to the main (prefer using pull requests on the website)  <br>
git log --oneline → show the logs in one line <br>
git pull → updates your repository bringing changes from remote to local <br>

# The General Workflow

Pull first, create a new branch, work on it, commits, etc... <br>
Rebase your changes against main specially if you're working in the feature more than 1 day because main is still "going on". <br>
Pull again, rebase, you may have conflicts. <br>
You have many commit you'll need to resolve the conflict in all of them, it's advisable to squash all of your local commits first, rebase, stash the commit, resolve the conflicts (now there's just on because of the squash) them commit, push and raise a pull request. <br>

# Rebase

Is when the main has moved on and you don't have the lastest changes in your branch that you're working on. You tried to pull the changes and apply them to your current branch then you push to remote and raise a pull request. <br>

git pull -r origin main → to rebase (read text above) <br>
git rebase --continue → after the rebase unitl no more conflicts <br>
git push -f → after the rebase and all conflicts resolved <br>

