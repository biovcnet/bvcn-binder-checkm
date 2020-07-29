# Binder for BVCN Comparative Genomics lesson

Initially forked from [here](https://github.com/binder-examples/conda). Thank you to the awesome [binder](https://mybinder.org/) team!

[![Binder](https://mybinder.org/badge_logo.svg)](https://gesis.mybinder.org/binder/v2/gh/astrobiomike/bvcn-binder-checkm/master?urlpath=lab)

Part of the [Bioinformatics Virtual Coordination Network](https://biovcnet.github.io/) :)


### Tutorial accompanying the bin evaluation lesson of the metagenomics topic of the BVCN
Lesson and tutorial by Daan Speth
   
** General overview**
For this checkM tutorial, we will estimate the completeness of the genomes from [this paper](https://www.nature.com/articles/ncomms11172) which was part of my PhD thesis.  
This is not (entirely) out of vanity, but for 2 specific reasons:  
1) We retrieved a modest number of genomes (23) so the tutorial will run somewhat quickly.  
2) We did not use checkM in the paper, so have a comparison to a different completeness estimate.  


**Data retrieval**
Note: these steps are already done, but here for completeness.
We will walk through these steps in the tutorial.  
  
First, we find the relevant accession number. NCBI studies tend to be organized in bioprojects, so that is the number you eventually want to use. 
We directly reported it [(PRJNA274364)](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA274364), 
but NCBI will also make it easy to find it on each individual genome record page, such as [this one](https://www.ncbi.nlm.nih.gov/nuccore/LLZP00000000).




