# toy example data for UVC 

1. Download and extract the file toy-example-data.tar.gz, then cd to the extracted directory
2. Download and extract the file ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/technical/reference/phase2_reference_assembly_sequence/hs37d5.fa.gz if not available on local system.
3. Set the the environment variables UVC_SCRIPT_DIR to the directory containing uvcTN.sh and hs37d5 to the full-path filename of the extracted hs37d5.fa 
4. Run the following command: ( ${UVC_SCRIPT_DIR}/uvcTN.sh $hs37d5 SRR7757440.bam SRR7757439.bam /tmp/SRR7757440_SRR7757439_TN.vcf.gz SRR7757440,SRR7757439 -q 0 )
5. View results with the command: ( bcftools view /tmp/SRR7757440_SRR7757439_TN.vcf.gz -i "QUAL>=40" | less ) and check that exactly the following two variants appear (not more and not less):
   +  3      16306504        .       C       T
   + 19      49990694        .       G       A
