# SIV_Transmission_Study
Set of scripts used to analyze intrarectal and intravenous barcode data from infection of macaques with SIVmac239M.

# Important Considerations: 
With this set of scripts, you will be required to use Jupyter Notebook. Jupyter Notebook is free to download, and we recommend downloading Anaconda Navigator
and using Anaconda to access Jupyter Notebook. Anaconda Navigator is available at: https://www.anaconda.com/products/individual

There are multiple scripts included in this repository, and each one is used for different reasons. 

# IRvsIVFullPipeline: 
This script takes an input of a csv file listing barcode names, counts, and frequencies, from a single sample. The script we used for barcode data acquisition was
kindly provided to us by the Keele lab at NCI-Frederick. We were able to use the output from their R script to feed directly into this script. It manipulates and organizes the data before calculating Simpson's Diversity Index for each sample and compiling it into a single csv that can be opened in Excel if you would like to 
make personal manipulations to the output. The output will tell you the name of the file the data was drawn from (For example, "animal1_day1") as well as a Simpson's Diversity index value. These values will range between 0 and 1, with 0 indicating minimum possible diversity and evenness within the sample, while 1 indicates maximum possible diversity and evenness within the sample. 

# Part1_NefRM9_counts
This script will take a FASTQ input and output a list of nucleotide sequences for a desired region. In this case, I wanted to extract Nef RM9. This script was modified from the Zequencer Zika virus sequence analysis software developed by Dr. Dave O'Connor's lab at the University of Wisconsin-Madison. The original script is documented and provided at https://bitbucket.org/dhoconno/zequencer/src/master/. 

# Part1_GagGW9_counts
This script is nearly identical to the aforementioned Nef RM9 counts script--the only difference is in this case, I wanted to extract Gag GW9. 

# EpitopeScreening
This script takes the output from either the Nef RM9 counts file, or the Gag GW9 counts file (which is the nucleotide sequence to the desired region), and outputs an organized listing of amino acid sequences and their counts. So, you would first use either the Nef RM9 counts file, or the Gag GW9 counts script, and then you would use this script to tidy up the data and identify amino acid sequences and their counts. 

# TatSL8toBarcodeLinkage
This script takes an input FASTQ file and outputs a list of barcodes and the corresponding Tat SL8 epitope sequence linked to that barcode. Note: this is linkage data. Therefore, the output provided ONLY links barcodes to the Tat SL8 sequences tht were found on the exact same read. This is not a general count of barcodes and sequences, but a more specific linkage between barcodes and the corresponding Tat SL8 sequences. 
