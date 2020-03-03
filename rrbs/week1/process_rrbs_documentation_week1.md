
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

