# Binder for BVCN Comparative Genomics lesson

Initially forked from [here](https://github.com/binder-examples/conda). Thank you to the awesome [binder](https://mybinder.org/) team!

[![Binder](https://mybinder.org/badge_logo.svg)](https://gesis.mybinder.org/binder/v2/gh/astrobiomike/bvcn-binder-checkm/master?urlpath=lab)

Part of the [Bioinformatics Virtual Coordination Network](https://biovcnet.github.io/) :)


### Tutorial accompanying the bin evaluation lesson of the metagenomics topic of the BVCN
Lesson and tutorial by Daan Speth
   
**General overview**  
For this checkM tutorial, we will estimate the completeness of the genomes from [this paper](https://www.nature.com/articles/ncomms11172) which was part of my PhD thesis.  
This is not (entirely) out of vanity, but for 2 specific reasons:  
1) We retrieved a modest number of genomes (23) so the tutorial will run somewhat quickly.  
2) We did not use checkM in the paper, so have a comparison to a different completeness estimate.  


**Data retrieval**  
Note: these steps are already done, but here for completeness.
We will walk through these steps in the tutorial.  
  
First, we find the relevant accession number. NCBI studies tend to be organized in bioprojects, so that is the number you eventually want to use. 
We directly [reported it](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA274364) so it is easy to find, 
but NCBI will also make it easy to find it on each individual genome record page, such as [this one](https://www.ncbi.nlm.nih.gov/nuccore/LLZP00000000).  
  
Once you're on the bioproject page and scroll down, you see a list of assemblies associated with this Bioproject, with a "Download" link at the top right of the table.
If you click the link, this will sadly not download the assmblies. But it will download a tsv file of the table, which can be useful for othger purposes.  
Just wanted to point out this red herring I've definitely fallen for in the past...   
To actually get the assemblies, we scroll back up to the top, and click Assemblies, under "Related information". 
This will bring us [here](https://www.ncbi.nlm.nih.gov/assembly?LinkName=bioproject_assembly_all&from_uid=274364), 
where we can download all constituent assemblies using the button at the top. 
Doing so will get us the assemblies of choice as a comperessed tar file (genome_assemblies_genome_fasta.tar). This file is present in the binder.





