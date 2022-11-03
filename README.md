Requirements:

MkDocs is installed

## Setup mkDocs Project

[Getting Started with MkDocs](https://www.mkdocs.org/getting-started/)

C:\Users\Riley>cd Desktop

C:\Users\Riley\Desktop>mkdocs new LinuxMkDocs
INFO     -  Creating project directory: LinuxMkDocs
INFO     -  Writing config file: LinuxMkDocs\mkdocs.yml
INFO     -  Writing initial docs: LinuxMkDocs\docs\index.md

C:\Users\Riley\Desktop>cd LinuxMkDocs

C:\Users\Riley\Desktop\LinuxMkDocs>echo > README.txt

C:\Users\Riley\Desktop\LinuxMkDocs> mkdocs serve

Open:

http://127.0.0.1:8000/

## Build mkDocs Project

```bash
mkdocs build
```

## Setup GitHub repo for project pages





## Git push to main

```bash
git init

git add * 

git commit -m "commit message"

git branch -M main

git remote add origin https://github.com/rileyalbiston/docs-linux-notes.git

git push -u origin main
```




## Git deploy mkdocs via gh-deploy

[mkDocs Deploying your docs](https://www.mkdocs.org/user-guide/deploying-your-docs/)

```bash
mkdocs gh-deploy
```









