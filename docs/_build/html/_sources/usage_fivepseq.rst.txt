.. _usage_fivepseq:

***************
Fivepseq usage
***************


Core command line arguments
----------------------------------

These are the arguments to be provided::

    fivepseq \
    -g path_to_your_genome_fasta \
    -a path_to_your_annotation_gff (sorry no gtf for now) \
    -b path_to_one_or_many_bam_files 
        (multiple files provided with pattern ("parent_dir/*.bam") within brackets) \
    -o output_directory \
    -t title_of_the_run \
    [optional arguments] \


Optional arguments
------------------------

**Conflict**

The conflict mode specifies how to deal with files/folders that already exist:
::

    --conflict
        default: add - only adds missing files to existing directory 
        overwrite - overwrites all the files in the existing (in case) output directory 
        alt_dir - uses alternative directory by appending '+' suffix to existing (in case) output directory 
|
**Outlier downsampling**

Set p value threshold for outlier detection: counts with less than the [--op] probability of falling into Poisson distribution will be down-sampled. 

::

    --op
        default: 0
        -1 - turn off downsampling

Alternatively, set constant threshold for count down-sampling. Instead of outlier detection, values larger than this constant will be down-sampled.

::

    --ds
        default: None
|
**Gene filter**    

Supply a text file with newline-separated list of gene ids you'd like to filter/use. 
The names should correspond to those present under the gene_id tag in the gff file. 
Note: only these genes will be used in all the calculations.

::

    -gf/-genefilter
        default: None
|

**Gene set analysis**

This option provides a possibility to compare plots for different samples. 
Supply a tab separated text file, with the following structure:

    Columns: gene_attribute (e.g. Name) -> geneset

    Rows: value_of_the_attribute -> geneset_name

Note, the gene_attribute is the attribute name in the gtf or gff file. 
In case of gff, the attribute in the cds feature will be considered. 
With this option, fivepseq will generate a separate plotting directory called genesets, with tabbed-plots to either compare samples for each geneset, or genesets for each sample. The counts folder will also be divided according to the geneset used. The default folder will be named protein_coding.

::

    -gs/-geneset
        default: None
|
**Loci coordinates** (beta)

This option requires a file with coordinates of the loci (e.g. RBP binding coordinates), relative to which, the user wants to generate scatter-plots. 
The file should be tab-separated, with the following structure: 
    Columns: chr->str->start->end->symbol 
    
    Rows: the chromosome name, strand (+ or -), start and end coordinates and the name of the RBP (or the locus).
   
::

    --loci-file
        default: None


Four different output plots will correspond to reads located in:
    (1) 3UTR and CDS regions, 
    (2) only 3UTR, 
    (3) only 5UTR and 
    (4) only CDS.

|


    