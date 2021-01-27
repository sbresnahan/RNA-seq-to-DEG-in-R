# RNA-seq to DEGs Virtual Workshop: data management, analysis, and visualization with R Studio<sup>*</sup>, GitHub, and L<sup>A</sup>T<sub>E</sub>X
##### Instructor name and contact information
- Sean Bresnahan [stb5321@psu.edu](stb5321@psu.edu)

##### [>\*Access the workshop markdown here\*<](link)

## Workshop Description
Hello, fellow denizens of the universe! (Specifically, ye humans who wish to tread the roads of computational biology in some form or another.) I designed this workshop as an introduction to many interrelated topics and tools that IMO are not only essential for conducting RNA-seq and differential gene expression analyses, but are quite useful and insightful for the endeavor of learning how to take a raw, high-throughput dataset all the way from A to Z (where "A" is the sequencing machine, and "Z" is a robust and internally replicable document detailing all analyses conducted).  

Why care about this? Isn't the task of conducting such experiments and publishing manuscripts complex enough already? To answer this, I want you to consider three things:  
* The claims you'll eventually make in your manuscript should, if you're doing it right, be informed by your analyses,
* Some human(s) will need to *review* said manuscript (and thus said analyses), and,
* Some other human(s) might be very interested in the work you've done and like to learn how to conduct similar analyses themselves.  

Thus, the intent of this course is to not only learn how to use fancy tools specific to transcriptomic analyses, but to do so in the spirit of the art and science of scientific story telling. Something that has bothered me (and others... for example, [see this piece lamenting the disparity of reproducible transcriptomic analyses](https://www.nap.edu/read/25303/chapter/6)...) while learning the tools of the trade is a lack of human readable and effortlessly replicable code being made available for independent assessment/utilization/adaptation (i.e., peer review and scientific progress). I think this is a bad thing. Not only does this add an unnecessary burden to the peer review process, but it makes for a very disorganizing (and often *exuberantly frustrating*) research experience. To help reduce the number of fists shaken at the sky, curses lobbed at the RefSeq deities, and nights spent curled up over a blank terminal and a bowl of spicy udon noodles (or whatever existential crisis comfort foods you particularly enjoy), we will practice taking raw data and writing a story, that anyone can follow and reproduce should they have reason or interest to do so. So, *even if* you are wholly uninterested in (or irrationally terrified of) bioinformatics, but feel the same way about these issues, there is still something here for you.

### Goals and objectives
* To understand the importance of data transparency and to learn practical data management practices
* To understand what GitHub is useful for in this regard, and how to use it
* To learn how to set up a computer for bioinformatic and statistical analyses in R Studio<sup>*</sup>
* To learn how to access and retrieve next generation sequencing data from [NCBI's Short Read Archive](https://www.ncbi.nlm.nih.gov/sra)
* To understand the data types and structures involved in RNA-seq and differential gene expression analyses; what sequencing reads and gene expression count matrices are, and how to work with them
* To understand differential gene expression analysis results and how to visualize them to tell a story
* To learn how to write and work with markdown documents for reproducible data analysis
* To learn how to utilize publisher-provided L<sup>A</sup>T<sup>E</sup>X typesets for formatting analyses (and our stories informed by them) for publication.

### Timeline
TBD! Development of this workshop is currently ongoing (and the instructor is somewhat - or wholly - naive to instructing many others on this subject), so this is a learning process for me as well. Ultimately, my intent is that this course be entirely standalone, such that you, dear denizen of the universe, can follow it at your own pace from start to finish, without a single helping hand. For a first "in-person" run, per initial feedback, the virtual workshop will be split into four sessions, as follows:
* Initial setup and discussion about data transparency, management, and reproducibility,
* RNA-seq analysis, from sequencing reads to gene expression count matrices
* DEG analysis, from count matrices to DEGs (and what they're good for), and finally,
* Preparing markdown and L<sup>A</sup>T<sub>E</sub>X documents for scientific communication.  

*Note: we will cover making and using markdown documents in sessions 2 and 3*  

In order to ensure a more-the-merrier situation, to RSVP for the workshop, [please fill out this form](http://whenisgood.net/rnaseqdegspsuworkshop) letting me know your availability during the week. **I will announce dates and times for these sessions by 2/1/21**.

## Getting Started
\* = alright, I hate to tell you this, but, no matter how hard you try to avoid it you *will* need to set a few things up in bash (if using a Mac, you can work in bash via Terminal). The algorithms used to align NGS reads to a reference genome are simply too resource intensive to implement in R directly, and many excellent command line tools are readily available to download and install. To make things easier for us, we will use a package management system (Conda) which will effectively reduce the number of opportunities for Murphy's law to manifest. The second half of this workshop covers the world of R Markdown, wherein bash code chunks can be written and run while knitting the markdown document. Therefore it *is* technically possible to complete the entirety of RNA-seq and DEG analysis within R... *once you know things will run smoothly in bash :)* More on this later...
### Conda
[Download an installer for Miniconda here.](https://docs.conda.io/en/latest/miniconda.html) Follow the instructions, then open a Terminal window once installation completes.

First, we need to create a Conda "environment" in which to install a few bioinformatics tools. In Terminal:

```
conda create -n bioinformatics
```

Each time you open a new Terminal window, it is operating within a base environment called `.bash_profile`. We want to work within our new bioinformatics Conda environment:

```
conda activate bioinformatics
```

Next, we can install half of the tools we need directly through Conda. These tools are called [**samtools**](http://www.htslib.org) and [**bedtools**](https://bedtools.readthedocs.io/en/latest/), suites of programs for interacting with high-throughput sequencing data and for conducting operations on genomic intervals. We won't use them directly in this workshop, but they are often prerequisite for other bioinformatics tools. To install these tools into our Conda environment:

```
conda install samtools

conda install bedtools
```

### Command line tools
Additionally, we will install [**trim_galore**](https://www.bioinformatics.babraham.ac.uk/projects/trim_galore/), and [**kallisto**](https://pachterlab.github.io/kallisto/). Trim_galore is a wrapper program around [**cutadapt**](https://cutadapt.readthedocs.io/en/stable/) - which is used to trim sequencing adapters from sequencing reads (more on this later) - and [**FastQC**](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/) - which creates reports detailing quality control metrics of the sequencing reads (more on this later, too). Kallisto is the tool we will use to generate transcript abundance estimates for calculating gene expression. To install trim_galore and kallisto, follow each link (above) and associated download and install instructions.

### R Studio
The reason you're here! [Download an installer for R Studio here.](https://rstudio.com/products/rstudio/download/) Follow the instructions and open once installation completes.

### GitHub
The entire workshop is contained within this GitHub repository. Why GitHub? Because it is a highly supported and accessible code hosting platform for version control and collaboration. Whether you eventually decide to stick with GitHub or explore some other platform, you will quickly find that in NGS data analysis, transparency and accessibility of code is critical, both for you as the analyst as well as the scientific community, who should be able to understand your documentation and reproduce your work.

#### Linking GitHub to R Studio
Throughout this workshop, we will utilize the files in and simple directory structure of this repository. Thankfully, the folks at R Studio and GitHub at some point got smart and joined forces; after setting up a GitHub account and creating a repository, individual repositories can be synced to R Studio, allowing one to "commit" new changes (e.g. to your code, to files related to or produced by your code) to the repository for effective version control. (*To learn more about using GitHub and interfacing with R Studio, [see this excellent guide](https://happygitwithr.com).*)

First, [create a GitHub account.](https://github.com/join)

Next, go back to Terminal and [install Git.](https://happygitwithr.com/install-git.html#install-git) You can do this through installing **Xcode command line tools**:

```
xcode-select --install
```

Then, open R Studio and install the [usethis](https://usethis.r-lib.org) package to set your GitHub user name and email from within R:

```
install.packages("usethis")

usethis::use_git_config(user.name = "Jane Doe", user.email = "jane@example.org")
```

Finally, download and enter the [RNA-seq-to-DEG-in-R](https://github.com/sbresnahan/RNA-seq-to-DEG-in-R.git) repository within R Studio:

```
usethis::use_course("https://github.com/sbresnahan/RNA-seq-to-DEG-in-R/archive/main.zip")

setwd('some directory')
```

The R Console will prompt `Downloading into 'some directory'` and ask whether you prefer a different location. Provide an alternative install directory or select `3` to continue. Just remember to keep track of the install directory as it is necessary to set R Studio's working directory to it in order to initialize the pipeline.
