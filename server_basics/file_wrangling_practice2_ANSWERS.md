## Answers - File Wrangling Practice Exercises, Part 2

### Answers

1. How many lines are in the file `README.md`?

Use `wc` or `wc -l` to only get the line count.

```bash
[username]$ wc -l README.md 
52 README.md
```

2. How many comments (lines containing the R comment character '#') are there in the file `analysis/fake_rrbs_analysis.Rmd`?

You can find all the lines using `grep`, then count them using `wc`

```bash
# this is how to find all the lines with grep
[username]$ grep '#' analysis/fake_rrbs_analysis.Rmd 
## Fake RRBS Analysis
### Read in the "Data"
# get list of two chr21 files
# read file in using methylKit
#### `methylKit` Data Wrangling
# filter for greater than 10 reads and remove the top 0.5% of outliers
# combine all the samples (still a necessary step even though there's 
# only 1 "sample") into one table
#### Calculate the Percent Methylation
# get percent methylation
#### Test for Differential Methylation
# calculate differential methylation
#### Save Data and Results
### wrangle wide data
# save
#write_tsv(data_wide, 'count_data_wide.tsv')
### transform wide data into skinny data
# save
#write_tsv(data_skinny, 'count_data_skinny.tsv')
# make into a tibble to make working with it easier
# save
#rite_tsv(diff_meth, 'diff_meth.tsv')
### Visualize
#### Histograms
#ggsave('coverage_histograms.png')
#ggsave('perc_meth_histograms.png')
#### `methylKit` correlation plot
# novogene
#### Volcano Plot
### volcano plot
# get annotations/labels for volcano plot

# you can find all the lines and pipe to wc to do everything in one step
[username]$ grep '#' analysis/fake_rrbs_analysis.Rmd | wc -l
31
```

3. Check the head of `analysis/diff_meth.tsv`. Now, sort `analysis/diff_meth.tsv`. What's different and why might that be a problem?

Notice that once you do a simple sort, positions at 10Mb now come before postions at 9Mb! Linux will put everything beginning with 1 first, even if it's a longer number. Also, it won't sort chromosomes correctly; it will order chromosomes by chr1, chr10, chr11... Be careful when sorting genomic data especially!

```bash
# look at the beginning of the file
[username]$ head analysis/diff_meth.tsv 
chr	start	end	strand	pvalue	qvalue	meth.diff
chr21	9439220	9439220	*	0.13846153846153847	1	-20
chr21	9439238	9439238	*	1	1	3.75
chr21	9439247	9439247	*	1	1	-1.25
chr21	9439266	9439266	*	0.9999999999999999	1	-5
chr21	9439283	9439283	*	0.6644892864572498	1	15
chr21	9439348	9439348	*	0.34128800261523373	1	-24.615384615384613
chr21	9439362	9439362	*	0.05153199203542449	1	-42.30769230769231
chr21	9439385	9439385	*	0.6175220660346519	1	-14.615384615384613
chr21	9439388	9439388	*	0.6692690806299636	1	16.153846153846153

# look at the beginning of the file after simple sorting
[username]$ sort analysis/diff_meth.tsv | head
chr21	10371851	10371851	*	0.00790855793999385	0.4044978515602449	-46.25
chr21	10371864	10371864	*	0.0409460958670225	1	-37.5
chr21	10395370	10395370	*	0.16809151192033372	1	17.934782608695656
chr21	10395381	10395381	*	0.16809151192033372	1	17.934782608695656
chr21	10421834	10421834	*	1	1	1.6823354774863901
chr21	10421918	10421918	*	0.8241002588021316	1	-4.951690821256037
chr21	10421940	10421940	*	1	1	2.2946859903381664
chr21	10421961	10421961	*	0.25462962962962965	1	6.521739130434781
chr21	10421967	10421967	*	0.7210696988178666	1	-2.732919254658384
chr21	10491963	10491963	*	0.09760034066279681	1	12.474120082815745
```

4. Use cut to display only the chr, start, end, and two methPerc columns in `analysis/count_data_wide.tsv`.

```bash
# First, look at the file before you do anything
[kkeith]$ head analysis/count_data_wide.tsv 
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

# Now use cut to get the relevant columns (and head so you don't print the entire file)
[kkeith]$ cut -f1-3,8,12 analysis/count_data_wide.tsv | head
chr	start	end	methPerc_f01	methPerc_f14
chr21	9439220	9439220	100	80
chr21	9439238	9439238	56.25	60
chr21	9439247	9439247	81.25	80
chr21	9439266	9439266	75	70
chr21	9439283	9439283	25	40
chr21	9439348	9439348	84.61538461538461	60
chr21	9439362	9439362	92.3076923076923	50
chr21	9439385	9439385	84.61538461538461	70
chr21	9439388	9439388	53.84615384615385	70
```

5. Find all of the `ggplot()` lines in `analysis/fake_rrbs_analysis.Rmd`.

```bash
# grep for ggplot
[username]$ grep ggplot analysis/fake_rrbs_analysis.Rmd 
ggplot(data_skinny, aes(x = cov)) +
ggplot(data_skinny, aes(x = methPerc)) +
ggplot(aes(x = meth.diff, y = log_qvalue)) +
```