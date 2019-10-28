## ANSWERS - Viewing Files Practice Exercises

### Answers

1. View the beginning of the file `README.md`.

```bash
# To look at the beginning of the file, use head.
# I only looked at the first 8 lines instead of the default 10, because there was some code that didn't render well in markdown on the ninth line. It was markdown-ception
[username]$ head -n 8 README.md 
## Fake Practice Documentation File

Here's where I would normally describe the experiment! Instead, I'll describe the sample I extracted chr21 stuff from. Woonbok did reduce representation bisulfite sequencing (RRBS) for several samples from the NINDS repository here at Coriell. I took the chr21 reads and data from various files in the RRBS pipeline from the F01 sample.

### Setup

Make a directory for the analysis and subdirectories to organize the analysis with.
```

2. Read the entire `README.md` file.

You can use `more` or `less`. The last line in the files is `### Analyze Data`, so if you saw that you're good!

3. Make a new file and write something in it.

```bash
# make a new file
[username]$ touch new_file.txt

# use an editor to put something in it
[username]$ nano new_file.txt

# see what I wrote in the file
[username]$ cat new_file.txt 
Exercise complete!
```
There are many different ways to do this, so as long as you made a file with something in it, you're good!