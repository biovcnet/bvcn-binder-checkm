## Binder for BVCN bin evaluation lesson

Initially forked from [here](https://github.com/binder-examples/conda). Thank you to the awesome [binder](https://mybinder.org/) team!
  
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/biovcnet/bvcn-binder-checkm/master?urlpath=lab)
  
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
If you click the link, this will sadly not download the assmblies. But it will download a tsv file of the table, which can be useful for other purposes. 
For example, we will use it to rename our fasta files below   
   
To actually get the assemblies, we scroll back up to the top, and click Assemblies, under "Related information". 
This will bring us [here](https://www.ncbi.nlm.nih.gov/assembly?LinkName=bioproject_assembly_all&from_uid=274364), 
where we can download all constituent assemblies using the button at the top. 
Doing so will get us the assemblies of choice as a comperessed tar file (genome_assemblies_genome_fasta.tar). This file is present in the binder.
   
   
**Organization**  
We'll first unpack the top level directory:   
```tar -xvf genome_assemblies_genome_fasta.tar```
  
go into the directory and check the README:  
```cd ncbi-genomes-2020-07-28/```  
```cat README.txt```  
   
unpack the genomes and inspect:  
```gunzip *gz```
```ls -lh```  
  
Optional: rename the bins to more meaningful names:
```perl -p -i -e 's/ /_/g' ../PRJNA274364_AssemblyDetails.txt```  
```while read line ; do OLD=$(echo $line | cut -f1 -d' ') ; NEW=$(echo $line | cut -f6 -d' ') ; mv "$OLD"* "$NEW".fna ; done < ../PRJNA274364_AssemblyDetails.txt```   
  
  
**running CheckM core command**  
We'll start with a look at all the options CheckM has to offer:  
```checkm -h```

We will	not be running the preferred "lineage workflow" because	of memory limitations in the binder.  
Instead, we will run the "taxonomy workflow":  
```checkm taxon_list -h```  
```checkm taxon_list```  
  
For now we will use domain "Bacteria".  
Note: Running this command will take approximately 25 minutes   
If you don't want to wait this long, continue below  
```checkm taxonomy_wf -h```  
```checkm taxonomy_wf -t 4 -x fna -f checkm_results --tab_table domain Bacteria . checkm_out```  
    
While this is running, we will inspect a precomputed lineage workflow output directory.  
  
  
**Inspecting lineage workflow output**  
First, open a new terminal using the "+" button in the top left corner of the jupyter lab screen, just under "File".  
In this new terminal, go into the "extra info" directory, and inspect the content of the "checkm_lineage_wf_out"  
```cd extra_info```   
```ls checkm_lineage_wf_out```
