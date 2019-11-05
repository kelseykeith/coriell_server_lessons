## Navigating the Filesystem Practice Exercises

### Getting Started

1. Log onto the server
2. Paste the following command into your terminal window. Make sure you don't include the backticks! `cd ~/data/practice_directory/`

### Questions

1. What's your working directory?

```bash
# You need to print your working directory
[username]$ pwd
/home/username/data/practice_directory
```
Yours will have your username instead of Kelsey's username though!

2. Change into the `data/` directory. From there change into the `fastqc/` directory.

```bash
# change into the data directory
[username]$ cd data

# change into the fastqc directory
[username]$ cd fastqc
```

3. Get back to your working directory from question 1.

```bash
# use the .. shortcut to go up two directories
[username]$ cd ../..
[username]$ pwd
/home/username/data/practice_directory

# or you can do it two steps
[username]$ cd ..
[username]$ cd ..
[username]$ pwd
/home/username/data/practice_directory
```

4. Go to your home directory. What's it's absolute path?

```bash
# use the ~ shortcut to go to your home directory
[username]$ cd ~
# user pwd to get the absolute folder path
[username]$ pwd
/home/username
```
Yours will have your username instead of username though!

5. Now find the practice directory you were working in. What's it's absolute path? What's it's relative path from your home directory?

The absolute path is `/home/username/data/practice_directory` and the relative path is `data/practice_directory`. You can find them using combinations of `ls` and `pwd`.