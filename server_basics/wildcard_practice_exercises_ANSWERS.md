## Answers - Wildcard Practice Exercises

### Answers

1. List all the fastq files (contain `.fastq.` in the filename) in the data directory.

Use `ll` and the anything wilcard `*`

```bash
ll data/*fastq*
-rw-r--r--. 1 kkeith research 2071761 Oct 28 16:25 data/rrbs_chr21_f01_L001_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2323 Oct 28 16:25 data/rrbs_chr21_f01_L001_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  315316 Oct 28 16:25 data/rrbs_chr21_f01_L001_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  390513 Oct 28 16:25 data/rrbs_chr21_f01_L001_R1_001_trimmed_fastqc.zip
-rw-r--r--. 1 kkeith research 2275447 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2312 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  289270 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  353468 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001_trimmed_fastqc.zip
-rw-r--r--. 1 kkeith research 2291428 Oct 28 16:25 data/rrbs_chr21_f14_L001_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2353 Oct 28 16:25 data/rrbs_chr21_f14_L001_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  295107 Oct 28 16:25 data/rrbs_chr21_f14_L001_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  362232 Oct 28 16:25 data/rrbs_chr21_f14_L001_R1_001_trimmed_fastqc.zip
-rw-r--r--. 1 kkeith research 2337532 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2337 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  290949 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  357637 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001_trimmed_fastqc.zip

data/fastqc:
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

2. List all the fastq files from Lane 2.

```bash
[username]$ ll data/*L002*fastq*
-rw-r--r--. 1 kkeith research 2275447 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2312 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  289270 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  353468 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001_trimmed_fastqc.zip
-rw-r--r--. 1 kkeith research 2337532 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2337 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  290949 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  357637 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001_trimmed_fastqc.zip
```

3. List all the gzipped files (files ending in `.gz`) in the practice directory

```bash
# Use * to represent any folder and *.gz for any gzipped file
[username]$ ll */*.gz
-rw-r--r--. 1 kkeith research  344513 Oct 28 16:25 analysis/rrbs_chr21_f01.bismark.cov.gz
-rw-r--r--. 1 kkeith research  413401 Oct 28 16:25 analysis/rrbs_chr21_f14.bismark.cov.gz
-rw-r--r--. 1 kkeith research 2071761 Oct 28 16:25 data/rrbs_chr21_f01_L001_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research 2060448 Oct 28 16:25 data/rrbs_chr21_f01_L001_R1_001_trimmed.fq.gz
-rw-r--r--. 1 kkeith research 2275447 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research 2263385 Oct 28 16:25 data/rrbs_chr21_f01_L002_R1_001_trimmed.fq.gz
-rw-r--r--. 1 kkeith research 2291428 Oct 28 16:25 data/rrbs_chr21_f14_L001_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research 2277689 Oct 28 16:25 data/rrbs_chr21_f14_L001_R1_001_trimmed.fq.gz
-rw-r--r--. 1 kkeith research 2337532 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research 2324552 Oct 28 16:25 data/rrbs_chr21_f14_L002_R1_001_trimmed.fq.gz
```