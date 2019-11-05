## ANSWERS - File Wrangling Practice Exercises

### Answers

1. Make a file called `practice_file.txt`. Now put a copy of `practice_file.txt` in scripts.

```bash
# make the file with touch; there are other options like nano
[username]$ touch practice_file.txt

# put a copy in scripts
[username]$ cp practice_file.txt scripts/
[username]$ ll scripts/
total 4
-rw-r--r--. 1 kkeith research 20 Oct 28 16:25 hello_world.sh
-rw-r--r--. 1 kkeith research  0 Oct 28 16:58 practice_file.txt
```

2. `practice_file.txt` doesn't belong in scripts. Move it to the analysis folder

```bash
# use mv to move the file; you can see its now in analysis and has disappeared from scripts
[username]$ mv scripts/practice_file.txt analysis/
[username]$ ll analysis/
total 2728
-rw-r--r--. 1 kkeith research 709860 Oct 28 16:25 count_data_skinny.tsv
-rw-r--r--. 1 kkeith research 461929 Oct 28 16:25 count_data_wide.tsv
-rw-r--r--. 1 kkeith research 125793 Oct 28 16:25 coverage_histograms.png
-rw-r--r--. 1 kkeith research 383996 Oct 28 16:25 diff_meth.tsv
-rw-r--r--. 1 kkeith research   4883 Oct 28 16:25 fake_rrbs_analysis.Rmd
-rw-r--r--. 1 kkeith research  47924 Oct 28 16:25 methylkit_corr_plot.png
-rw-r--r--. 1 kkeith research 129789 Oct 28 16:25 perc_meth_histograms.png
-rw-r--r--. 1 kkeith research      0 Oct 28 16:58 practice_file.txt
-rw-r--r--. 1 kkeith research 344513 Oct 28 16:25 rrbs_chr21_f01.bismark.cov.gz
-rw-r--r--. 1 kkeith research 413401 Oct 28 16:25 rrbs_chr21_f14.bismark.cov.gz
-rw-r--r--. 1 kkeith research 153209 Oct 28 16:25 volc_plot.png
[username]$ ll scripts/
total 4
-rw-r--r--. 1 kkeith research 20 Oct 28 16:25 hello_world.sh
```

3. It doesn't really belong in the analysis folder either. Make a new directory named `practice` to put `practice_file.txt` in and move it there.

```bash
# use mkdir to make a new directory
[username]$ mkdir practice
[username]$ ll
total 24
drwxr-xr-x. 2 kkeith research 4096 Oct 28 16:59 analysis
drwxr-xr-x. 3 kkeith research 4096 Oct 28 16:25 data
-rw-r--r--. 1 kkeith research   19 Oct 28 16:35 new_file.txt
drwxr-xr-x. 2 kkeith research 4096 Oct 28 17:00 practice
-rw-r--r--. 1 kkeith research    0 Oct 28 16:57 practice_file.txt
-rw-r--r--. 1 kkeith research 1356 Oct 28 16:25 README.md
drwxr-xr-x. 2 kkeith research 4096 Oct 28 16:59 scripts

# move practice.txt from analysis to practice
[username]$ mv analysis/practice_file.txt practice
[username]$ ll analysis/
total 2728
-rw-r--r--. 1 kkeith research 709860 Oct 28 16:25 count_data_skinny.tsv
-rw-r--r--. 1 kkeith research 461929 Oct 28 16:25 count_data_wide.tsv
-rw-r--r--. 1 kkeith research 125793 Oct 28 16:25 coverage_histograms.png
-rw-r--r--. 1 kkeith research 383996 Oct 28 16:25 diff_meth.tsv
-rw-r--r--. 1 kkeith research   4883 Oct 28 16:25 fake_rrbs_analysis.Rmd
-rw-r--r--. 1 kkeith research  47924 Oct 28 16:25 methylkit_corr_plot.png
-rw-r--r--. 1 kkeith research 129789 Oct 28 16:25 perc_meth_histograms.png
-rw-r--r--. 1 kkeith research 344513 Oct 28 16:25 rrbs_chr21_f01.bismark.cov.gz
-rw-r--r--. 1 kkeith research 413401 Oct 28 16:25 rrbs_chr21_f14.bismark.cov.gz
-rw-r--r--. 1 kkeith research 153209 Oct 28 16:25 volc_plot.png
[username]$ ll practice
total 0
-rw-r--r--. 1 kkeith research 0 Oct 28 16:58 practice_file.txt
```

4. Change the permissions on the folder so only you have access to it.

```bash
# take read and execute permission away from other (non-group) users
[username]$ chmod o-rx practice
# take read and execute permission away from other group users
[username]$ chmod g-rx practice
# now you can see that you (the owner) are the only user with permissions to do anything
[username]$ ll
total 24
drwxr-xr-x. 2 kkeith research 4096 Oct 28 17:01 analysis
drwxr-xr-x. 3 kkeith research 4096 Oct 28 16:25 data
-rw-r--r--. 1 kkeith research   19 Oct 28 16:35 new_file.txt
drwx------. 2 kkeith research 4096 Oct 28 17:01 practice
-rw-r--r--. 1 kkeith research    0 Oct 28 16:57 practice_file.txt
-rw-r--r--. 1 kkeith research 1356 Oct 28 16:25 README.md
drwxr-xr-x. 2 kkeith research 4096 Oct 28 16:59 scripts
```

5. These files were just for practice, so we don't need to keep them. Remove `practice_file.txt` and `practice`.

```bash
# you can do it in two steps where you remove the file and then the folder
[username]$ rm practice/practice_file.txt
[username]$ rmdir practice

# or you can do it in one step with remove recursive, rm -r
[username]$ rm -r practice/
rm: remove 1 argument recursively? y
[username]$ ll
total 20
drwxr-xr-x. 2 kkeith research 4096 Oct 28 17:01 analysis
drwxr-xr-x. 3 kkeith research 4096 Oct 28 16:25 data
-rw-r--r--. 1 kkeith research   19 Oct 28 16:35 new_file.txt
-rw-r--r--. 1 kkeith research    0 Oct 28 16:57 practice_file.txt
-rw-r--r--. 1 kkeith research 1356 Oct 28 16:25 README.md
drwxr-xr-x. 2 kkeith research 4096 Oct 28 16:59 scripts
```