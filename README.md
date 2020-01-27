# Coriell Bioinformatics Server Lessons

---

### Getting Started

#### Mac

1. You'll connect to the server through terminal, so you don't need to install any software. I suggest pinning terminal to the dock though. 
2. Download and install XQuartz <https://www.xquartz.org/>. This will let you view images from the server.
3. Download and install MacDown <https://macdown.uranusjr.com/>. You'll use this for documenting your work.
4. Download and install Macfusion. Follow the directions [here](how_to_install_macfusion.md).  This will let you transfer files to and from your computer and the server. This is the hardest thing to install, so if it doesn't work come ask for help!
5.  You should already have the Cisco AnyConnect VPN installed on your computer, but if you don't, follow the instructions [here](Cisco_AnyConnect_installation_instructions.pdf). This will allow you to connect to the server from outside of Coriell.
6. Install R. Go to R Cloud <https://cloud.r-project.org/> and click on "Download R for (Mac) OS X" and follow the instructions and your computer prompts.
7. Go to RStudio <https://rstudio.com/products/rstudio/download/> and download the **FREE** version for Mac, then follow the installation prompts.

#### PC

1. Download and install PuTTy <https://www.chiark.greenend.org.uk/~sgtatham/putty/>. This will let you connect to the server.
2. Download and install XMing <https://sourceforge.net/projects/xming/>. This will let you view images from the server.
3. Download and install Joplin <https://joplinapp.org/>. You'll use this for documenting your work.
4. Download and install WinSCP <https://winscp.net/eng/index.php>. This will let you transfer files to and from your computer and the server.
5. You should already have the Cisco AnyConnect VPN installed on your computer, but if you don't, follow the instructions [here](Cisco_AnyConnect_installation_instructions.pdf). This will allow you to connect to the server from outside of Coriell.
6. Install R. Go to R Cloud <https://cloud.r-project.org/> and click on "Download R for Windows" and follow the instructions and your computer prompts.
7. Go to RStudio <https://rstudio.com/products/rstudio/download/> and download the **FREE** version for Windows, then follow the installation prompts.

---

### Resources

- tmux cheatsheet <https://gist.github.com/MohamedAlaa/2961058>
- git book <https://git-scm.com/book/en/v2>
- R for Data Science <https://r4ds.had.co.nz/>

---

### Server Basics

#### Week 1 - **Terminus** - *2019-10-22*

Learn basic terminal commands by playing **Terminus** <https://web.mit.edu/mprat/Public/web/Terminus/Web/main.html>

#### Week 2 - **How to Use the Server** - *2019-10-29*

- [slides](server_basics/week2/how_to_use_the_server_week2.pdf)
- Practice Exercises
  - Command-Line Basic Navigation [Practice Exercises](server_basics/week2/viewing_stuff_practice.md), [ANSWERS](server_basics/week2/viewing_stuff_practice_ANSWERS.md)

#### Week 3 - **How to Use the Server, cont.** - *2019-11-05*

- [slides](server_basics/week3/how_to_use_the_server_week3.pdf)
- Practice Exercises
  - Viewing Files [Practice Exercises](server_basics/week3/viewing_files_practice.md), [ANSWERS](server_basics/week3/viewing_files_practice_ANSWERS.md)
  - Navigating the Filesystem [Practice Exercises](server_basics/week3/navigating_practice.md), [ANSWERS](server_basics/week3/navigating_practice_ANSWERS.md)
  - File Wrangling [Practice Exercises](server_basics/week3/file_wrangling_practice.md), [ANSWERS](server_basics/week3/file_wrangling_practice_ANSWERS.md)

#### Week 4 - **How to Use the Server, cont.** - *2019-11-12*

- [slides](server_basics/week4/how_to_use_the_server_week4.pdf)
- Practice Exercises
  - Wildcards [Practice Exercises](server_basics/week4/wildcard_practice.md), [ANSWERS](server_basics/week4/wildcard_practice_exercises_ANSWERS.md)
  - Miscellaneous [Practice Exercises](server_basics/week4/miscellaneous_practice.md), [ANSWERS](server_basics/week4/miscellaneous_practice_exercises_ANSWERS.md)
  - File Wrangling Part 2 [Practice Exercises](server_basics/week4/file_wrangling_practice2.md), [ANSWERS](server_basics/week4/file_wrangling_practice2_ANSWERS.md)

#### Week 5 - **How to Use the Server, cont.** - *2019-11-19*

- [slides](server_basics/week5/how_to_use_the_server_week5.pdf)
- Practice Exercises
  - I/O Operators [Practice Exercises](server_basics/week5/io_operators_practice.md)

#### Week 6 - **How to Use the Server, cont.** - *2019-12-03*

- [slides](server_basics/week6/how_to_use_the_server_week6.pdf)
- Practice Exercises
  - Managing Processes [Practice Exercises](server_basics/week6/managing_processes_practice_exercises.md), [ANSWERS](server_basics/week6/managing_processes_practice_exercises_ANSWERS.md)
  - Running Processes in the Background [Practice Exercises](server_basics/week6/background_processes_practice_exercises.md), [ANSWERS](server_basics/week6/background_processes_practice_exercises_ANSWERS.md)
- References
	- tmux cheatsheet <https://gist.github.com/MohamedAlaa/2961058>

##### Change the color of the bottom bar in tmux

Thanks to Himani for asking and this Stack Exchange post <https://unix.stackexchange.com/questions/60968/tmux-bottom-bar-color-change/60969>, here's how you change the color of the bottom bar in tmux.

In tmux, hit `Ctrl-B`, then type `:set status-style "bg=magenta"`. Replace magenta with another color from the list for other colors.

Possible colors: 
- black
- red
- green
- yellow
- blue
- magenta
- cyan
- white
- default

---

### Git

- [slides](git/git.pdf)
- References
	- Install git <https://git-scm.com/download>
	- git book <https://git-scm.com/book/en/v2>
	- Adding SSH keys to your GitHub account <https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh>
	- `.gitignore` <https://git-scm.com/docs/gitignore>
	- GitHub Desktop <https://desktop.github.com/>

---

### RNA-seq

#### Process RNA-seq Week1 - *2020-01-07*

Briefly went over how Illumina sequencing works and the types and structure of FastQ files. Also set up our project folders including GitHub repositories. The project documentation contains all of the commands we used today, except for where to find your SSH key, which is in the slides.

- [slides](rnaseq/week1/process_rnaseq_week1.pdf)
- [project documentation](rnaseq/week1/project_documentation.md)

#### Process RNA-seq Week2 - *2020-01-14*

Went over the FastQC program and it's output report and why we trim reads. Ran FastQC and trimming. Will go over results of trimming next week. All commands used today are in both the slides and the project documentation.

- [slides](rnaseq/week2/process_rnaseq_week2.pdf)
- [project documentation](rnaseq/week2/project_documentation.md)

#### Process RNA-seq Week3 - *2020-01-21*

Went over aligning reads and counting features. All the commands used today are in the slides and the project documentation.

- [slides](rnaseq/week3/process_rnaseq_week3.pdf)
- [project documentation](rnaseq/week3/project_documentation.md)

#### Differential Expression - *2020-01-28*

- differential expression demo [Rmd](rnaseq/week4/diff_exp_w_DESeq2.Rmd), [html](rnaseq/week4/diff_exp_w_DESeq2.html)
- References
  - `DESeq2` [Vignette](https://bioconductor.org/packages/release/workflows/vignettes/rnaseqGene/inst/doc/rnaseqGene.html)
- Packages Used
  - [tidyverse](https://cran.r-project.org/web/packages/tidyverse/index.html)
  - [conflicted](https://cran.r-project.org/web/packages/conflicted/index.html)
  - [vroom](https://cran.r-project.org/web/packages/vroom/index.html)
  - [BiocManager](https://www.bioconductor.org/install/)
  - [DESeq2](http://bioconductor.org/packages/release/bioc/html/DESeq2.html)
  - [fastcluster](https://cran.r-project.org/web/packages/fastcluster/index.html)
  - [ggdendro](https://cran.r-project.org/web/packages/ggdendro/index.html)
  - [AnnotationDbi](https://bioconductor.org/packages/release/bioc/html/AnnotationDbi.html)
  - [org.Hs.eg.db](http://bioconductor.org/packages/release/data/annotation/html/org.Hs.eg.db.html)
