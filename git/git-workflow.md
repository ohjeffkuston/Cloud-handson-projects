## Acknowledgments

Nintendo Switch Sports was played heavily in between completing Terraform labs.

### Git Workflow

```bash
# update local repo
git pull
```
```bash
# display the state of the working directory and the staging area
git status
```
```bash
# create/checkout new branch
git checkout -b <new branch name>
git status
```
```bash
# adds a change in the working directory to the staging area
git add .
git status
```
```bash
# captures a snapshot of the project's currently staged changes
git commit -m "comments go here"
git status
```
```bash
# push branch to origin
git push origin <new branch name>
git status
```
# AFTER MERGE
```bash
# switch to the main branch and update local repo
git checkout main
git pull
git branch --delete <branchname>
```