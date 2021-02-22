# RNA-seq to DEGs Virtual Workshop: data management, analysis, and visualization with R Studio<sup>*</sup>, GitHub, and L<sup>A</sup>T<sub>E</sub>X
#### [Workflow](https://sbresnahan.github.io/RNAseq-to-DEGs/)
##### Instructor name and contact information
- Sean Bresnahan [stb5321@psu.edu](stb5321@psu.edu)

## Registration
Workshop sessions will be held over [Zoom](https://zoom.psu.edu). [Please RSVP here](https://www.eventcreate.com/e/rnaseqtodegs) to receive an email invitation to each Zoom meeting.

## Workshop Description
Hello, fellow denizens of the universe! (Specifically, ye humans who wish to tread the roads of computational biology in some form or another.) I designed this workshop as an introduction to many interrelated topics and tools that IMO are not only essential for conducting RNA-seq and differential gene expression analyses, but are quite useful and insightful for the endeavor of learning how to take a raw, high-throughput dataset all the way from A to Z (where "A" is the sequencing machine, and "Z" is a robust and internally replicable document detailing all analyses conducted).  

Why care about this? Isn't the task of conducting such experiments and publishing manuscripts complex enough already? To answer this, I want you to consider three things:  
* The claims you'll eventually make in your manuscript should, if you're doing it right, be informed by your analyses,
* Some human(s) will need to *review* said manuscript (and thus said analyses), and,
* Some other human(s) might be very interested in the work you've done and like to learn how to conduct similar analyses themselves.  

Thus, the intent of this course is to not only learn how to use fancy tools specific to transcriptomic analyses, but to do so in the spirit of the art and science of scientific story telling. Something that has bothered me (and others... for example, [see this piece lamenting the disparity of reproducible transcriptomic analyses](https://www.nap.edu/read/25303/chapter/6)...) while learning the tools of the trade is a lack of human readable and effortlessly replicable code being made available for independent assessment/utilization/adaptation (i.e., peer review and scientific progress). I think this is a bad thing. Not only does this add an unnecessary burden to the peer review process, but it makes for a very disorganizing (and often *exuberantly frustrating*) research experience. To help reduce the number of fists shaken at the sky, curses lobbed at the RefSeq deities, and nights spent curled up over a blank terminal and a bowl of spicy udon noodles (or whatever existential crisis comfort foods you particularly enjoy), we will practice taking raw data and writing a story, that anyone can follow and reproduce should they have reason or interest to do so. So, *even if* you are wholly uninterested in (or irrationally terrified of) bioinformatics, but feel the same way about these issues, there is still something here for you.

**Important disclaimer**: I am a second year graduate student, and do not claim to be an expert in any of these subjects. But - I've spent a lot of time working out ways to make transcriptomics analyses more organized, clear, interpretable, and replicable, and am hopeful that through this workshop, we will collectively produce a pretty decent resource for others picking up these tools. If you'd like more expert-level, hyper-robust, ultra-detailed tutorials and resources on DEG analysis particularly, please see [this workflow](https://www.bioconductor.org/packages/devel/workflows/vignettes/rnaseqGene/inst/doc/rnaseqGene.html) by Michael Love et al... IMO, it doesn't get much better than this!

### Goals and objectives
* To understand the importance of data transparency and to learn practical data management practices
* To understand what GitHub is useful for in this regard, and how to use it
* To learn how to set up a computer for bioinformatic and statistical analyses in R Studio<sup>*</sup>
* To learn how to access and retrieve next generation sequencing data from [NCBI's Short Read Archive](https://www.ncbi.nlm.nih.gov/sra)
* To understand the data types and structures involved in RNA-seq and differential gene expression analyses; what sequencing reads and gene expression count matrices are, and how to work with them
* To understand differential gene expression analysis results and how to visualize them to tell a story
* To learn how to write and work with markdown documents for reproducible data analysis
* To learn how to utilize publisher-provided L<sup>A</sup>T<sub>E</sub>X typesets for formatting analyses (and our stories informed by them) for publication.

### Microsoft Teams
Throughout the workshop (and beyond!), we will use the [Microsoft Teams](https://www.microsoft.com/en-us/microsoft-teams/group-chat-software) platform as a way to network among ourselves, and as a virtual “working group” for tech support. Teams is a great alternative to Slack, which integrates Microsoft Office tools rather than Google tools. You can access Teams from the web, or download the desktop/mobile app. Ideally, we will run this workshop or a variant of it again in the future, and this Team will remain open as a permanent resource. Feel free to start using our Team for all your Q&A needs :)

#### Office hours
If you have questions or issues while following the setup instructions, I can help you 1:1 during these times:
* Monday: 9AM-5PM (EST)
* Tuesday: 9AM-12PM (EST)
* Wednesday: 9AM-5PM (EST)
* Thursday: 9-6PM (EST)
  
Just message me in Teams and I’ll try to respond ASAP!

### Timeline
This workshop will be split into four sessions, one session from 3-5pm (EST) every two weeks, running 02/23/21-04/06/21:
* **02/23/21, 3-5pm (EST)**: Initial setup and discussion about data transparency, management, and reproducibility  
   **Co-hosted by [Briana Ezray](https://twitter.com/bezray2?lang=en), Research Data Librarian - STEM, Penn State University Libraries**
* **03/09/21, 3-5pm (EST)**: RNA-seq analysis, from sequencing reads to gene expression count matrices
* **03/23/21, 3-5pm (EST)**: DEG analysis, from count matrices to DEGs (and what they're good for), and finally,
* **04/06/21, 3-5pm (EST)**: Preparing markdown and L<sup>A</sup>T<sub>E</sub>X documents for scientific communication.  

*Note: we will cover making and using markdown documents in sessions 2 and 3*    
  
Hope to see you there! :)
