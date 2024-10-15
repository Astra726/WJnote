# Share and collaborate on your project using GitHub.

## Create a Repository
Go to GitHub.

Create a new repository for your project by clicking on the **New** button in the repositories section.

Name the repository and select whether it should be **Public** or **Private** (depending on whether you want others to see it).

## Push Your Project to GitHub:
On your local machine where the MkDocs project exists:

```
# Initialize Git
git init

# Add your files to the Git staging area
git add .

# Commit your changes
git commit -m "Initial commit"   

Switched to a new branch 'main'
git checkout -b main 

# Link the repository to your local directory
git remote add origin https://github.com/your-username/your-repository.git

# Push the changes to GitHub
git push -u origin main    
```
Now, your project is stored on GitHub.

## Collaborating Across Multiple Computers
On any other computer, you (or collaborators) can clone the repository and continue editing:
```
# Clone the repository:
`git clone https://github.com/your-username/your-repository.git`

# Commit and push the changes:
git add .
git commit -m "Description of changes"
git push

# Pull changes on other machines before working:
`git pull`
```
## upload (push) your changes
```
# Navigate to Your Project Directory
cd /path/to/your/project

# Check Git Status, to see which files have been modified or added, run:
git status

# Stages all changes in your working directory
git add .

# Stage specific files
git add filename

# Commit the Changes
git commit -m "Your commit message here"

# Push the Changes to GitHub
git push origin main
```
## Changes the repository name
```
git remote set-url origin [new_url]

git remote -v
```