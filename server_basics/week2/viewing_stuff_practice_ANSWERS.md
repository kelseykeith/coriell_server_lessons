## ANSWERS - Viewing Stuff on the Command Line Practice Exercises

### Answers

1. List all the files and folders you see.

```bash
# could use ls
[username]$ ls
analysis  data  README.md  scripts

# Kelsey likes ll better because it shows you more information
[username]$ ll
total 16
drwxr-xr-x. 2 kkeith research 4096 Oct 28 16:16 analysis
drwxr-xr-x. 3 kkeith research 4096 Oct 28 16:16 data
-rw-r--r--. 1 kkeith research 1356 Oct 28 16:16 README.md
drwxr-xr-x. 2 kkeith research 4096 Oct 28 16:16 scripts
```

2. What are file sizes of the files and folders in the directory in bytes?

```bash
# now you have to use a flag to see the file sizes
[username]$ ll
total 16
drwxr-xr-x. 2 kkeith research 4096 Oct 28 16:16 analysis
drwxr-xr-x. 3 kkeith research 4096 Oct 28 16:16 data
-rw-r--r--. 1 kkeith research 1356 Oct 28 16:16 README.md
drwxr-xr-x. 2 kkeith research 4096 Oct 28 16:16 scripts
```
| name | folder or file? | size (bytes) |
| --- | --- | --- |
| analysis | folder | 4096 |
| data | folder | 4096 |
| README.md | file | 1356 |
| scripst | folder | 4096 |

3. Are there any hidden files?

```bash
# you have to use the -a flag to see hidden files
[username]$ ll -a
total 32
drwxr-xr-x. 5 kkeith research 4096 Oct 28 16:21 .
drwxr-xr-x. 3 kkeith research 4096 Oct 28 14:07 ..
drwxr-xr-x. 2 kkeith research 4096 Oct 28 15:40 analysis
drwxr-xr-x. 3 kkeith research 4096 Oct 28 15:43 data
-rw-r--r--. 1 kkeith research   44 Oct 28 16:21 .hidden.txt
-rw-r--r--. 1 kkeith research 1356 Oct 18 13:57 README.md
drwxr-xr-x. 2 kkeith research 4096 Oct 28 13:44 scripts
-rw-r--r--. 1 kkeith research   46 Oct 18 13:30 .surprise.txt
```
Yep, there are two named `.hidden.txt` and `.surprise.txt`!