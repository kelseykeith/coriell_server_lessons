## Answers - Miscellaneous Practice Exercises

### Answers

1. Print your history. What were your last five commands?

These should look slightly different for everyone, but the command is the same. Your history command will always be the last command typed!

```bash
# Use tail to only print the last 5 commands
[username]$ history | tail -n 5
 1031  cut -f 6 analysis/count_data_skinny.tsv 
 1032  cut -f 6 analysis/count_data_skinny.tsv | head
 1033  cut -f 6 analysis/count_data_skinny.tsv | sort | head
 1034  cut -f 6 analysis/count_data_skinny.tsv | sort | tail
 1035  "Hello, bioinformatic server" >> hello.txt 
 1036  history | tail -n 5
```

2. List all of the files in the fastqc directory in the data directory. Remember, you can use **tab** to complete the folder names so you don't have to type them all the way!

```bash
[username]$ ll data/fastqc/
total 2656
-rw-r--r--. 1 kkeith research 319361 Oct 28 16:25 rrbs_chr21_f01_L001_R1_001_fastqc.html
-rw-r--r--. 1 kkeith research 395168 Oct 28 16:25 rrbs_chr21_f01_L001_R1_001_fastqc.zip
-rw-r--r--. 1 kkeith research 295553 Oct 28 16:25 rrbs_chr21_f01_L002_R1_001_fastqc.html
-rw-r--r--. 1 kkeith research 362976 Oct 28 16:25 rrbs_chr21_f01_L002_R1_001_fastqc.zip
-rw-r--r--. 1 kkeith research 303669 Oct 28 16:25 rrbs_chr21_f14_L001_R1_001_fastqc.html
-rw-r--r--. 1 kkeith research 375182 Oct 28 16:25 rrbs_chr21_f14_L001_R1_001_fastqc.zip
-rw-r--r--. 1 kkeith research 293092 Oct 28 16:25 rrbs_chr21_f14_L002_R1_001_fastqc.html
-rw-r--r--. 1 kkeith research 360216 Oct 28 16:25 rrbs_chr21_f14_L002_R1_001_fastqc.zip
```

3. Clear your screen. Hit the up arrow until you get back to your history command and run it again. Now what are your last five commands?

```bash
[username]$ history | tail -n 5
 1002  history
 1003  ll
 1004  ll data/fastqc/
 1005  history | grep -n 5
 1006  history | tail -n 5
```