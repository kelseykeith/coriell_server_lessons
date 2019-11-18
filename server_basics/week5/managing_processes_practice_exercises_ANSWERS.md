## Answers - Managing Processes Practice Exercises

### Ansers

1. Type the command `zcat data/rrbs_chr21_f14_L001_R1_001.fastq.gz` into terminal and kill it.

Hit Ctrl + C to kill it

2. Type the command `zcat data/rrbs_chr21_f14_L001_R1_001.fastq.gz` into terminal and stop it

Hit Ctrl + Z to stop it

3. Find the process ID of the stopped command and kill it

Use either `ps` or `top` to find the process ID, then kill it.

```bash
[username]$ ps
  PID TTY          TIME CMD
16123 pts/23   00:00:00 gzip
16146 pts/23   00:00:00 ps
98235 pts/23   00:00:00 bash
[username]$ kill -9 16123
[1]+  Killed                  zcat data/rrbs_chr21_f14_L001_R1_001.fastq.gz
```