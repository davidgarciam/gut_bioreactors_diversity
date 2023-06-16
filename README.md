# Meta-analysis of the microbial diversity cultured in bioreactors simulating the gut microbiome

This repository contains all the code needed to reproduce the results shown in the paper: *"Meta-analysis of the microbial diversity cultured in bioreactors simulating the gut microbiome: another key to unlocking the microbial dark matter"*

## Description: 

  * *0_Install_packages.Rmd*: Installs all the packages required for subsequent analyses.
  * *1_Metadata_retrieve.Rmd*: Explores the .xml files stored in the folder xmlFiles that were used during the search in the NCBI Sequence Read Archive (SRA)
  * *2_Download_sequences.Rmd*: Downloads the raw sequencing data from the NCBI and organize it into individual folder for each selected study. It uses the commands in the files *2_Download_raw_data.sh* and *2_tidy_all.sh*.
  * *3_Bioinformatic.Rmd*: Uses *dada2* to obtain Amplicon Sequences Variants (ASVs) from all the selected projects.
  * *4_Taxonomy.Rmd*: Uses *dada2* and *BLAST* to obtain the taxonomy of the ASVs.
  * *5_Create_phyloseq_objects.Rmd*: Organize the metadata of the sequences, ASVs, and taxonomy, into phyloseq objects which required for further analysis.
  * *6_Statistical_analysis.Rmd*: Merges all the phyloseq objects into a single object, and colapses the taxonomy to family level. It also contains the code to reproduce all the statistical analysis, including figures and tables.
  * *7_ASV_enrichment_analysis*: Compares the ASV within selected project to identify the ASVs that are enriched in the culture/bioreactor. See the paper for more details.
  * *8_Taxonomy_comparison*: Retrieves the taxonomy of the ASVs and compares it within selected studies.
  * *9_ASV_enrichment_plots*: Creates the plots shown in the section Analysis of ASVs enrichment in the bioreators.
  
## RData:

Contains the original phyloseq objects that were used during the statistical analysis. It contains the merged phyloseq objects before collapsing the taxonomy to family level in the file *ps_merge.Rda*, and after collapsing in the file *ps_merge_fam.Rda*. 

It also contains the phyloseq object for each selected study in the folder *primary_id*.

## supporting_metadata

Contains multiple input files required for data analysis.