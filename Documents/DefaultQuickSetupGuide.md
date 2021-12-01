
# GitHub Quick Setup Guide 

Note : Below is one for HTTPS and SSH url example for below Instructions.
- HTTPS = ```https://github.com/hpngithub/Users-admin-Documents-GitHub.git```

- SSH = ```git@github.com:hpngithub/Users-admin-Documents-GitHub.git```

### Create New Repo Instructions
#### HTTPS : create a new repository on the command line
```bash
echo "# Users-admin-Documents-GitHub" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/hpngithub/Users-admin-Documents-GitHub.git
git push -u origin main
```

#### SSH: create a new repository on the command line
```bash
echo "# Users-admin-Documents-GitHub" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:hpngithub/Users-admin-Documents-GitHub.git
git push -u origin main
```
### Push to Exsting Repo Instructions
#### HTTPS : push an existing repository from the command line
```bash
git remote add origin https://github.com/hpngithub/Users-admin-Documents-GitHub.git
git branch -M main
git push -u origin main
```
#### SSH : push an existing repository from the command line
```bash
git remote add origin git remote add origin git@github.com:hpngithub/Users-admin-Documents-GitHub.git
git branch -M main
git push -u origin main
```
### Import Code Instructions
#### HTTPS : You can initialize this repository with code from a Subversion, Mercurial, or TFS project.
[![Import code]()](https://github.com/hpngithub/Users-admin-Documents-GitHub/import)


