# Abyss-assembly_test
#First we installed the abyss software from http://www.bcgsc.ca/platform/bioinfo/software/abyss), But we have problem with the installation in CentOS and we installed the software from "Compiling ABySS from source" https://github.com/bcgsc/abyss#compiling-abyss-from-source, then we download the files from (https://www.ebi.ac.uk/ena/data/view/SRR4149288) 
#Afert that we install the software and run the analysis With the bash script "abyss.sh"


 abyss-pe name=azotobacter k=64 in='SRR4149288_1.fastq SRR4149288_2.fastq' #This is the basic script to run the analysis with abyss we ran two analysis with different k-mer to compare.  
 
 abyss-pe name=azotobacter k=64 in='SRR4149288_1.fastq SRR4149288_2.fastq' #One .sh "abyss64.sh" to run the analysis to 64 k-mer
 abyss-pe name=azotobacter k=32 in='SRR4149288_1.fastq SRR4149288_2.fastq'#One .sh  "abyss32.sh" to run the analysis to 32 k-mer  
 
 #in both .sh we ran the assembly annotation with the software "Prokka" version 1.12  the script used is: 
 
prokka azotobacter32-contigs.fa  #This command line create a multiple files with the annotation assembly we used the file .tsv for find the histidine_kinase protein


grep -c "histidine" PROKKA_03082018.tsv #It create a script in bash to count all coincidence to the word "histidine" and give 13 coincidence in both assembler (32 & 64 kmer) before that, it open the file .tsv create of Prokka and find all genes of histidine kinase and found six genes(monomer) that make up the protein. 
