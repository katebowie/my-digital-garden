---
title: Frictionless, sequencing data, and the SRA
---

### Whaddup!

*Oh hey, what's on your mind?*

I work on sequencing DNA from different communities of microbes in the human body, like the bacteria in the [[LUTS in men|bladder]]. This means that I generate a massive amount of data and it can get unruly pretty damn quickly. Unruly data means not only am I bad at organization, but it will be more difficult for me to share the data with others and it may not be reproducible 

SoOoOo luckily, [Frictionless](https://frictionlessdata.io/reproducible-research/#the-plan) has created some tools which bundle raw data, metadata, software, and whatever else all together in a datapackage, which is helpful for organization and data validation among other things. OH yeaaaah this seems fantastic! But wait no, it doesn't work with class S5 objects nor FASTA files, thus is manually intensive to upload all of those files and input the column names 😕. (I speak on a potential workaround to use the datapackage creator with microbiome sequencing data in a blogpost [here](https://fellows.frictionlessdata.io/blog/kate-datapackage-blog/), however this data is partially processed and it's definitely not a longterm solution.) 



*Now what's the big idea?*

Maybe for my fellowship with Frictionless (oh yeah, that's an important detail), I should help make their packages work with sequencing data! And to make this tool even more useful (I'm *definitely* getting ahead of myself) I should consider compatibility for uploading to public repositories. In general, to publish any of this sequencing data, most (all?) journals requires uploading the sequencing data to some public repository (most commonly the SRA = short read archive). So maybe if I work on this project, I should keep that in mind too... 


## Questions that I should probably address

In no particular order:

1. Has anyone thought of this?
2. File types for SRA?
3. File types for the metadata?
4. What are the barriers for frictionless and my (sequencing) data? Can these be broken down into problems, regardless of knowing the solution or not?

**Has anyone thought of this?**
--> After googling for a good 10 minutes, the short answer is no. There is a pipeline created on [CyVerse](https://learning.cyverse.org/projects/sra_submission_quickstart/en/latest/step1.html) that goes through creating a SRA "submission package", however a requirement is uploading your data to CyVerse Data Store and I'm not sure this is the same as a data package necessarily.

**What are the file types for the SRA?**
--> Wow what a great question. 



