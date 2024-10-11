# share and collaborate on your MkDocs project using GitHub.
## Create a GitHub Repository

Go to GitHub.

Create a new repository for your MkDocs project by clicking on the **New** button in the repositories section.
Name the repository and select whether it should be **Public** or **Private** (depending on whether you want others to see it).

## Push Your MkDocs Project to GitHub
On your local machine where the MkDocs project exists:

Initialize Git if you haven’t already:

`git init`

Add your files to the Git staging area:

`git add .`

Commit your changes:

`git commit -m "Initial commit"`

Link the repository to your local directory:

`git remote add origin https://github.com/your-username/your-repository.git`

Push the changes to GitHub:

`git push -u origin main`

Now, your MkDocs project is stored on GitHub.

## Collaborating Across Multiple Computers
On any other computer, you (or collaborators) can clone the repository and continue editing:

Clone the repository:

`git clone https://github.com/your-username/your-repository.git`

Commit and push the changes:

```
git add .
git commit -m "Description of changes"
git push
```
Pull changes on other machines before working:

`git pull`

## Enable GitHub Pages for Hosting MkDocs
After pushing your MkDocs project to GitHub, install the MkDocs GitHub Pages plugin:

`pip install mkdocs-material mkdocs-git-revision-date-localized-plugin`

Add this to your *mkdocs.yml* file:
```
plugins:
  - search
  - git-revision-date-localized
```

Deploy your site:

`mkdocs gh-deploy`

## upload (push) your changes

 Navigate to Your Project Directory

`cd /path/to/your/project`

Check Git Status
To see which files have been modified or added, run:

`git status`

Stage the Changes

`git add .`

This stages all changes in your working directory. If you want to stage specific files, you can specify them like this:

`git add filename`

Commit the Changes

`git commit -m "Your commit message here"`

Push the Changes to GitHub

`git push origin main`

## changes the repository name

`git remote set-url origin [new_url]`

`git remote -v`