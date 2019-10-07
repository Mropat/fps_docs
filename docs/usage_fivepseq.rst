.. _usage_fivepseq:

***************
Fivepseq usage
***************


Command line arguments
----------------------------------

These are the arguments to be provided:

.. code-block:: shell

    fivepseq \
    -g <path_to_genome_fasta> \
    -a <path_to_annotation> \
    -b <path_to_bam_file(s) \  #(multiple files provided with pattern ("parent_dir/*.bam")) 
    -o <output_directory> \
    -t <title_of_the_run> \
    [optional arguments]


Optional arguments
------------------------

**Conflict**

The conflict mode specifies how to deal with files/folders that already exist:

.. code-block:: shell

    --conflict
        default: add - only adds missing files to existing directory 
        overwrite - overwrites all the files in the existing (in case) output directory 
        alt_dir - uses alternative directory by appending '+' suffix to existing (in case) output directory 
|
**Outlier downsampling**

Set p value threshold for outlier detection: counts with less than the [--op] probability of falling into Poisson distribution will be down-sampled. 

.. code-block:: shell

    --op
        default: 0
        -1 - turn off downsampling

Alternatively, set constant threshold for read count down-sampling. Instead of outlier detection, values larger than this constant will be down-sampled.

.. code-block:: shell

    --ds
        default: None
|
**Gene filter**    

Supply a text file with newline-separated list of gene ids you'd like to filter/use. 
The names should correspond to those present under the gene_id tag in the gff file. 
Note: only these genes will be used in all the calculations.

.. code-block:: shell

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

.. code-block:: shell

    -gs/-geneset
        default: None
|
|
|

    