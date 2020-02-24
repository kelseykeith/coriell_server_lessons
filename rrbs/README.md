
## Process Bisulfite Sequencing (BS-Seq) Data

### Get the Data

Navigate to wherever you put your practice directories for lessons and copy the code below to grab the data and code for this practice RRBS run.

```bash
cp -r /home/kkeith/data/coriell_bioinformatics_lessons/rrbs ./
```

### Test Run

#### Check Quality with FastQC

```bash
# from RRBS data folder
[kkeith]$ mkdir fastqc
[kkeith]$ fastqc *.fq.gz -o fastqc
```

#### Trim

```bash
# from data directory
[kkeith]$ mkdir ../01_trim
[kkeith]$ for i in *1.fq.gz; do trim_galore --rrbs --paired --fastqc -q 30 --illumina --output ../01_trim $i ${i/1.fq.gz/2.fq.gz}; done
```

#### Align

```bash
# from the RRBS data directory
[kkeith]$ cd ../01_trim/
[kkeith]$ mkdir ../02_align
[kkeith]$ for i in *1_val_1.fq.gz; do bismark --bowtie2 /mnt/data/data_jj/jj4/rrbs/tools/genomes/hg19lambda/ --output ../02_align -1 $i -2 ${i/1_val_1.fq.gz/2_val_2.fq.gz}; done
```

#### Extract Methylation

```bash
# from trim directory
[kkeith]$ cd ../02_align/
[kkeith]$ mkdir ../03_extract_meth
[kkeith]$ for i in *.bam; do bismark_methylation_extractor --paired-end --include-overlap --bedGraph --output ../03_extract_meth $i; done
```













