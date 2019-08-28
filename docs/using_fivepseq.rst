.. _using_fivepseq:


***************
Fivepseq usage
***************


Count and plot files in a folder
-----------------

This the most common call you'd like to make. These are the arguments to be provided::

	fivepseq 
	-g #Path to your genome in fasta format
	-a #Path to annotation gff
	count_and_plot
	-b #Path to one or many bam files
	-o #0utput directory 
	-t #Title of the run 


Optional arguments
-----------------

The conflict mode specifies how to deal with files/folders that alraedy exist. There are three options you may choose from::

    add (default) - only adds missing files to existing directory
    overwrite - overwrites all the files in the existing (in case) output directory
    alt_dir - uses alternative directory by appending '+' suffix to existing (in case) output directory



This arguments sets the p value threshold for outlier detection: point with less than the --ds probability of falling into Poisson distribution will be down-sampled.::

	optional argument: --downsample/ --ds


Supply a text file with newline-separated list of gene names you'd like to filter/use. The names should correspond to those present under the Name tag in the gff file.

    optional argument: -s/-geneset

