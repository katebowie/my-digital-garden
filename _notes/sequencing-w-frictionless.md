---
title: Frictionless, sequencing data, and the SRA
---

### Whaddup!

*Oh hey, what's on your mind?*

I work on sequencing DNA from different communities of microbes in the human body, like the bacteria in the [[LUTS in men|bladder]]. This means that I generate a massive amount of data and it can get unruly pretty damn quickly. Unruly data means not only am I bad at organization, but it will be more difficult for me to share the data with others and it may not be reproducible 

SoOoOo luckily, [Frictionless](https://frictionlessdata.io/reproducible-research/#the-plan) has created some tools which bundle raw data, metadata, software, and whatever else all together in a datapackage, which is helpful for organization and data validation among other things. OH yeaaaah this seems fantastic! But wait no, it doesn't work with class S5 objects nor FASTA files, thus is manually intensive to upload all of those files and input the column names 😕. (I speak on a potential workaround to use the datapackage creator with microbiome sequencing data in a blogpost [here](https://fellows.frictionlessdata.io/blog/kate-datapackage-blog/), however this data is partially processed and it's definitely not a longterm solution.) 



*Now what's the big idea?*

Maybe for my fellowship with Frictionless (oh yeah, that's an important detail), I should help make their packages work with sequencing data! And to make this tool even more useful (I'm *definitely* getting ahead of myself) I should consider compatibility for uploading to public repositories. In general, to publish any of this sequencing data, most (all?) journals requires uploading the sequencing data to some public repository (most commonly the [SRA = short read archive](https://www.ncbi.nlm.nih.gov/sra/docs/submitmeta/#introduction)). So maybe if I work on this project, I should keep that in mind too... 


## Questions that I should probably address

In no particular order:

1. Has anyone thought of this?
2. File types for SRA?
3. File types for the metadata?
4. What are the barriers for frictionless and my (sequencing) data? Can these be broken down into problems, regardless of knowing the solution or not?

**Has anyone thought of this?**
--> After googling for a good 10 minutes, the short answer is no. There is a pipeline created on [CyVerse](https://learning.cyverse.org/projects/sra_submission_quickstart/en/latest/step1.html) that goes through creating a SRA "submission package", however a requirement is uploading your data to CyVerse Data Store and I'm not sure this is the same as a data package necessarily.


**Let's talk about the metadata for a second** --> When the SRA talks about metadata, they group it together as a *submission*. It looks like one SRA submission (SRA#) is made up  of these parts:

- STUDY (SRP#) 
- SAMPLE(SRS#)
- EXPERIMENT(SRX#) 
- RUN(SRR#)

Experiment and Run objects have the instrument and library information (ie illumina and  250bp paired-end). Each "experiment" is a unique sequencing result for a specific sample... *what about replicates?* well, if they're biological, then they should be separate "experiments".

A Run is essentially information that connects the data files with each experiment. !Paired-end data files must be listed together in the same run!

Data can be submitted using the SRA Portal Wizard, but also certain types are accepted from dbGAP (controlled access data) or GEO (functional gene studies). For this project, I only really care about the SRA Portal Wizard. 


**What are the file types for the SRA?**
--> Wow what a great question. The SRA is a RAW DATA archive. This is important. And the SRAs requires the quality scores for all the data submitted... which is pretty cool actually. Anyway, for my purposes, the SRA accepts FASTQ files (no FASTA since again, wants the quality score).


**So, this only gets more complicated**
--> The SRA has it's own databases that one must upload their metadata and files to, and THEN upload those to the actual SRA. Oy vey. Also just read someone's experience with github (shout out [Rachael](https://rachaellappan.github.io/SRA/)) and they mentioned if you're lucky and all set up, this process will take an entire day... ouch.s




