## Coriell Bioinformatics Lessons: Practice RNA-seq Analysis

### Setup
*2020-01-07*

#### Set Up a Folder for the Project

```bash
# starting from my home directory, /home/kkeith, change to my data directory where I want to put the project directory
[kkeith]$ cd data
# make the project directory
[kkeith]$ mkdir rnaseq_practice
# switch into the project directory 
[kkeith]$ cd rnaseq_practice
# copy the data to my project directory
[kkeith]$ cp -r /mnt/data/coriell_bioinformatics_server_lessons/coriell_server_lessons/rnaseq/rnaseq_data/ ~/data/rnaseq_practice
```

#### Set Up a Git Repository

For some back up and version control, but mostly for project documention.

```bash
# start the git repository
[kkeith]$ git init
# make a README to describe the project and the directory
[kkeith]$ nano README.md
# add a .gitignore so you don't upload large files to GitHub
[kkeith]$ nano .gitignore
# add the files so GitHub will track them / add changes so they can be committed
[kkeith]$ git add .gitignore README.md
# commit the files
[kkeith]$ git commit -m 'first commit'
# add the GitHub repository as a remote
[kkeith]$ git remote add origin git@github.com:kelseykeith/test_rnaseq_practice.git
# push files to remote + this first time set the remote as the automatic place to push
[kkeith]$ git push -u origin master
```
