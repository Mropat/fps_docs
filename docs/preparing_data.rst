.. _preparing_data:


***************
Preparing Data
***************

Required files
-----------------

In order to run fivepseq, the following files are required:

|    Genomic sequence file (**.fasta**)
|    Genomic annotation file (**.gff/ .gtf**)
|    Aligned reads (**.bam**)
|    Alignment index (**.bai**)


|
Sourcing genome and annotation files
--------------------------------------

There are multiple resources which maintain and distribute sequence and annotation data, for instance `Ensembl <https://www.ensembl.org/index.html>`_, `RefSeq <https://www.ncbi.nlm.nih.gov/assembly/>`_, and `SGD <https://www.yeastgenome.org/>`_.
However, the naming conventions and format may differ slightly depending on resource. 
For this reason, we recommend that your genomic and annotation files are to be retrieved from the same database.


|
Pre-processing of sequencing data
-----------------------------------

An example of pre-processing pipeline can be found `here <https://github.com/lilit-nersisyan/fivepseq/blob/master/preprocess_scripts/preprocess_yeast.sh>`_. 
In order to run this pipeline, you need to have access to common bioinformatics software such as STAR, umi_tools, BEDtools, samtools, FastQC, MultiQC and cutadapt. 

