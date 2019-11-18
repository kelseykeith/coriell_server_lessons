## Answers - I/O Operators Practice Exercises

### Answers

1. Type `echo “Hello, world”` and redirect it to a file named `hello.txt`. Use cat to view the file.

```bash
# Make the file
[username]$ echo "Hello, world" > hello.txt
# View the file
[username]$ cat hello.txt
Hello, world
```

2. Use a combination of zcat and piping to view the head of a fastq file in the data folder. What does it look like?

```bash
# Step 1: Find a fastq file by looking at what's in the data folder
[username]$ ll data
total 35048
drwxr-xr-x. 2 kkeith research    4096 Oct 28 16:25 fastqc
-rw-r--r--. 1 kkeith research 7224247 Oct 28 16:25 rrbs_chr21_f01.bam
-rw-r--r--. 1 kkeith research 2071761 Oct 28 16:25 rrbs_chr21_f01_L001_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2323 Oct 28 16:25 rrbs_chr21_f01_L001_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  315316 Oct 28 16:25 rrbs_chr21_f01_L001_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  390513 Oct 28 16:25 rrbs_chr21_f01_L001_R1_001_trimmed_fastqc.zip
-rw-r--r--. 1 kkeith research 2060448 Oct 28 16:25 rrbs_chr21_f01_L001_R1_001_trimmed.fq.gz
-rw-r--r--. 1 kkeith research 2275447 Oct 28 16:25 rrbs_chr21_f01_L002_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2312 Oct 28 16:25 rrbs_chr21_f01_L002_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  289270 Oct 28 16:25 rrbs_chr21_f01_L002_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  353468 Oct 28 16:25 rrbs_chr21_f01_L002_R1_001_trimmed_fastqc.zip
-rw-r--r--. 1 kkeith research 2263385 Oct 28 16:25 rrbs_chr21_f01_L002_R1_001_trimmed.fq.gz
-rw-r--r--. 1 kkeith research 8045749 Oct 28 16:25 rrbs_chr21_f14.bam
-rw-r--r--. 1 kkeith research 2291428 Oct 28 16:25 rrbs_chr21_f14_L001_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2353 Oct 28 16:25 rrbs_chr21_f14_L001_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  295107 Oct 28 16:25 rrbs_chr21_f14_L001_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  362232 Oct 28 16:25 rrbs_chr21_f14_L001_R1_001_trimmed_fastqc.zip
-rw-r--r--. 1 kkeith research 2277689 Oct 28 16:25 rrbs_chr21_f14_L001_R1_001_trimmed.fq.gz
-rw-r--r--. 1 kkeith research 2337532 Oct 28 16:25 rrbs_chr21_f14_L002_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research    2337 Oct 28 16:25 rrbs_chr21_f14_L002_R1_001.fastq.gz_trimming_report.txt
-rw-r--r--. 1 kkeith research  290949 Oct 28 16:25 rrbs_chr21_f14_L002_R1_001_trimmed_fastqc.html
-rw-r--r--. 1 kkeith research  357637 Oct 28 16:25 rrbs_chr21_f14_L002_R1_001_trimmed_fastqc.zip
-rw-r--r--. 1 kkeith research 2324552 Oct 28 16:25 rrbs_chr21_f14_L002_R1_001_trimmed.fq.gz

# Step 2 (optional): Confirm you have a valid file path by using ls or ll for one fastq file
[username]$ ll data/rrbs_chr21_f01_L001_R1_001.fastq.gz
-rw-r--r--. 1 kkeith research 2071761 Oct 28 16:25 data/rrbs_chr21_f01_L001_R1_001.fastq.gz

# Step 3: Look at the top of the file using zcat and head
[username]$ zcat data/rrbs_chr21_f01_L001_R1_001.fastq.gz | head
@SN930:920:HJVVWBCX2:1:1201:12794:27493_1:N:0:CCGTCC
GGATAAATTATTATTTATTATTTATTTATAAAAATTTAAAATTTTTATTATGGGAAATAAGTTTTTAATTATTATT
+
GGGGGIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIGIIIIIIIIIIIII
@SN930:920:HJVVWBCX2:1:2212:6952:6780_1:N:0:CCGTCC
AATAAAATTAATTTAGTAAAGTTGTAGGATTTAAAGTAAAGATTTAAAAAAATATAAATAGTAAATATTTTGAAAAG
+
GGGGGIIIIGIIIIIIIIIIIIIIIGIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII
@SN930:920:HJVVWBCX2:2:1205:5578:41813_1:N:0:CCGTCC
GATTTAAAGTAAAGATTTAAAAAAATATAAATAGTAAATATTTTGAAAAGGAAATTAAGAAAATAATTTATTTGTAATGG
```

3. Append something to your `hello.txt` file? Maybe a reply to its message?

```bash
# Add something using the append (>>) operator
[username]$ echo "Hello, bioinformatic server" >> hello.txt 

# check that it worked using cat or head or something
[username]$ head hello.txt 
Hello, world
Hello, bioinformatic server
```

4. What are the last 10 lines of `analysis/rrbs_chr21_f01.bismark.cov.gz`?

Notice that the file ends in `.gz`; it's gzipped, so you have to use `zcat` to look at it.

```bash
# Use zcat to open the file and tail to look at the end of it
[username]$ zcat analysis/rrbs_chr21_f01.bismark.cov.gz | tail
chr21	48118756	48118756	80	4	1
chr21	48118757	48118757	100	1	0
chr21	48118762	48118762	80	4	1
chr21	48118763	48118763	100	1	0
chr21	48118766	48118766	100	1	0
chr21	48119474	48119474	33.3333333333333	1	2
chr21	48119506	48119506	66.6666666666667	2	1
chr21	48119517	48119517	33.3333333333333	1	2
chr21	48119520	48119520	100	3	0
chr21	48119539	48119539	100	3	0
```

5. What's the highest coverage of any site in the count data in the analysis folder?

```bash
# Step 1: Look at what's in the analysis folder.
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

# Step 2: There are two files with count in the name, so look at both
[username]$ head analysis/count_data_skinny.tsv 
chr	start	end	strand	sample_id	cov	methPerc	numCs	numTs
chr21	9439220	9439220	*	f01	16	100	16	0
chr21	9439220	9439220	*	f14	10	80	8	2
chr21	9439238	9439238	*	f01	16	56.25	9	7
chr21	9439238	9439238	*	f14	10	60	6	4
chr21	9439247	9439247	*	f01	16	81.25	13	3
chr21	9439247	9439247	*	f14	10	80	8	2
chr21	9439266	9439266	*	f01	16	75	12	4
chr21	9439266	9439266	*	f14	10	70	7	3
chr21	9439283	9439283	*	f01	16	25	4	12
[username]$ head analysis/count_data_wide.tsv 
chr	start	end	strand	cov_f01	numCs_f01	numTs_f01	methPerc_f01	cov_f14	numCs_f14	numTs_f14	methPerc_f14
chr21	9439220	9439220	*	16	16	0	100	10	8	2	80
chr21	9439238	9439238	*	16	9	7	56.25	10	6	4	60
chr21	9439247	9439247	*	16	13	3	81.25	10	8	2	80
chr21	9439266	9439266	*	16	12	4	75	10	7	3	70
chr21	9439283	9439283	*	16	4	12	25	10	4	6	40
chr21	9439348	9439348	*	13	11	2	84.61538461538461	10	6	4	60
chr21	9439362	9439362	*	13	12	1	92.3076923076923	10	5	5	50
chr21	9439385	9439385	*	13	11	2	84.61538461538461	10	7	3	70
chr21	9439388	9439388	*	13	7	6	53.84615384615385	10	7	3	70

# Step 3: Since the coverage information is all in one column in the skinny count table it will be easier to sort that file. Use cut to get only the coverage column, sort to sort, and since we only need the biggest number, just print the tail to the terminal.
[kkeith]$ cut -f 6 analysis/count_data_skinny.tsv | sort | tail
98
98
98
98
99
99
99
99
99
cov
```




