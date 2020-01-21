## Coriell Bioinformatics Lessons: Practice RNA-seq Analysis

### Setup
*2020-01-07*

#### Set Up a Folder for the Project
*2020-01-07*

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
*2020-01-07*

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

### Quality Control
*2020-01-14*

#### Check Quality with FastQC
*2020-01-14*

```bash
# go to the rnaseq data
[kkeith]$ cd data/coriell_bioinformatics_lessons/rnaseq_practice/rnaseq_data
# make a folder to put the output in
[kkeith]$ mkdir fastqc
# run FastQC with a loop
[kkeith]$ for i in *.fastq.gz; do fastqc $i -o fastqc/; done
# OR FastQC will run for all fastq files if you supply the files using wildcards
[kkeith]$ fastqc *.fastq.gz -o fastqc/
```
#### Trim Adapters and Low Quality Sequences
*2020-01-14*

```bash
# still in the data directory
[kkeith]$ pwd
/home/kkeith/data/coriell_bioinformatics_lessons/rnaseq_practice/rnaseq_data
# make folders for the analysis and to put the trimmed reads in
[kkeith]$ mkdir ../analysis
[kkeith]$ mkdir ../analysis/01_trim
# trim with trim_galore
[kkeith]$ for i in *R1.fastq.gz; do trim_galore --paired --fastqc --illumina --output ../analysis/01_trim/ --retain_unpaired -q 30 $i ${i/R1/R2}; done
```
### Process Reads
*2020-01-21*

#### Align
*2020-01-21*

```bash
# go to the directory where the trimmed reads are
[kkeith]$ pwd
/home/kkeith/data/coriell_bioinformatics_lessons/rnaseq_practice/
[kkeith]$ cd analysis/01_trim
# make a new directory to put the aligned files in
[kkeith]$ mkdir ../02_analysis
# align with STAR
[kkeith]$ for i in *val_1.fq.gz; do STAR --genomeDir /mnt/data/gdata/human/hg38/chr21/STAR_index/ --readFilesIn $i ${i/R1_val_1/R2_val_2} --readFilesCommand zcat --outFileNamePrefix ../02_align/${i/R1*/} --outSAMtype BAM SortedByCoordinate; done
```
#### Count Features

```bash
# go to the directory where the aligned reads are
[kkeith]$ pwd
/home/kkeith/data/coriell_bioinformatics_lessons/rnaseq_practice/analysis/01_trim
[kkeith]$ cd ../02_align/
# make a directory to put the count tables in
[kkeith]$ mkdir ../03_count
# count the number of reads for each gene
[kkeith]$ for i in *.bam; do featureCounts -a /mnt/data/gdata/human/hg38/chr21/homo_sapiens_hg38_chr21.gtf -o ../03_count/${i/Aligned.sortedByCoord.out.bam/counts.txt} -R BAM $i; done
```















