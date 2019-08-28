.. _preparig_files:


***************
Peparing data for analysis
***************


Required files
=============================

Fetch fasta and gff files from RefSeq ::



  wget 
  ftp://ftp.ncbi.nlm.nih.gov/genomes/all/*/*/*/*/GCF_000146045.2_R64/*.gff.gz;
  ftp://ftp.ncbi.nlm.nih.gov/genomes/all/*/*/*/*/GCF_000146045.2_R64/*R64_genomic.fna.gz



-----------------

Generate Bam files using STAR or BBmap::

  samtools index file

