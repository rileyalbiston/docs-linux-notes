Link to page:

https://www.rileyalbiston.com/docs-linux-notes/

Link to this repo:

https://github.com/rileyalbiston/docs-linux-notes/

Requirements:

Python 3

MkDocs is installed

## Setup mkDocs Project

[Getting Started with MkDocs](https://www.mkdocs.org/getting-started/)
```bash
cd Desktop
mkdocs new docs-linux-notes
cd docs-linux-notes
echo > README.txt
mkdocs serve
```
Open:

http://127.0.0.1:8000/

## Build mkDocs Project

```bash
mkdocs build
```

## Setup GitHub repo for project pages

<Add notes on setting up the repo on GitHub and creating the gh-pages branch>

Initial push to the new repo:

```bash
git init
git add * 
git commit -m "commit message"
git branch -M main
git remote add origin https://github.com/rileyalbiston/docs-linux-notes.git
git push -u origin main
```

## Git push to main

```bash
git add * 
git commit -m "commit message"
git push -u origin main
```


## Git deploy mkdocs via gh-deploy

[mkDocs Deploying your docs](https://www.mkdocs.org/user-guide/deploying-your-docs/)

```bash
mkdocs gh-deploy
```









