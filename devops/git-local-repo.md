
### Initialize a Local Repository
```
git config --global user.name "My Name"
git config --global user.email name@surname.com
```
```
mkdir gitlearning
cd gitlearning

git init
```
### Clone a remote repository

### Working with local repository
#### Create
```
echo "Repository hosting documentation for learning" > README.md
```
#### Stage
```
git add README.md
```
#### Commit 
```
git commit -m "Added README"
```

## Branching
### Create a local branch
```
git checkout -b feature/a
```
Add a file here or make changes to an existing file
### Add and Commit
```
git add README.md
git commit -m "Spelling corrections"
```
### Merge a local branch to main branch
```
git checkout master
git merge feature/a master
```
