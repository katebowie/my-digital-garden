---
title: Frictionless, sequencing data, and the SRA
---

### Whaddup!

*Oh hey, what's on your mind?*

I work on sequencing DNA from different communities of microbes in the human body, like the bacteria in the [[LUTS in men|bladder]]. This means that I generate a massive amount of data and it can get unruly pretty damn quickly. Unruly data means not only am I bad at organization, but it will be more difficult for me to share the data with others and have it be actually reproducible. 

SoOoOo here comes Frictionless with some tools to help bundle raw data, metadata, software, whatever else all together in a datapackage. Omg how great! **But NO**, it doesn't work with class 5 R objects nor FASTA files😕. 


*Now what's the big idea?*

Maybe for my fellowship with Frictionless (oh yeah, that's an important detail), I should help make their packages work with sequencing data! Also to publish any of this sequencing data, that requires uploading the sequencing data to some public repository (most commonly the SRA = short read archive). So maybe if I work on this project, I should keep that in mind too... 


## Questions that I should probably address:

1. Has anyone thought of this?
2. File types for SRA?
3. File types for the metadata?
4. What are the barriers for frictionless and my (sequencing) data? Can these be broken down into problems, regardless of knowing the solution or not?



